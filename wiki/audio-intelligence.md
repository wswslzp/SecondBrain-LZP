---
title: "Audio Intelligence"
tags: [ai, audio, speech, voice-agents, tts]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[mati-staniszewski]]", "[[cascaded-vs-fused-architectures]]", "[[multimodal-ai]]"]
---

# Audio Intelligence

音频/语音 AI 的前沿领域。[[mati-staniszewski]]（ElevenLabs）和 [[andreas-blattmann]] 的共同主题。

## 三个评估维度

ElevenLabs 的框架：
1. **质量/情感** — 自然语感、情绪控制
2. **可靠性** — 工具调用、认证、数据库操作
3. **延迟** — 实时对话体验（目标 ~300ms）

企业与消费场景的取舍：见 [[cascaded-vs-fused-architectures]]。

## 核心难题

### 情感理解（输入侧）
大多数 voice 模型**只转录文字**，扔掉情感/语调/口音信息。
- 即使 ChatGPT Advanced Voice 也不检测"愤怒 vs 悲伤"
- 关键瓶颈：缺少"peppy / sad / stressed"的训练数据

ElevenLabs 2026 年初的突破：
1. 花一年时间建标注 pipeline（peppy/sad/stressed 等）
2. 情感检测烤进 transcription
3. 传递到 LLM 作为 context
4. 合成时产生对应情绪

### 情感控制（输出侧）
以前：模型决定如何读文本（你只能重新生成）
现在（过去 6 个月）：可以导演——"用更戏剧化的方式重读，同时慢一些"

## 架构选择

### Cascaded（ElevenLabs 当前主流）
```
[Speech-to-Text + 情感检测]
    ↓
[LLM（工具调用）]
    ↓
[Text-to-Speech（情感合成）]
```

优势：可靠性、可追溯、可集成任何 LLM

### Fused（Sesame 方向）
单模型端到端

优势：延迟低、情感自然

## 模型演化时间线

- **2022**：第一代 TTS 自然度突破，用上下文感知预测情感音调
- **2023**：多语言 + 角色声音定制（voice marketplace）
- **2024**：AI localization 成熟（Javier Milei UN 演讲、Lex Fridman 对谈）
- **2025**：实时 voice agents（Deutsche Telekom、Revolut、Clara）
- **2026**：cascaded vs fused 混合部署、情感表达、设备端部署

## ElevenLabs 的规模

- 2022 年起步
- 2025 末：$330M ARR
- 2026 Q1 新增 $100M+ ARR
- 450 人，每团队 <10
- 收入按**部署**可预测（vs Anthropic 按 compute 可预测）

## 业务案例

### 恢复声音
- ~10,000 ALS、喉癌患者
- 合成他们失去的声音
- ElevenLabs 最自豪的工作之一

### 乌克兰 Diia
- 战争中政府服务数字化
- Voice 接口让没有网络的人能打电话
- 每个部委独立快速部署（绕过繁文缛节）

### 企业 Voice Agents
- 客户支持、销售、预订
- 场景需求：两因素认证、数据库查询、支付处理 → 必须 cascaded

## 反对语音认证

> "Voice authentication in banking is not the future. That's the wrong approach." — Mati Staniszewski

AI 合成声音太容易 → 语音不应是安全认证机制。

## 设备端部署

- 2026 年 ElevenLabs 首次在设备上跑模型
- 策略：**先质量，后小型化**
- 不做"低质量的设备端"妥协
- 设备端目前限语言和基础 TTS——interactivity 仍需云

## 与 BFL / Luma 的共性

- 都遵循 [[ai-factory]] 管线
- 都在探索 [[unified-models]] 方向
- 都遇到 [[cascaded-vs-fused-architectures]] 的取舍
- 都强调"围绕数据设计算法"

## 关键引语

> "For enterprises, reliability > latency. That's why cascaded will win for the next few years." — Staniszewski

> "Chat GPT Advanced Voice still doesn't understand if I'm angry or sad. If I said the same sentence in an angry way or sad way, it just transcribes it." — [[anjney-midha]]

## 来源
- [[cs153-elevenlabs-mati-staniszewski]]
- [[cs153-bfl-andreas-blattmann]]
