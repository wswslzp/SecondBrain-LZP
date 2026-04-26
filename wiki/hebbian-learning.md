---
title: "Hebbian Learning"
tags: [neuroscience, learning, synaptic-plasticity]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[memory-consolidation]]", "[[sleep-consolidated-memory]]", "[[complementary-learning-systems]]"]
---

# Hebbian Learning

"Neurons that fire together, wire together." — Donald Hebb (1949)

## 核心原理

当两个神经元**同时激活**时，它们之间的突触连接会**增强**。反之，不同步激活的连接会减弱。这是大脑学习和记忆的基本机制之一。

## 数学表达

连接强度变化：
$$\Delta w_{ij} = \eta \cdot x_i \cdot x_j$$

其中 η 为学习率，x_i 和 x_j 为两个神经元的激活水平。

## 在 SCM 中的应用

[[sleep-consolidated-memory|SCM]] 的 NREM 巩固阶段使用 Hebbian 强化：
- 工作记忆中共同出现的高价值概念之间连接增强
- Δs_ij = 0.1 · I(c_i) · I(c_j)
- 配合**突触下调**（α=0.8）防止无限增长

## 在 AI/ML 中的延伸

- **反向传播**本质上是 Hebbian learning 的梯度版本
- **Self-Organizing Maps (SOM)** 使用竞争性 Hebbian 规则
- **Hopfield Networks** 的权重更新遵循 Hebbian 原理

## References

- [[memory-consolidation]]
- [[sleep-consolidated-memory]]
