---
title: "Deflated Sharpe Ratio"
tags: [quant-trading, statistical-validation, multiple-testing]
date_created: 2026-05-17
date_modified: 2026-05-17
aliases:
  - DSR
  - 通胀夏普率
related: ["[[ai-quant-system]]", "[[backtest-leakage]]", "[[three-gate-evaluator]]"]
---

# Deflated Sharpe Ratio (DSR)

## Overview

**Deflated Sharpe Ratio** 是 Marcos López de Prado 提出的统计方法，用于在**多次试验**（n_trials）的背景下校正 Sharpe 比率，避免选择偏差（selection bias）和 p-hacking。

**核心观察**：测试 10,000 个真实 alpha 为零的随机策略，仅靠运气，**最佳 IS Sharpe 也能超过 3.5**。如果你只看最好的那个，会错把噪声当 alpha。

## 计算逻辑

```python
def deflated_sharpe(returns, n_trials, annualization=252):
    n = len(returns)
    mu, sigma = returns.mean(), returns.std()
    sharpe = mu / sigma * np.sqrt(annualization)
    skew = ((returns - mu)**3).mean() / sigma**3
    kurt = ((returns - mu)**4).mean() / sigma**4

    gamma = 0.5772156649  # Euler-Mascheroni
    sr_per = sharpe / np.sqrt(annualization)
    log_n = np.log(max(n_trials, 2))

    # 期望最大零假设 Sharpe（Bonferroni-style 校正）
    sr0 = (np.sqrt(2 * log_n) - gamma / np.sqrt(2 * log_n)) / np.sqrt(annualization)

    # 偏度/峰度调整后的 z 统计
    num = (sr_per - sr0) * np.sqrt(n - 1)
    den = np.sqrt(max(1 - skew*sr_per + (kurt-1)/4 * sr_per**2, 1e-9))

    dsr = float(norm.cdf(num / den))
    return {
        'observed_sharpe': sharpe,
        'expected_max_null': sr0 * np.sqrt(annualization),
        'dsr_pvalue': dsr,
        'verdict': 'pass' if dsr > 0.95 else 'reject'
    }
```

## 关键直觉

| `n_trials` | 期望"零 alpha 最大 Sharpe" | 含义 |
|-----------|--------------------------|------|
| 1 | ~0 | 单次测试，不需要校正 |
| 100 | ~0.5 | 即使无 edge，运气也能给 Sharpe 0.5 |
| 1,000 | ~0.7 | 1000 次测试需要超过 0.7 才有意义 |
| 10,000 | ~0.85 | 1 万次测试，光靠运气能到 0.85 |

**所以 IS Sharpe 2.0 在 1 次试验下"惊艳"，但在 10,000 次试验下平庸。**

## 在 [[ai-quant-system]] 中的角色

zostaff 把 DSR 用作**第二道硬门**，原则：
- `dsr_pvalue < 0.95` → **拒绝，无人工 override**
- Memory Agent 持续维护 `n_total_attempts`，每次新策略评估时把它喂给 DSR
- 这意味着随着测试越多，门槛会**自动**变得越高

> "Hard gate: `dsr_pvalue < 0.95` = strategy does not ship. No human override."

## 真实示例

zostaff 文章里 6M 动量策略迭代：
- **Iter 2**：修正 look-ahead 后，OOS Sharpe 0.5 → DSR 在 2 trials 下拒绝
- **Iter 3**：加入横截面 vol 归一化，OOS Sharpe 0.85 → DSR 0.97 在 3 trials 下接受

## 与传统 Sharpe 的对比

| 指标 | 多重检验感知 | 偏度/峰度校正 | 适合发表论文 | 适合做交易决策 |
|------|------------|--------------|-------------|---------------|
| 普通 Sharpe | ❌ | ❌ | ❌ | ❌ |
| Probabilistic Sharpe | ❌ | ✅ | 🤷 | 🤷 |
| **Deflated Sharpe** | ✅ | ✅ | ✅ | ✅ |

## 参考

- López de Prado, "The Sharpe Ratio Efficient Frontier" (2008)
- López de Prado, "The Deflated Sharpe Ratio" (2014)

## Sources

- [[ai-quant-system-zostaff]]

## Related

- [[ai-quant-system]]
- [[backtest-leakage]]
- [[three-gate-evaluator]]
