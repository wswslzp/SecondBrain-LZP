---
title: "多模态记忆 (Multimodal Memory)"
tags: [multimodal-memory, ai-memory, cognitive-science]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[human-memory-systems]]", "[[ai-agent-memory]]", "[[cross-modal-binding]]", "[[memos-memory-os]]"]
---

# 多模态记忆 (Multimodal Memory)

AI Agent 记忆系统从纯文本/向量检索进化到原生支持图像、音频、视频等多模态信息的存储与检索。

## 概述

传统 AI 记忆（如 Mem0、Zep）以文本为核心——即使处理图片也先转成文字描述。2025-2026年出现的多模态记忆系统直接在嵌入空间中存储和检索多种模态，保留了文本转写无法捕获的信息（颜色、语调、空间关系等）。

## 三大范式转变

1. **文本记忆 → 多模态记忆**：从只记对话文本，到能记住图像、音频、视频
2. **被动存储 → 主动巩固**：从简单 RAG 检索，到有遗忘和巩固机制
3. **单 Agent → 记忆操作系统**：从单一记忆工具，到统一的记忆管理层

## 四种技术路线

| 路线 | 代表 | 优势 | 劣势 |
|---|---|---|---|
| **A. 嵌入统一** | ImageBind | 跨模态检索天然支持 | 存储成本大，解释性差 |
| **B. 转写归一** | MemVerse | 复用现有文本基础设施 | 信息损失 |
| **C. MemCube 多形态** | MemOS | 每种模态原生表示 | 架构复杂 |
| **D. 持续捕获** | Screenpipe | 零遗漏 | 隐私、存储、噪声 |

## 脑科学基础

人脑的多感官记忆不是分开存的——走进森林记住的是"在森林里"的统一体验，而非三个独立的视觉/听觉/嗅觉条目。[[cross-modal-binding]] 通过 γ 振荡实现。

## 代表项目

| 项目 | Star | 模态 | 亮点 |
|---|---|---|---|
| [[memos-memory-os]] | 8.7K | 文本+图像+工具+人设 | MemCube 抽象，记忆操作系统 |
| [[simplemem]] | 3.2K | 文本+图像+音频+视频 | 多模态 SOTA，pip 可装 |
| M3-Agent | 1.3K | 视频+音频+文本 | ICLR 2026，字节跳动 |
| [[screenpipe]] | 18.4K | 屏幕+音频+键盘 | 开源 Rewind 替代 |

## Sources

- [[multimodal-memory-systems]]
- [[human-memory-cognitive-science]]
