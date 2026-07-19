---
title: "Frontier Systems（前沿系统）"
tags: [ai, infrastructure, compute, systems]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[anjney-midha]]", "[[compute-infrastructure]]", "[[context-feedback-loops]]", "[[ai-factory]]", "[[unified-models]]", "[[product-management-ai-era]]", "[[nikhyl-singhal]]", "[[venture-capital-systems]]", "[[ai-energy-bottleneck]]"]
---

# Frontier Systems

Stanford CS 153（2026 春）的课程框架。由 [[anjney-midha]] 和 Mike Abrash 共同授课，前称"Security at Scale"，2026 年更名反映 AI 时代的全栈重写。

## AI 全栈

从底到顶：

1. **资本** — 最灵活
2. **土地/电力/外壳** — 数据中心建设、能源
3. **芯片** — [[jensen-huang|Jensen Huang]]（[[nvidia|Nvidia]]）, Lisa Su (AMD)
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

CS 153 早期讲座主要覆盖前两个（Context/Compute）；**Capital 与 Culture** 由 [[ben-horowitz]] 的一讲补上（[[venture-capital-systems]]、[[network-effects]]），而 AI 全栈里「土地/电力/外壳」这一**实体层**由 [[scott-nolan]] 的能源专讲补上（[[ai-energy-bottleneck]]）。

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

## 跨领域的 Frontier Lab 案例

CS 153 讲座覆盖了不同模态下的前沿系统：

| 领域 | Lab | 核心架构决定 |
|------|-----|-------------|
| 代码 | Anthropic | Context 独占 + RL |
| 图像 | [[andreas-blattmann]] / BFL | Latent diffusion + [[open-weights-strategy]] |
| 视频/多模态 | [[amit-jain]] / Luma | [[unified-models]] |
| 语音 | [[mati-staniszewski]] / ElevenLabs | Cascaded 企业，混合方向 |

详见 [[ai-factory]] 与 [[cascaded-vs-fused-architectures]]。

## 非技术一讲：product 与 career

CS153 第 9 讲切到产品与职业（讲者 [[nikhyl-singhal]]，Skip）——前五讲都是技术创始人谈 AI/context/the loop，这一讲谈 **AI 如何把产品管理从「information mover」重塑为「有 judgment 的 builder」**、组织变平、中层经理承压。详见 [[product-management-ai-era]] 与 [[career-as-chapters]]。

## 来源
- [[cs153-frontier-systems]]
- [[cs153-luma-amit-jain]]
- [[cs153-bfl-andreas-blattmann]]
- [[cs153-elevenlabs-mati-staniszewski]]
- [[cs153-skip-nikhyl-singhal]]
- [[cs153-jensen-huang-compute]]
- [[cs153-ben-horowitz]]
- [[cs153-scott-nolan-energy]]
