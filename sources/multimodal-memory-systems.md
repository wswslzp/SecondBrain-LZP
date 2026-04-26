---
title: "多模态记忆系统调研：AI 记忆系统超越纯文本的前沿"
author: "自研"
date_ingested: 2026-04-26
date_published: 2026-04-26
tags: [multimodal-memory, ai-memory, memory-systems, cognitive-science, memos, simplemem, screenpipe]
url: "local research"
type: research
---

## Summary

2025-2026年AI记忆系统正从纯文本/向量进化到原生支持图像、音频、视频等多模态。调研覆盖16个项目，按成熟度分为四层：原生多模态记忆系统（SimpleMem、MemOS、M3-Agent等）、屏幕/感知级记忆（Screenpipe、Rewind/Limitless）、具身Agent记忆（VideoAgent、CMMR-VLN）、基础研究（ImageBind、脑科学多感官整合）。

## Key Points

- **三大范式转变**：文本记忆→多模态记忆、被动存储→主动巩固、单Agent→记忆操作系统
- **MemOS（⭐8.7K）** 提出 MemCube 抽象，统一明文/激活/参数三种记忆形式，定位为记忆的"操作系统"
- **SimpleMem（⭐3.2K）** 实现真正多模态 SOTA，三阶段管线（压缩→合成→检索），LoCoMo F1 +411%
- **M3-Agent**（字节跳动，ICLR 2026）双进程设计处理视频/音频流，超过 GPT-4o +6.7-8.2%
- **Screenpipe（⭐18.4K）** 开源 Rewind 替代，持续捕获屏幕+音频+键盘
- **脑科学启示**：大脑通过 γ 振荡（>30Hz）绑定多感官记忆；反向有效性原则（最弱单模态信号→最强多感官增强）
- **认知萎缩风险**：AI 替你记住一切，海马体可能退化（类似 GPS 削弱空间导航能力）
- **对 Hermes 最可行路线**：短期用 MLLM 转文本存入 Hindsight（路线B），中期加嵌入+原始文件引用（路线A补充）

## Concepts

- [[multimodal-memory]]
- [[memos-memory-os]]
- [[simplemem]]
- [[screenpipe]]
- [[imagebind]]
- [[cognitive-atrophy]]
- [[cross-modal-binding]]
- [[human-memory-systems]]
- [[ai-agent-memory]]
