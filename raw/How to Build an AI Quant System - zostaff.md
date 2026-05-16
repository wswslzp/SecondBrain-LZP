# How to Build an AI Quant System. Test 1,000 Strategies per Week.

- **Author:** @zostaff
- **Date:** 2026-05-13
- **URL:** https://x.com/zostaff/status/2054533153893613839
- **Type:** X Article (long-form)
- **Views:** 328.2K
- **Repo:** https://github.com/zostaff/ai-quant-researcher

---

Backtest engine, feature pipeline, validation stack, AI research loop, production monitoring, all code, no filler.

In 2018 a serious quantitative strategy took a researcher with a PhD and a few years of experience between two and six months, from idea to validated backtest. In 2026, the same person working with an LLM stack does it in an evening. That is a 50× change in the unit of work, and it changes everything downstream: what edges are findable, how fast they decay, what skills matter.

But faster generation without faster validation is not a 50x productivity gain. It is a 50x amplifier of statistical garbage. This article is the engineer's manual for that new world, almost entirely code, with just enough conceptual scaffolding to understand why each piece exists.

Everything described here is packaged into a working repository: https://github.com/zostaff/ai-quant-researcher

## Architecture

Six agents, one orchestrator. Each agent is a single Claude API call with a strict role prompt, narrow tool scope, and a clear acceptance criterion. The orchestrator runs the loop: hypothesis → data → code → backtest → critique → risk check → memory → next hypothesis.

| Agent | Role | Tools |
|-------|------|-------|
| Hypothesis | Generates economic stories with named mechanisms | Web search, memory of past failures |
| Data | Fetches, aligns, point-in-time-corrects, engineers features | Data loaders, FeaturePipeline |
| Code | Writes vectorized backtest with proper `shift(1)` and costs | Code execution sandbox |
| Critic | Adversarially reviews for leakage, overfitting, p-hacking | Code reader, metrics analyzer |
| Risk | Sizes positions, checks correlation to existing book | Portfolio state |
| Memory | Tracks every attempt so multiple-testing burden is known | Attempt database |

Three hard gates before any strategy ships:
1. Critic passes structural review
2. Deflated Sharpe clears the multiple-testing bar
3. Risk agent confirms portfolio-level fit

## Backtest engine

If this is wrong, everything downstream is wrong. Build it once, never touch it.

### Vectorized backtest

```python
import numpy as np
import pandas as pd
from dataclasses import dataclass

@dataclass
class BacktestConfig:
    initial_capital: float = 100_000
    fee_bps: float = 5.0          # round-trip fees in basis points
    slippage_bps: float = 2.0     # additional cost per trade
    max_leverage: float = 1.0
    annualization: int = 252

def vectorized_backtest(prices: pd.Series, signal: pd.Series,
                        cfg: BacktestConfig = BacktestConfig()) -> dict:
    """
    `signal`: desired position at close of each bar.
    +1 = full long, -1 = full short, 0 = flat, fractional OK.
    CRITICAL: position = signal.shift(1). We decide at bar t's close,
    trade at bar t+1's open. Without this shift = look-ahead bias.
    """
    returns = np.log(prices / prices.shift(1))
    position = signal.shift(1).fillna(0).clip(-cfg.max_leverage, cfg.max_leverage)
    gross = position * returns
    turnover = position.diff().abs().fillna(0)
    costs = turnover * (cfg.fee_bps + cfg.slippage_bps) / 1e4
    net = gross - costs
    equity = cfg.initial_capital * np.exp(net.cumsum())
    return {
        'returns': net, 'gross_returns': gross, 'equity': equity,
        'position': position, 'turnover': turnover, 'costs': costs,
        'metrics': performance_metrics(net, cfg.annualization),
    }
```

### Metrics that matter

```python
def performance_metrics(returns: pd.Series, annualization: int = 252) -> dict:
    r = returns.dropna()
    if len(r) < 30 or r.std() == 0:
        return {'sharpe': 0, 'reason': 'insufficient_data'}
    mean_ann = r.mean() * annualization
    vol_ann = r.std() * np.sqrt(annualization)
    sharpe = mean_ann / vol_ann
    downside = r[r < 0]
    sortino = mean_ann / (downside.std() * np.sqrt(annualization)) if len(downside) > 0 else np.inf
    cum = r.cumsum()
    drawdown = cum - cum.cummax()
    max_dd = drawdown.min()
    calmar = mean_ann / abs(max_dd) if max_dd < 0 else np.inf
    return {
        'sharpe': sharpe, 'sortino': sortino, 'calmar': calmar,
        'mean_return_ann': mean_ann, 'vol_ann': vol_ann,
        'max_drawdown': max_dd, 'skewness': r.skew(),
        'excess_kurtosis': r.kurtosis(), 'hit_rate': (r > 0).mean(),
        'profit_factor': ...,  # see source
    }
```

