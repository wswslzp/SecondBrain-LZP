---
title: "Three-Gate Evaluator"
tags: [quant-trading, ai-agents, system-design]
date_created: 2026-05-17
date_modified: 2026-05-17
aliases:
  - 三道硬门
related: ["[[ai-quant-system]]", "[[deflated-sharpe-ratio]]", "[[multi-agent-research-loop]]"]
---

# Three-Gate Evaluator

## Overview

**Three-Gate Evaluator** 是 [[zostaff]] 在 [[ai-quant-system]] 里提出的策略验收设计：每个候选策略必须连续通过三道独立的硬门，**任意一道挂掉策略就死**，**没有人工 override**。

设计哲学：量化研究最大的敌人是研究员自己的"再试一次"。规则化、不可妥协的门槛是阻止 p-hacking 的唯一办法。

## 三道门

### Gate 1: Critic Agent 结构审查

对抗式 LLM Agent，系统提示开篇：
> "ASSUME THIS STRATEGY IS BROKEN until you prove otherwise."

检查 8 类问题：
1. Look-ahead bias
2. Survivorship bias
3. Overfitting (degradation > 50%)
4. Trades < 100（样本不足）
5. Mechanism inconsistency（代码与假设不符）
6. Hidden optimization（参数偷优化）
7. Unrealistic costs
8. Tail risk hidden by Sharpe（高 kurtosis）

输出：
```json
{
  "passes": bool,
  "issues_found": [...],
  "severity": "fatal|major|minor",
  "suggested_fix": "..." or null
}
```

### Gate 2: Deflated Sharpe Ratio

详见 [[deflated-sharpe-ratio]]。

```python
dsr = deflated_sharpe(oos_ret, memory.n_total_attempts)
if dsr['verdict'] == 'reject':
    continue  # 拒绝，无 override
```

关键：`n_total_attempts` 由 Memory Agent 累积。**测试越多，门槛越高**。

### Gate 3: 组合相关性

新策略与所有已接受策略的 OOS PnL 相关性必须 < 0.7：

```python
if accepted:
    corrs = [np.corrcoef(oos_ret, prev_ret)[0, 1] for prev in accepted]
    if max(corrs) > 0.7:
        continue  # 拒绝 — 与现有 book 太像
```

防止收集"5 个看起来不同但其实是同一个 momentum 因子的策略"。

## 设计原则

### 1. No human override

人类研究员的"override 权"是 p-hacking 的源头。即使你 100% 确信这是个真 alpha，过不了 DSR 就不上。

### 2. Gates 独立

三道门检查不同维度（结构 / 统计 / 组合），独立无相关。一个策略可能通过 Critic 但被 DSR 拒，反之亦然。

### 3. Memory 跨循环累积

Memory Agent 不只记成功的，**所有失败也要记**。`n_total_attempts` 持续增长，相当于研究员的"经验衰减"——你越尝试越多，对每个新候选越苛刻。

## 真实案例

zostaff 文章里的迭代：

| 迭代 | Gate 1 (Critic) | Gate 2 (DSR) | Gate 3 (Corr) | 结果 |
|------|-----------------|---------------|----------------|------|
| 1 | ❌ 揪出 look-ahead | — | — | 拒绝 |
| 2 | ✅ | ❌ Sharpe 0.5 不够 (2 trials) | — | 拒绝 |
| 3 | ✅ | ✅ DSR 0.97 (3 trials) | ✅ 第一个，无对比 | **接受** |

## 可推广的设计模式

> **任何重大、不可逆的决策**都可以套用三道门思路。

例：投资决策版（Roc 适用）
- **Gate 1（机制审查）**："这个买入/卖出的'why'用大白话说得通吗？senior PM 会不会一句话戳穿我？"
- **Gate 2（统计校正）**："我这种思路在过去做过几次了？历史上类似决策的命中率有意义吗？"
- **Gate 3（组合一致性）**："这个动作会不会让我的整体仓位过度集中或与已有逻辑矛盾？"

任意一道挂掉就不动手。**这种设计哲学比任何具体策略都有持久价值。**

## Sources

- [[ai-quant-system-zostaff]]

## Related

- [[ai-quant-system]]
- [[deflated-sharpe-ratio]]
- [[multi-agent-research-loop]]
- [[backtest-leakage]]
