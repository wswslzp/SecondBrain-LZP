---
title: "Unified Models（统一多模态模型）"
tags: [ai, multimodal, architecture]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[amit-jain]]", "[[andreas-blattmann]]", "[[multimodal-ai]]", "[[cascaded-vs-fused-architectures]]"]
---

# Unified Models

**一个 transformer backbone，所有模态编码到同一个空间，在同一个模型中推理。**

2026 年前沿 AI 的关键架构方向，[[amit-jain]]（Luma）和 [[andreas-blattmann]]（BFL）的观点高度一致。

## 定义与对比

### 什么不是 unified

**"VLM"（Vision Language Model）**
- 能理解图像，但不能生成图像
- 理解与生成割裂

**Nano Banana 模式**
- 大 diffusion tower 生成图像
- 大 language tower 生成文本
- 中间用 thin bridge（700-800M 参数 VAE）通信
- Generate enhanced prompt（EP）→ 传给 image model
- "few-shot architecture"——仍是两座塔

### 什么是 unified

> "Just like the human brain. Different areas for processing visual/auditory, but those are just encoders. All information goes into the neocortex where reasoning and judgment happen in one place." — Amit Jain

架构：
```
[文本编码器] ─┐
[图像编码器] ─┼─→ [同一个 transformer backbone] ─→ 输出（任何模态）
[视频编码器] ─┤
[音频编码器] ─┘
```

Transformer 对信息类型不敏感——关键是前/后的编码器/解码器。

## 为什么需要

### 1. 像素也是智能的载体
> "Just like language models produce words, image models produce pixels. How you arrange them determines intelligence."

一张"因果正确"的示意图承载的智能不亚于一段文字。

### 2. End-to-end 工作需要所有模态
用户想要的不是"一张图"——是"做一个营销活动""拍一个电影镜头""规划一个机器人动作"。

这些任务必须跨模态推理。

### 3. 跨模态相关性的学习价值
两个刚体碰撞 → 声音+视觉+动作的关联。单模态无法学到这个物理理解。

## 关键 ingredient

### 不同模态的编码特性
- **离散**最好编码：文本
- **连续**最好编码：图像、音频
- **介于之间**：视频

Unified 架构能同时处理。

### Self Flow（BFL, 2026-03）
解决多模态 representation alignment——以前的 alignment 技术（如 Dino）只适用于单模态。self-flow 让跨模态自动对齐。

## End-to-End 工作架构

从 Luma 的实例（见 [[ai-factory]]）：

```
[Skills 层]     ← 领域专家的知识（50 页"如何做好幻灯片"）
     ↓
[Unified Model] ← orchestrator，决定用哪些 skill/tool
     ↓
[Tool Harness]  ← Linux、API、代码执行
```

## 与 cascaded 的取舍

见 [[cascaded-vs-fused-architectures]]。Unified ≈ fused。
- Fused：延迟优势、端到端学习
- Cascaded：可追溯性、可靠性、模块化

[[mati-staniszewski]]（ElevenLabs）认为企业场景 cascaded 胜，消费场景 fused 胜，未来混合。

## 训练成本

按 [[amit-jain]]：
- 多模态 Luma 当前规模：~100K H100/GB300，30PB 可训练数据
- "严格是 LLM 的超集"
- 长期 compute 需求 > LLM（因为数据更多）
- 当前 $1B 做 LLM lab $5-10B 做的事

## 关键引语

> "If you want to solve world understanding and 'world models,' you need a backbone that understands language and generates pixels all in one go. No delta in between." — Amit Jain

> "We want to be using this generality of the representation, but we actually want to be using it for things. So we add additional context and importantly actions." — Andreas Blattmann

## 来源
- [[cs153-luma-amit-jain]]
- [[cs153-bfl-andreas-blattmann]]