Three metrics most people ignore but shouldn't: **excess kurtosis > 3** = fat tails (your Sharpe 2 strategy is hiding crash risk), **calmar** = what LPs care about (recovery psychology), **profit factor** = distinguishes robust trend-following from fragile mean-reversion.

### Event-driven engine

For intraday strategies where fill detail matters, a bar-by-bar engine with pending orders, limit fills, and slippage. Both engines should agree on the same strategy within cost tolerance. If they don't, the vectorized one has a bug (usually forgotten shift or double-counted costs).

### Realistic cost model

Constant `fee_bps` is a lie. Real costs depend on size, volatility, and venue:

```python
def realistic_cost_bps(order_size, adv, current_vol, venue='lit'):
    """Decomposed: spread + square-root impact + venue fees."""
    spread_bps = 1.5 + 5 * current_vol
    impact_bps = 10 * np.sqrt(order_size / adv) * 100
    venue_bps = {'lit': 0.3, 'dark': 0.2, 'rfq': 0.5}.get(venue, 0.3)
    return spread_bps / 2 + impact_bps + venue_bps
```

Sweep `order_size` with this model. Your "Sharpe 2" at $100k becomes Sharpe 0.4 at $10M. That's your strategy's capacity.

## Features and leakage

Every LLM I've tested has introduced look-ahead bias when generating feature code. The defense is structural: make leakage mechanically impossible.

### Five leakage types

| # | Type | Example | Fix |
|---|------|---------|-----|
| 1 | Centered windows | `rolling(20, center=True)` | Never `center=True` |
| 2 | Forgotten `shift(1)` | Feature uses bar t's close to trade at bar t | `signal.shift(1)` before PnL |
| 3 | Full-sample standardization | Z-score over entire dataset before train/test split | Refit scaler per fold |
| 4 | Survivorship | Backtest on today's S&P 500 with 10yr history | Point-in-time index membership |
| 5 | Restated fundamentals | Using 2013-restated FY2010 earnings | Point-in-time vendors |

Forgetting `shift(1)` turns pure noise into a fake +190% PnL curve.

### Leakage-proof feature pipeline

```python
class FeaturePipeline:
    """Every feature computed from STRICTLY past data, by construction."""
    def __init__(self):
        self.transforms = []
    def add(self, name, fn, lookback):
        """fn(window) -> scalar. window = data.iloc[t-lookback : t] (past only)."""
        self.transforms.append((name, fn, lookback))
        return self
    def fit_transform(self, data):
        out = pd.DataFrame(index=data.index)
        for name, fn, lookback in self.transforms:
            values = np.full(len(data), np.nan)
            for i in range(lookback, len(data)):
                window = data.iloc[i-lookback:i]
                try:
                    values[i] = fn(window)
                except Exception:
                    values[i] = np.nan
            out[name] = values
        return out
```

### Triple-barrier labels (López de Prado)

Better than "did price go up in 5 days?" — respects the path, the stop, and the take-profit:
+1 = profit target hit first, -1 = stop hit first, 0 = time exit.

## Validation

Random k-fold on time series = future data trains the model that predicts the past = inflated Sharpe = garbage.

### Walk-forward

Degradation ratio = OOS Sharpe / IS Sharpe.
- Healthy: 0.6-0.8
- Below 0.3 = overfit
- Above 1.0 = suspicious (data error or lucky regime)

### Combinatorial purged CV

45 paths instead of 5-10 folds. Report the distribution, not the mean.

### Deflated Sharpe ratio

Tested 10,000 strategies with zero edge → best in-sample Sharpe > 3.5 by pure luck. The deflated Sharpe corrects for this:

