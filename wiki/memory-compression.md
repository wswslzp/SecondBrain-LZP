---
title: "Memory Compression — 记忆压缩技术"
tags: [ai-memory, compression, efficiency, llm-memory]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[memory-system-architecture]]", "[[ai-memory-taxonomy]]", "[[memory-forgetting]]"]
---

# Memory Compression

AI 记忆系统在有限资源下保留最大信息量的压缩策略。

## 四个层次

### 1. 内容级压缩 (Content-Level)
- 提取核心信息，丢弃冗余
- 对话摘要：10 轮对话 → 3 句话要点
- **实例**：Hermes 的 context compaction

### 2. 表示级压缩 (Representation-Level)
- 向量量化：降低 embedding 精度以节省空间
- 降维：PCA / 随机投影 减少向量维度
- 稀疏化：只保留显著维度

### 3. 组织级压缩 (Organization-Level)
- 聚类：将相似记忆合并为类别
- 层次结构：细节记忆 → 摘要 → 主题 → 概述
- 知识图谱：关系网络比平铺文本更紧凑

### 4. 知识蒸馏 (Knowledge Distillation)
- 将外部记忆中的高频知识"蒸馏"进模型参数
- 外部记忆 → 微调 → 参数记忆
- 平衡：可编辑性 ↔ 访问速度

## 压缩 vs 遗忘

| 维度 | 压缩 | 遗忘 |
|------|------|------|
| **信息保留** | 保留核心，丢弃形式 | 完全移除 |
| **可逆性** | 不可逆（有损） | 不可逆 |
| **动机** | 效率 | 效率 + 隐私 + 准确性 |
| **结果** | 更紧凑的记忆 | 更少的记忆 |

参见 [[memory-forgetting]] 了解遗忘机制。

## 2026 前沿

- **MemVR** — 基于向量检索的 KV Cache 压缩
- **ACRE** — 长记忆 Agent 的累积推理
- **SkillClaw** — 技能蒸馏进可复用工具

## References

- [[awesome-ai-memory]]
- [[memory-system-architecture]]
