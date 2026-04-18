---
title: "Frontier Systems（前沿系统）"
tags: [ai, infrastructure, compute, systems]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[anjney-midha]]", "[[compute-infrastructure]]", "[[context-feedback-loops]]"]
---

# Frontier Systems

Stanford CS 153（2026 春）的课程框架。由 [[anjney-midha]] 和 Mike Abrash 共同授课，前称"Security at Scale"，2026 年更名反映 AI 时代的全栈重写。

## AI 全栈

从底到顶：

1. **资本** — 最灵活
2. **土地/电力/外壳** — 数据中心建设、能源
3. **芯片** — Jensen Huang (Nvidia), Lisa Su (AMD)
4. **云** — 基础设施层（Satya Nadella/Microsoft）
5. **模型** — Anthropic, OpenAI（Sam Altman）
6. **Agents**
7. **应用** — 部署为解决方案
8. **治理** — 安全、信任、部署框架

## 伟大的过渡（Great Transition）

> "For the first time at least in my life, I can't remember a time when there was such a big revisiting of assumptions up and down the stack where everyone's trying to figure something out."

每个层级都在重新审视假设。不确定性 = 机会。

## 四大瓶颈（4 Cs）

Midha 的框架：
- **Context**（[[context-feedback-loops]]）
- **Compute**（[[compute-infrastructure]]）
- **Capital**
- **Culture**

CS 153 课程主要覆盖前两个。

## 制造智能的简单配方

```
Compute + Data + Algorithms → Intelligence
```

### 工业化过程
- 4 年前：手工匠式
- 现在：
  - 基础训练：每年 2 次 × 100K GB300
  - Mid-training：2-4 次/年 × 10% 计算
  - Post-training（RL + SFT）：**连续进行**，已占近一半计算

## 规模定律遇见市场

Anthropic 4 年从 $0 到 $20B 的关键：
- 计算资本 → 60-90 天后 → 能力跳跃 → 收入跳跃
- **Dollar in, dollar out** — 硬资产（3-4× 收入倍数）转化为软件收入（30-40×）
- 输出比输入对市场有 **10× 价值**

## Recursive Self-Improvement

Midha 的系统级观点（非模型级）：
- 一个执行良好的公司不断改进自己的 compute/context/capital 飞轮
- 不一定需要"超级智能模型"

## 来源
- [[cs153-frontier-systems]]
