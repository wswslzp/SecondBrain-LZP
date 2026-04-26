---
title: "Memory Retrieval Pipeline — 记忆检索管线"
tags: [ai-memory, retrieval, rag, search]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[memory-system-architecture]]", "[[ai-memory-taxonomy]]", "[[hindsight]]"]
---

# Memory Retrieval Pipeline

AI 记忆系统从海量存储中精确定位相关信息的多阶段管线。

## 标准三阶段管线

```
Query → [语义预筛] → [上下文重排序] → [时间过滤] → Top-K Results
         Top-100        考虑当前上下文     优先最新
```

### Stage 1: 语义预筛 (Semantic Pre-filtering)
- 向量相似度匹配获取 Top-100 候选
- 使用 dense embeddings（如 OpenAI ada-002, sentence-transformers）
- **关键**：召回率 > 精确率，宁可多选

### Stage 2: 上下文重排序 (Contextual Reranking)
- 基于当前查询上下文重新排序
- Cross-encoder 或 LLM-based reranker
- 考虑对话历史、用户身份、任务类型

### Stage 3: 时间过滤 (Temporal Filtering)
- 优先返回最近的相关信息
- 时间衰减权重 + 硬性截止
- 处理信息过时/矛盾

## 高级检索策略

### 混合检索 (Hybrid Retrieval)
- **Dense Vector**：处理语义相似性
- **Sparse Keyword**：处理精确匹配
- **Multi-vector**：长文档分段独立索引

### 记忆路由 (Memory Routing)
- 根据查询类型自动选择检索源
- 个人记忆 vs 公共知识库 vs 工作记忆
- 减少不相关检索的噪声

### 记忆反思循环 (Memory Reflection Loop)
- 模型周期性"回顾"对话历史
- 生成高层摘要作为新的可检索记忆
- 类似人类的"复习巩固"

## 在 Hermes/Hindsight 中的实现

Hindsight 的检索管线：
1. **Semantic search** — 向量相似度
2. **Keyword matching** — 精确关键词
3. **Entity graph traversal** — 实体图遍历
4. **Reranking** — 综合排序

对应工具：
- `hindsight_recall(query)` — 标准检索
- `hindsight_reflect(query)` — 跨记忆推理合成

## 2026 前沿方法

- **MemCoT** — 记忆驱动思维链，将检索融入推理过程
- **CodaRAG** — 联想学习启发的连接性检索
- **SinkTrack** — Attention Sink 锚定上下文
- **MemReader** — 从被动提取到主动提取的长期记忆

## 评测指标

- **召回率** — 找到了多少相关记忆
- **精确率** — 返回的记忆有多少是相关的
- **延迟** — 检索速度
- **上下文利用率** — 检索到的记忆是否真的被有效使用

## References

- [[awesome-ai-memory]]
- [[memory-system-architecture]]
- [[hindsight]]
