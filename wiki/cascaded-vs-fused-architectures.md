---
title: "Cascaded vs Fused 架构"
tags: [ai, architecture, multimodal, audio, video]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[unified-models]]", "[[audio-intelligence]]", "[[mati-staniszewski]]"]
---

# Cascaded vs Fused 架构

2026 年前沿 AI 系统的核心架构辩论。贯穿 [[audio-intelligence]]（ElevenLabs）、[[visual-intelligence]]（BFL）、[[multimodal-ai]]（Luma）。

## 定义

### Cascaded（级联）
```
[Modal A 模型] → [中间表示（通常是文本）] → [Modal B 模型]
```

例子（ElevenLabs voice agent）：
```
[Speech-to-Text + 情感检测]
    ↓
[LLM（推理 + 工具调用）]
    ↓
[Text-to-Speech（情感生成）]
```

### Fused（融合）
单个 unified 模型端到端处理所有模态（[[unified-models]]）。

```
[Audio 输入] → [Unified Model] → [Audio 输出]
```

## 三维评估

[[mati-staniszewski]] 的框架：

| 维度 | Cascaded | Fused |
|------|----------|-------|
| 情感/质量 | 可修复（ElevenLabs 新版） | 已有（Sesame CSM） |
| **可靠性** | **胜** | 劣 |
| **延迟** | 劣 | **胜**（~300ms） |

## 什么时候选哪个

### Cascaded 胜（企业场景）
预订机票的 voice agent 需要：
1. 双因素认证
2. 从数据库拉取信息
3. 处理支付
4. **每步可追踪**——"哪个模型哪步出错？"

> "For enterprises, reliability > latency. That's why cascaded will win for the next few years." — Staniszewski

### Fused 胜（消费/companion 场景）
- 快速响应（~300ms）
- 情感自然流动
- 不需要可靠工具调用
- 例子：companion apps

### 混合（未来）
同一个客户内切换：
- 浏览产品时用 fused（低延迟）
- 到认证/支付步骤切换到 cascaded（可靠）

## 训练取舍

### Cascaded
- 可独立训练各模型
- 需要额外时间让它们协作
- 情感传递必须在训练前**烤进 pipeline**（transcription 阶段检测情感 → 作为 LLM 的 context → 合成情感语音）

### Fused
- Emergent behavior（涌现行为）
- 依赖一个好的开源 LLM backbone
- **融合文本 token 与音频 token 极难**——大多数人搞不定这步
- 即使解决了，仍依赖落后的开源模型

## 跨模态的体现

### BFL（视觉）
- Flux 1 = 单模态（text-to-image）
- Flux Context = 仍本质单模态
- 未来 = unified multimodal with self-flow alignment
- 机器人的 post-training：模型产生动作 → 物理世界反馈 → 数据回流

### Luma（视觉 + 多模态）
- 2025 年架构：多个"tower"（language/image/video/audio）+ fusion
- **不够**，无法做长对话、长故事
- 2026 年转向单一 backbone 的 unified model

### ElevenLabs（音频）
- 2022-24 都在 cascaded
- 2025 年情感 pipeline 烤进 cascaded
- 2026 年探索 fused——特别是 companion 场景

## 关键引语

> "Cascaded architecture is right for the next few years for enterprises. Fused will win where reliability isn't essential but speed is." — Mati Staniszewski

> "Unified models can actually work because transformers don't care what kind of information you're passing through them. It's the encoders and decoders where things fall apart." — Amit Jain

## 来源
- [[cs153-elevenlabs-mati-staniszewski]]
- [[cs153-luma-amit-jain]]
- [[cs153-bfl-andreas-blattmann]]
