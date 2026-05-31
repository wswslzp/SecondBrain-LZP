---
title: "Multimodal AI（多模态 AI）"
tags: [ai, multimodal, architecture, foundation-models]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[unified-models]]", "[[visual-intelligence]]", "[[audio-intelligence]]"]
---

# Multimodal AI

跨多种自然表征（文本、图像、视频、音频、动作）的 AI——2026 年前沿 AI 的主流方向。

## 自然 vs 非自然表征（Blattmann 框架）

- **自然**：图像、视频、音频——太阳光、声波等人类无法控制的电磁/机械源
- **非自然**：文本——进化压缩的人造通信编码

文本信息密度高但狭窄。自然信号冗余但包含物理世界的全部。

## 人类学习顺序

> "First three to five years you observe with audio and video. Then you learn to read." — Blattmann

3 岁孩子的智能超过任何 LLM——因为他们从自然表征起步。

**策略结论**：从自然表征起步构建模型，文本只是高阶推理的后续，不是起点。

## 多模态的价值来源

### 1. 跨模态相关性
刚体碰撞 → 声音 + 视觉 + 力的时空关联。单模态学不到物理理解。

### 2. 行动空间统一
机器人、computer use、创意工具都需要同一种理解。

### 3. End-to-end 工作
真正的商业任务（做一个广告、写一部小说、规划一个动作）跨越多个模态。

## 两种实现路径

### Unified（一个 backbone）
见 [[unified-models]]。[[amit-jain]] 和 [[andreas-blattmann]] 的押注。

### Cascaded（专家模型级联）
见 [[cascaded-vs-fused-architectures]]。企业场景的当前主流。

## 当前 state of the art

### 视觉
- **BFL**：Flux 系列 + Self Flow（跨模态 representation alignment）
- **Luma**：Dream Machine → Unified Model（混合 auto-regressive + diffusion）
- **Google**：Gemini（仍多塔 + thin bridge，按 [[amit-jain]] 判断）

### 音频
- **ElevenLabs**：cascaded 企业产品 + 探索 fused
- **Sesame**：开源 CSM，fused 方向
- **OpenAI Advanced Voice**：不检测情感输入（暴露 cascaded 的不足）

### 物理智能（仍在起步）
- Robotics（没有"行动数据的互联网"）
- Computer use
- [[amit-jain]] 的客户案例：能源电网诊断、材料科学

## 数据规模问题

"围绕数据设计算法，而不是反过来"：
- 3D：数据永远不够（Luma 的早期教训）
- 视频：比图像三维（空间 × 空间 × 时间），适合学世界模型
- 机器人：需要真实世界交互产生新数据

## 多模态会超过 LLM 吗

[[amit-jain]]：**会**
- 严格是 LLM 的超集
- 长期 compute 需求 > LLM
- 学科视角更广（能源电网、材料、studio 物理）

## 关键引语

> "You need to think from first principles how humans do it. Learning on natural representations by first observing and second interacting." — Blattmann

> "Multimodal models will far surpass language systems just because of the access to more data." — Amit Jain

## 来源
- [[cs153-luma-amit-jain]]
- [[cs153-bfl-andreas-blattmann]]
- [[cs153-elevenlabs-mati-staniszewski]]

## Omni 推理系统

[[sglang-omni-llm-inference]] 提供了一个系统设计视角：多模态/Omni 的关键边界不一定是“支持哪些模态”，而是 decode 是否变成 [[multi-stage-decode]]。当语音输出引入 Talker、MTP、Vocoder 等异构 stage，推理系统必须重新设计调度、通信与显存预算。

## 来源补充
- [[sglang-omni-llm-inference]]
