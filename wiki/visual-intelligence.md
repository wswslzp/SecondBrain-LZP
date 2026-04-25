---
title: "Visual Intelligence"
tags: [ai, vision, image-generation, diffusion]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[multimodal-ai]]", "[[andreas-blattmann]]", "[[amit-jain]]"]
---

# Visual Intelligence

视觉领域的"foundation intelligence"——不再是单一任务（text-to-image）而是系统性能力。[[andreas-blattmann]]（BFL）和 [[amit-jain]]（Luma）的交汇主题。

## 定义（Blattmann）

Visual intelligence 建立在两个支柱上：
1. **观察**（pre/mid training，图像+视频+音频）
2. **交互**（post-training，action prediction，物理反馈）

**不仅是生成**：单纯生成"漂亮像素"是"stupid model"。智能需要世界理解 + 推理 + 行动预测。

## 四个应用域

从单一 text-to-image 扩展到：

### 1. 内容创作（Content Creation）
- 图像、视频、音频、音乐生成
- 广告、电影、营销
- 教育材料

### 2. 物理 AI / 机器人
- Action prediction：给定视频/图像 → 预测下一个键盘/力矩动作
- Post-training 连接到物理世界产生反馈

### 3. Computer Use
- 视觉理解屏幕
- 预测点击/键盘操作
- 完成任务

### 4. 世界建模与仿真
- 可微分世界模型
- 预测"如果 Caesar 没被暗杀"之类反事实

## 与语言模型的区别

### 相似
- Iterative（迭代）模型
- 规模与 compute 可预测相关

### 不同

**Diffusion/flow matching 的 iterative 方向**：artificial time axis（从纯噪声到数据）
- 数据效率**低**（每个样本可在 continuous trajectory 上无限采样）
- 推理可**蒸馏到 1-2 步**（[[distillation]]）

**LLM 的 iterative 方向**：token by token
- 数据效率**高**（所有 token 并行训练）
- 推理无法简单跳过

**开放问题**：如何结合两者优点？

## 可验证性问题

与代码、材料科学不同，视觉美学**不易验证**：
- "5 手指"可验证
- "character consistency"可验证
- 但"这张图好看吗"依赖受众

→ 导致两个后果：
1. 需要海量人工标注
2. **开源权重 + 客户定制**成为商业策略（见 [[open-weights-strategy]]）

## 机器人的关键解锁

从观察到交互的 pipeline：
```
[视觉 pre-training] → 条件化 action → [Robot 动作] → 物理反馈 → 数据回流 → [更好的模型]
```

这是物理 AI 终于 work 的关键。

## 3D 表征辩论

### Blattmann：反对显式 3D
> "I don't have an explicit 3D representation in my head. I learn from video and audio."

人类是从时空视频学习隐式 3D 理解。

### Midha：部分认同，但有 niche
- Point clouds、meshes 对机器人室内定位（GPS denied）仍有用
- 但对人机交互："narrow, inflexible, static"
- 不如可整合时间+音频的多模态表征

## 关键进展

- **2021**：Latent Diffusion（可微压缩 + 低维训练）
- **2022**：Stable Diffusion 爆红
- **2024**：Flux 1 解决手指问题
- **2025**：Flux Context 解决 character consistency
- **2026-03**：Self Flow（多模态表征对齐）

## 关键引语

> "Visual models are starting to become way more than content creation. It's about physical AI, robotics, computer use, world modeling." — Blattmann

> "Image and video models today are really stupid—not in a derogatory way. They have no understanding of what they're generating, the physics of it, any introspection." — Amit Jain

## 来源
- [[cs153-bfl-andreas-blattmann]]
- [[cs153-luma-amit-jain]]
