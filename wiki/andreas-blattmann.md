---
title: "Andreas Blattmann"
tags: [person, ai, bfl, flux, stable-diffusion, diffusion]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[visual-intelligence]]", "[[open-weights-strategy]]", "[[distillation]]"]
---

# Andreas Blattmann

Black Forest Labs (BFL) 联合创始人，Stable Diffusion 共同作者。

## 背景
- 德国出生，原学机械工程
- 2019 年转入 AI，在 Heidelberg PhD 实验室
- 与 Robin 和 Patrick 共同创办 BFL（位于 Freiburg，黑森林地区）
- BFL 现值 >$30 亿，25 人团队，**整个公司历史仅 1 人离职**

## 关键贡献

### Latent Diffusion（2021-22）
核心想法：无法在像素空间训练生成模型（太贵）→ 学一个压缩模型（类似学习 JPEG）→ 在低维 latent 空间训练。

**结果**：比 Google/OpenAI 少几个数量级的计算也能做出 SOTA。

### Stable Diffusion（2022）
将 latent diffusion 扩展到文本条件的图像生成。在湾区爆红——视觉输出让非 ML 社区也能感受到生成模型的威力。

### Flux 系列（BFL）
- Flux 1：首个真正解决"5 根手指"的模型
- Flux 1 Context：用户反馈驱动的图像编辑模型（character consistency）
- 与 Meta 合作为 20 亿用户驱动图像编辑

### Self Flow（2026-03）
多模态 representation alignment 的突破。让视觉生成模型跨模态自动学习统一表征。

## 核心观点

### 自然 vs 非自然表征
- 自然：图像、视频、音频（太阳的电磁波，人无法控制）
- 非自然：文本（进化压缩的通信编码，信息密度高）
- **3 岁孩子比任何 LLM 聪明** → 因为他们先学自然表征
- 语言是高阶推理的后续，不是起点

### 3D 表征辩论
> "I don't have an explicit 3D coordinate representation in my head."

人类学 3D 是通过视频 + 交互的隐式模式。所以不押注显式 3D 表征。
（但 [[anjney-midha]] 部分反驳：狭窄场景仍有用）

### 持久性胜过天才
> "The frontier is persistent. Most teams give up right before they succeed."

BFL 在 ChatGPT-1 image 发布时差点 panic，但没放弃，60 天后 Context 发布压过对手。

## 与本 Wiki 的关系

在 [[cs153-bfl-andreas-blattmann]] 讲座中覆盖：
- Latent diffusion 的起源
- BFL 的 [[ai-factory]] 实例
- Flux 商业模式（[[open-weights-strategy]]）
- Diffusion vs LLM 的架构权衡
- Self Flow

## 来源
- [[cs153-bfl-andreas-blattmann]]
