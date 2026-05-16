---
title: "Backtest Leakage"
tags: [quant-trading, backtesting, statistical-validation]
date_created: 2026-05-17
date_modified: 2026-05-17
aliases:
  - 回测数据泄漏
  - look-ahead bias
related: ["[[ai-quant-system]]", "[[walk-forward-validation]]", "[[deflated-sharpe-ratio]]"]
---

# Backtest Leakage

## Overview

**回测数据泄漏（leakage）**指策略在训练或回测时无意中使用了"未来"信息，导致历史业绩看起来漂亮但实盘崩盘。

[[zostaff]] 在 [[ai-quant-system-zostaff]] 中观察到："**每一个 LLM 在生成特征代码时都会引入 look-ahead bias**"。防御不能靠"小心检查"——要靠**结构性约束**让泄漏机械上不可能发生。

> 经典例子：忘记 `signal.shift(1)` 能把纯噪声变成 +190% 的虚假 PnL 曲线。

## 五类泄漏

| # | 类型 | 例子 | 修正 |
|---|------|------|------|
| 1 | **Centered windows** | `rolling(20, center=True)` 用了未来的 10 根 K 线 | 永远不要 `center=True` |
| 2 | **忘记 `shift(1)`** | 用 bar t 收盘信号在 bar t 交易（不可能） | `signal.shift(1)` 后再算 PnL |
| 3 | **全样本标准化** | 用整个数据集的 mean/std 算 z-score | 每个 fold 重新拟合 scaler |
| 4 | **幸存者偏差** | 用今天的 S&P 500 成分回测 10 年 | Point-in-time index membership |
| 5 | **财报重述** | 用 2013 年重述的 FY2010 财报数据 | Point-in-time 数据供应商 |

## 防御层 1：FeaturePipeline（结构防御）

```python
class FeaturePipeline:
    """Every feature computed from STRICTLY past data, by construction."""
    def add(self, name, fn, lookback):
        # fn(window) -> scalar
        # window = data.iloc[t-lookback : t]  # 永远只看过去
        ...
```

每个特征用 `(name, fn, lookback)` 三元组定义，遍历时窗口严格用 `iloc[i-lookback : i]`，**结构上不可能看到未来**。

## 防御层 2：`signal.shift(1)`

约定：信号在 bar t 收盘决定，**bar t+1 开盘**才能交易。所有 PnL 计算前必须 shift。

```python
returns = np.log(prices / prices.shift(1))
position = signal.shift(1).fillna(0)  # CRITICAL
gross_pnl = position * returns
```

## 防御层 3：[[walk-forward-validation]]

随机 k-fold 在时序数据上 = 用未来训练预测过去 = 一定泄漏。必须用 walk-forward + purge。

## 防御层 4：Critic Agent 对抗审查

zostaff 的 Critic Agent 系统提示开篇：
> "ASSUME THIS STRATEGY IS BROKEN until you prove otherwise."

明确检查 8 项：
1. Look-ahead bias
2. Survivorship bias
3. Overfitting > 50%
4. Trades < 100（样本不足）
5. Mechanism inconsistency（机制说不通）
6. Hidden optimization（参数偷优化）
7. Unrealistic costs
8. Tail risk hidden by Sharpe

## 真实案例

zostaff Iter 1：
```python
ret_6m = df.groupby('ticker')['close'].pct_change(periods=126)
rank = ret_6m.groupby(level='date').rank(pct=True)
```
- IS Sharpe 2.1，OOS Sharpe 1.8 — 看起来很棒
- Critic：`pct_change(126) uses current bar's close, look-ahead by one bar`
- 修正后（Iter 2）：IS 0.7，OOS 0.5
- **结论：look-ahead 就是全部 alpha**

## 个人备注

对长期持有 + 个股集中度高的投资者（不只是高频量化）：
- 你做任何"如果当年这样做会怎样"的复盘，都要警惕**幸存者偏差**（你只记得 NVDA 涨，不记得当年同期被淘汰的对手）
- "如果我那时候卖了 X 持有 Y" 这种倒推，本质上是 future-leak 思维

## Sources

- [[ai-quant-system-zostaff]]

## Related

- [[ai-quant-system]]
- [[walk-forward-validation]]
- [[deflated-sharpe-ratio]]
- [[three-gate-evaluator]]
