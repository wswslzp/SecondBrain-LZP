---
title: "MemOS — 记忆操作系统"
tags: [memos, memory-os, ai-memory, multimodal-memory]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[multimodal-memory]]", "[[ai-agent-memory]]", "[[simplemem]]"]
---

# MemOS — 记忆操作系统

MemOS 将 AI 记忆从"工具"提升为"操作系统"层级的抽象，类似 Linux 之于进程管理。

## 核心概念：MemCube

MemCube 是 MemOS 的核心抽象，统一三种记忆形式：
- **明文记忆 (Plaintext)**：可读的文本/结构化数据
- **激活记忆 (Activation-based)**：模型内部的激活状态
- **参数记忆 (Parameter-level)**：嵌入在模型权重中的知识

记忆可**组合、迁移、融合**——不同 Agent 的记忆可以合并，记忆可以从一个模型迁移到另一个。

## 技术栈

- 后端：Neo4j（图数据库）+ Qdrant（向量数据库）
- 模态：文本 + 图像 + 工具痕迹 + 人设

## 性能

- 准确率比 OpenAI Memory +43.70%
- Token 节省 35.24%
- ⭐ 8,700 | Apache-2.0

## 论文

- arXiv:2507.03724 (2025-07)
- GitHub: [MemTensor/MemOS](https://github.com/MemTensor/MemOS)

## Sources

- [[multimodal-memory-systems]]
