---
title: "CS153 '26: Visual Intelligence Frontiers — Andreas Blattmann, Black Forest Labs"
author: "Andreas Blattmann"
date_ingested: 2026-04-18
date_published: 2026-04-11
tags: [ai, image-generation, diffusion, bfl, flux, stable-diffusion, multimodal]
url: "https://www.youtube.com/watch?v=TNxXs20yhMQ"
type: lecture-transcript
---

# CS153 '26: Visual Intelligence Frontiers — Andreas Blattmann (BFL)

Stanford CS 153 第 2 周讲座。Andreas Blattmann 是 Stable Diffusion 共同作者、Black Forest Labs (BFL) 联合创始人。讨论视觉智能前沿、Flux 模型系列、以及 BFL 如何从 25 人团队成长到 30 亿美元估值。

## 核心论点

视觉智能是下一个解锁领域。起点是观察（自然表征：图像、视频、音频），终点是**交互**（机器人、computer use）。Transformer backbone + self-flow 对齐让跨模态学习成为可能。

## 关键要点

### Latent Diffusion 突破
- 2019-21 在 Heidelberg 实验室（资源远少于 Google/OpenAI）
- 无法在像素空间训练生成模型（计算太贵）
- 解决方案：**训练压缩模型**（类似学习的 JPEG 编码器），找到感知等效的低维表示
- 在 latent 空间训练生成模型 → 节省数个数量级的计算
- 导致了 Stable Diffusion 2022 发布，在湾区被狂热追捧

### 自然 vs 非自然表征
- **自然表征**：图像、视频、音频（太阳、电磁波、人类无法控制的来源）
- **非自然表征**：文本（人造，进化中压缩为高效通信）
- 每个字符承载的信息比每个像素高得多 → 文本冗余度低
- **结论**：必须先学自然表征（像婴儿一样先观察），语言只是高阶推理的后续

### 从单模态到多模态
- 2022 年 Stable Diffusion = 单模态（text-to-image）
- 仅用于内容创作
- 现在目标：**统一多模态模型**
  - 物理 AI（机器人）
  - Computer use
  - 世界建模与仿真
  - 内容创作

### 跨模态的学习价值
例子：两个刚体碰撞 → 必然伴随声音 → 模型通过观察"声音与动作的相关性"获得更深的物理理解。单模态学不到这个。

### 从观察到交互
- Pre-training + mid-training = **观察**（背勇损失，反向传播）
- Post-training = **交互**（机器人在物理世界行动，产生数据反馈）
- 这是"关闭反馈回路"的关键——为什么物理世界可验证性推动最快进展

### Flux 的演化
- **Flux 1**（初代）：字面意义上"hands have 5 fingers"的基准超越
- 意外发现：用户大量用它做**character consistency**（训练 LoRA 实现人物一致性）
- **Flux 1 Context**（德语 "Kontext" 拼写）：专门的图像编辑模型，可以生成真正像你的"给我加小胡子"
- 6 周内 Context 收入翻倍
- Meta 宣布与 BFL 合作，为 20 亿用户驱动图像编辑

### 关键洞察：不要慌
OpenAI 发布 ChatGPT-1 image 时，BFL 在意大利 offsite。团队差点 panic。
- 好的 leader 不 panic
- 评估数据
- 往往直觉会告诉你还有未解决的问题
- 结果 60 天后 Context 发布，比 OpenAI 更好

### Self Flow（2026-03 发布）
- 解决 multimodal representation alignment 问题
- 以前的 representation alignment 只能在单模态（Dino-style）
- Self Flow 让视觉生成模型在多模态中自动对齐表征
- BFL 的朋友在所有 lab 都在打电话询问这篇论文

### 开源权重的商业逻辑
- 美学偏好因受众而异 → 无法中央化
- **open weights = 允许客户自定义** = 独特商业价值
- 每当"取决于受众"时 → 开源模型非常有价值
- Flux 三包：
  - **Flux Schnell**（德语"快"）：Apache 2.0 全开源，蒸馏到 4 步
  - **Flux Dev**：开源权重 + 商业许可
  - **Flux Pro**：API only
- **同样大小的模型，不同步数**（diffusion vs LLM 不同）
- 潜在对抗蒸馏（latent adversarial distillation）是关键解锁

### Diffusion vs Auto-regressive 取舍
- Diffusion：正交时间维度 → 数据效率低（每个样本可以在 continuous trajectory 上采样无数次）
- LLM：token by token → 数据效率高（所有 token 并行训练）
- Diffusion：**推理时可蒸馏到 1-2 步**（极大加速）
- LLM：推理时 token by token（无法简单跳过）
- 开放研究问题：结合两者优点？

### 3D 表征辩论
Blattmann 的立场：
> "I don't have an explicit 3D representation in my head."

人类学习：视频 + 音频 → 隐式 3D 理解。

Midha 反驳：**静态 3D 表征**（point clouds、meshes）对人机交互是"narrow, inflexible, static"，但对机器人室内定位（GPS denied）仍有用。

### 安全与治理
- EU AI Act 合规
- 内容过滤器 + 按需删除 personal data
- 对所有客户同等 guardrails（拒绝为大客户移除）
- 曾因此损失有意义的收入

## BFL 文化

- Freiburg（黑森林）总部
- 从零到 3+ 亿美元收入
- 整个公司历史**只有 1 人离职**
- "Disagree and commit"
- 25 人团队支撑 Meta 合作

## 关键引语

> "Language is not the be-all and end-all of intelligence. A three-year-old has more intelligence than any LLM, and they learn from video and audio first."

> "The frontier is persistent. Most teams give up right before they succeed."

> "Disagree and commit, then onwards."

## 相关页面
- [[andreas-blattmann]]
- [[visual-intelligence]]
- [[unified-models]]
- [[multimodal-ai]]
- [[open-weights-strategy]]
- [[distillation]]
- [[cascaded-vs-fused-architectures]]
