---
title: "SimpleMem — 多模态记忆 SOTA"
tags: [simplemem, multimodal-memory, ai-memory]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[multimodal-memory]]", "[[memos-memory-os]]", "[[ai-agent-memory]]"]
---

# SimpleMem / Omni-SimpleMem

真正的多模态记忆 SOTA，支持文本+图像+音频+视频的统一存储和检索。

## 三阶段管线

1. **Semantic Structured Compression** — 将交互蒸馏为紧凑索引单元
2. **Online Semantic Synthesis** — 写入时实时巩固
3. **Intent-Aware Retrieval Planning** — LLM 驱动的三层索引检索（dense向量 + BM25稀疏 + 符号元数据）

## Omni 扩展

- 熵驱动的选择性摄入（类似人脑注意力过滤）
- FAISS+BM25 金字塔渐进检索
- 知识图谱增强跨模态推理

## 性能

| 基准 | 得分 | 提升 |
|---|---|---|
| LoCoMo F1 | 0.613 | +411% |
| Mem-Gallery F1 | 0.810 | +214% |
| 检索速度 | 3.5× | - |

## 使用

```bash
pip install simplemem
```
支持 Claude / Cursor / LM Studio

## 论文与代码

- arXiv:2604.01007 (2026-04)
- GitHub: [aiming-lab/SimpleMem](https://github.com/aiming-lab/SimpleMem) ⭐3,200 | MIT

## Sources

- [[multimodal-memory-systems]]
