---
title: "Memory System Architecture — 记忆系统四层架构"
tags: [ai-memory, architecture, system-design, llm-memory]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[ai-memory-taxonomy]]", "[[memory-retrieval-pipeline]]", "[[memory-compression]]", "[[memory-forgetting]]", "[[ai-memory-open-source-landscape]]"]
---

# Memory System Architecture

AI/LLM 记忆系统的完整技术栈，包含四个核心层次。

## 四层架构

```
┌─────────────────────────────────────┐
│       Memory Control Layer          │  优先级管理、遗忘控制、一致性协调
├─────────────────────────────────────┤
│       Memory Retrieval Layer        │  多阶段检索、重排序、上下文注入
├─────────────────────────────────────┤
│       Memory Processing Layer       │  Embedding、摘要生成、记忆分段
├─────────────────────────────────────┤
│       Memory Storage Layer          │  向量数据库、图数据库、混合存储
└─────────────────────────────────────┘
```

### 1. 存储层 (Storage Layer)
- **向量数据库**：Chroma、Weaviate、Pinecone、Milvus
- **图数据库**：Neo4j、用于关系型记忆
- **混合存储**：向量 + 结构化 + 图的组合

### 2. 处理层 (Processing Layer)
- **Embedding 模型**：将文本/多模态内容转为向量表示
- **摘要生成器**：压缩长对话为结构化记忆
- **记忆分段器**：将长文档切分为独立可索引的片段

### 3. 检索层 (Retrieval Layer)
- **多阶段检索器**：粗筛 → 精排的级联管线（见 [[memory-retrieval-pipeline]]）
- **重排序模块**：基于当前上下文重新排序候选记忆
- **上下文注入器**：将检索到的记忆格式化后注入 prompt

### 4. 控制层 (Control Layer)
- **优先级管理**：记忆权重分配
- **遗忘控制**：实现各种 [[memory-forgetting]] 策略
- **一致性协调**：解决矛盾信息（时间戳优先、来源可信度加权）

## 五种原子操作

| 操作 | 描述 | 典型实现 |
|------|------|---------|
| **写入** (Write) | 对话 → 向量存储 | 结合摘要减少噪声 |
| **检索** (Retrieve) | 基于当前上下文获取 Top-K | 语义 + 关键词混合检索 |
| **更新** (Update) | 相似度匹配后替换/增强 | 向量相似度 → 合并 |
| **删除** (Delete) | 用户指令或自动策略 | 隐私过期、PII 清理 |
| **压缩** (Compress) | 合并相关记忆为摘要 | 见 [[memory-compression]] |

## 记忆管理 (Memory Management)

- **生命周期管理**：创建 → 活跃使用 → 低频访问 → 归档/删除
- **冲突解决**：时间戳优先、来源可信度加权
- **资源预算**：为不同用户/任务分配记忆配额
- **安全治理**：自动检测和脱敏 PII（个人身份信息）

## 在 Hermes 中的映射

| 架构层 | Hermes 组件 |
|--------|-----------|
| 存储层 | Hindsight（向量 + 实体图）、Memory（键值对） |
| 处理层 | 对话内容自动提取、Hindsight retain |
| 检索层 | Hindsight recall/reflect、Memory 注入 |
| 控制层 | Memory 2200 字符上限（被动遗忘）、手动管理 |

## References

- [[awesome-ai-memory]]
- [[ai-agent-memory]]
