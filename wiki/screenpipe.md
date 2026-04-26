---
title: "Screenpipe — 开源 Rewind"
tags: [screenpipe, screen-recording, ai-memory, multimodal-memory]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[multimodal-memory]]", "[[cognitive-atrophy]]"]
---

# Screenpipe

开源的屏幕+音频持续捕获系统，定位为 Rewind.ai / Microsoft Recall 的开源替代。

## 模态

- 屏幕截图（视觉/OCR）
- 系统音频
- 麦克风
- 键盘输入

## 架构

持续事件驱动的屏幕+音频捕获 → 本地存储 → AI 语义搜索：
- OCR + 无障碍树提取文本
- Whisper 语音转写
- 语义嵌入检索
- 插件系统（"Pipes"）+ MCP Server

## 资源消耗

- CPU: 5-10%
- RAM: 0.5-3GB
- 存储: ~5-10GB/月

## 链接

- GitHub: [screenpipe/screenpipe](https://github.com/screenpipe/screenpipe) ⭐18,400 | MIT

## Sources

- [[multimodal-memory-systems]]