```python
def deflated_sharpe(returns, n_trials, annualization=252):
    # ... computes expected_max_null Sharpe given n_trials,
    # then asks: does observed Sharpe beat it after skew/kurt adjustment?
    return {'observed_sharpe': sharpe,
            'expected_max_null': sr0 * np.sqrt(annualization),
            'dsr_pvalue': dsr,
            'verdict': 'pass' if dsr > 0.95 else 'reject'}
```

**Hard gate: `dsr_pvalue < 0.95` = strategy does not ship. No human override.**

## AI research loop with Claude

### Agents (each = one Claude API call)

- `hypothesis_agent`: generates ONE specific strategy hypothesis (not "trade momentum" — "long top-decile 6M return Russell 1000 ex-financials, short bottom decile, skip most recent month, weekly rebalance, inverse-vol weighted")
- `code_agent`: implements as `def make_signal(df) -> pd.Series` with rules: must use FeaturePipeline, must `signal.shift(1)`, must apply `realistic_cost_bps`, signal in [-1, +1]
- `critic_agent`: opens with **"ASSUME THIS STRATEGY IS BROKEN until you prove otherwise"**, checks 8 failure modes (look-ahead, survivorship, overfit >50%, trades <100, mechanism inconsistency, hidden optimization, unrealistic costs, hidden tail risk)

### The orchestrator (3 gates)

```
for i in range(max_iterations):
    h = hypothesis_agent(memory)
    h.code = code_agent(h)
    signal = exec_in_sandbox(h.code, price_data)
    result = walk_forward_evaluate(signal, price_data)

    # Gate 1: Critic
    critique = critic_agent(h, h.code, result)
    if not critique.passes: continue

    # Gate 2: Deflated Sharpe
    dsr = deflated_sharpe(oos_ret, memory.n_total_attempts)
    if dsr['verdict'] == 'reject': continue

    # Gate 3: Correlation to existing book
    if max(corr with accepted strategies) > 0.7: continue

    accepted.append((h, result))
```

### Real iteration — the AI catches its own bug

**Iter 1**: 6M momentum. IS Sharpe 2.1 / OOS Sharpe 1.8. Looks great.
Critic: `pct_change(126) uses current bar's close, look-ahead by one bar`. **Rejected.**

**Iter 2**: Same signal through FeaturePipeline + skip-month + shift. IS 0.7 / OOS 0.5.
The look-ahead **was** the entire alpha. Critic passes structure but DSR rejects (too low for 2 trials). **Rejected.**

**Iter 3**: Add cross-sectional vol normalization. OOS Sharpe 0.85, degradation 18%, kurtosis 3.1. DSR 0.97 at 3 trials. **Accepted.**

The AI didn't produce one great strategy. It produced candidates, failed most of them, and the **system** caught the failures.

## Production

### Paper trading
Run live data, simulated fills, minimum 30 calendar days. Measure fill_rate and slippage deviation vs backtest. Any alert → do not graduate to live.

### Kill-switches
```python
@dataclass
class KillSwitchConfig:
    intraday_loss_pct: float = 0.02
    rolling_5d_loss_pct: float = 0.05
    max_concentration_pct: float = 0.20
    max_leverage: float = 2.0
    data_staleness_sec: int = 60
```
Halt = flatten + stop. Reset = manual only after root-cause analysis. Same trigger twice in a week = strategy suspended.

### Audit log
"Why did we go long XYZ at 14:32?" must always have a deterministic, reproducible answer.

## Where AI still fails

- **Regime breaks** — LLMs extrapolate from training history. 2008/2020 pattern recognition not yet replicated.
- **True novelty** — LLMs combine and recombine; they rarely create. Won't invent the next cointegration framework.
- **Adversarial markets** — Every alpha is a brief window. LLMs are weak at modeling adversaries who themselves use LLMs.
- **Capacity** — Most AI-found "alphas" work at $100k and break at $10M. No intuition for market impact at scale.
- **Audit trail** — "The LLM thought it was a good idea" is not defensible to a regulator or LP.

> A useful test: if you cannot explain in plain language **why** a strategy should work, in a way that survives a hostile question from a senior PM, don't trade it. The economic intuition test hasn't changed since 1986. Only generation speed has.

## Closing

The tools are extraordinary. The temptation to deploy without validation is extraordinary. The cost of getting it wrong, when AI lets you get it wrong faster than ever, is extraordinary.

**Build slow. Validate hard. Trade small until you've proven yourself, to yourself.**
