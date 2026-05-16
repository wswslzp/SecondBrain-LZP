---
title: "Walk-Forward Validation"
tags: [quant-trading, backtesting, statistical-validation]
date_created: 2026-05-17
date_modified: 2026-05-17
aliases:
  - 滚动验证
  - WFV
related: ["[[ai-quant-system]]", "[[backtest-leakage]]", "[[deflated-sharpe-ratio]]"]
---

# Walk-Forward Validation

## Overview

**Walk-Forward Validation**（滚动前向验证）是时序数据的正确交叉验证方法。

> 核心原则：随机 k-fold 在时序数据上 = 用未来训练预测过去 = 一定泄漏 = Sharpe 必虚高 = 实盘必死。

## 三种模式

### 1. Walk-Forward（基础）

```
[train] [test]
        [train→ ] [test]
                 [train→ → ] [test]
                            ...
```

每个 fold 训练窗口往前推一步，测试集是紧接着的下一段。简单、对计算友好。

### 2. Anchored Walk-Forward

```
[train             ] [test]
[train               → ] [test]
[train                  → → ] [test]
                              ...
```

训练集起点不动（锚定），只增长右边界。模拟"模型记住所有历史"的场景。

### 3. Combinatorial Purged CV（CPCV）

López de Prado 提出。把时间切成 N 组，每次选 k 组当测试集，剩下当训练集，**按组合数枚举**。

例：N=10，k=2 → C(10,2) = 45 条不同路径。

```python
def combinatorial_purged_cv(n_bars, n_groups=10, n_test_groups=2,
                            purge_bars=5, embargo_bars=5):
    for test_idx in combinations(range(n_groups), n_test_groups):
        # purge: 测试集前 5 根 bar 从训练集剔除
        # embargo: 测试集后 5 根 bar 从训练集剔除
        ...
```

**Purge** 防止训练样本与测试样本因为 label 期重叠而泄漏；**Embargo** 防止测试集结束后的样本被同期 label 污染。

## 关键指标：Degradation Ratio

```
degradation = OOS Sharpe / IS Sharpe
```

| 范围 | 解读 |
|------|------|
| **0.6 - 0.8** | ✅ 健康（普遍 OOS 衰减）|
| < 0.3 | ❌ 严重过拟合 |
| > 1.0 | ⚠️ 可疑 — 数据错误 / 运气 / 漏看泄漏 |

## 报告分布而非均值

CPCV 给你 45 条路径，**别只看均值**。看：
- Sharpe 分布（5/50/95 分位）
- 最坏路径的回撤
- 一致性（多少比例路径 Sharpe > 0）

均值漂亮但分布双峰 = 策略在某些 regime 死掉，是个 regime-fragile alpha，不要碰。

## 与 [[ai-quant-system]] 的关系

zostaff 的 orchestrator 用 walk-forward + purge 做 OOS 评估：

```python
walk_forward_evaluate(data, fit_fn, predict_fn,
                     train_size=252, test_size=63, purge=5)
```

OOS signal 然后喂给 [[deflated-sharpe-ratio]] 做最后的统计校正。

## Pitfall

⚠️ **Walk-forward 不等于"无泄漏"**。如果 feature 本身有 look-ahead（见 [[backtest-leakage]]），即使用了 walk-forward，每个 fold 内仍然泄漏。两者是正交的防御层，必须**同时**用。

## Sources

- [[ai-quant-system-zostaff]]

## Related

- [[ai-quant-system]]
- [[backtest-leakage]]
- [[deflated-sharpe-ratio]]
