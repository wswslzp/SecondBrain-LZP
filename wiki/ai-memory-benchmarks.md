---
title: "AI Memory Benchmarks — 记忆评测基准"
tags: [ai-memory, benchmark, evaluation, llm-memory]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[ai-memory-taxonomy]]", "[[memory-retrieval-pipeline]]", "[[ai-memory-open-source-landscape]]"]
---

# AI Memory Benchmarks

AI/LLM 记忆系统的评测方法和基准数据集。该领域 2026 年爆发式增长，53 篇 benchmark 论文。

## 评测维度

### 1. 记忆准确性 (Memory Accuracy)
- 存储的信息是否正确反映了原始内容
- 更新后的信息是否一致
- **挑战**：幻觉 vs 真实记忆

### 2. 检索效果 (Retrieval Effectiveness)
- 召回率：找到了多少相关记忆
- 精确率：返回的有多少是相关的
- 延迟：检索速度

### 3. 个性化能力 (Personalization)
- 用户偏好记忆的准确度
- 跨会话一致性
- 个性化响应质量

### 4. 长期保持 (Long-Term Retention)
- 跨多天/多会话的记忆持久性
- 信息衰减率
- 记忆容量上限

### 5. 遗忘能力 (Forgetting Capability)
- Machine Unlearning 的完整性
- 遗忘后是否影响相关知识
- 隐私合规性验证

## 代表性 Benchmarks

| Benchmark | 年份 | 评测重点 |
|-----------|------|---------|
| LoCoMo | 2024 | 长对话记忆（跨5+会话） |
| LOCOBENCH | 2025 | 长上下文推理 |
| MemBench | 2025 | 多维度记忆评估 |
| AgentMemBench | 2026 | 完整 Agent 记忆生命周期 |
| PersonalBench | 2026 | 个性化记忆准确性 |
| ForgetBench | 2026 | 遗忘效果 & 知识保持 |
| MemForge | 2026 | 多用户记忆注入安全性 |
| MemoryScope | 2026 | 多粒度记忆管理 |

## 关键发现

1. **100k 上下文拐点** — 外部记忆系统在约 10 轮对话后成本效率超过长上下文模型
2. **个性化与准确性的 trade-off** — 过度个性化导致确认偏误
3. **遗忘不完整** — 多数系统表面删除但残余信息仍可通过间接方式检索
4. **多 Agent 记忆共享** — 缺乏标准化协议，各系统不兼容

## References

- [[awesome-ai-memory]]
- [[memory-retrieval-pipeline]]
