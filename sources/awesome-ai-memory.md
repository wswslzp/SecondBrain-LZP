---
title: "Awesome-AI-Memory: 学术界 AI 记忆研究全景索引"
author: "[[iaar-shanghai]]"
date: 2026-04-26
url: "https://github.com/IAAR-Shanghai/Awesome-AI-Memory"
type: repository
tags:
  - ai-memory
  - llm-memory
  - agent-memory
  - survey
  - benchmark
  - open-source
---

## Summary

IAAR-Shanghai 维护的 AI 记忆研究领域最全面的 curated 知识库，收录 **349 篇论文**和 **97 个开源项目**。系统覆盖长期记忆、检索增强、记忆原生系统设计、评测基准与实际应用。2026 年至今已收录 180 篇新论文，是当前最活跃的 AI 记忆研究索引。

## Key Points

- **四大论文分类**：Survey（8）、Framework & Methods（242）、Datasets & Benchmark（53）、Systems & Models（38）
- **记忆系统四层架构**：存储层 → 处理层 → 检索层 → 控制层，是当前学术界对 AI 记忆系统的标准分层方式
- **五种原子操作**：写入、检索、更新、删除、压缩——涵盖了记忆系统的完整生命周期
- **记忆四维分类**：按频率、结构化程度、共享范围、时效性——与认知科学的分类形成对照
- **遗忘机制四类**：选择性遗忘（Machine Unlearning）、隐私驱动、记忆衰减、冲突驱动
- **43 个开源系统**时间线横跨 2023-2026，从 Zep/Letta 到 MemOS/Hindsight/SkillClaw
- **关键发现**：100k context 下，外部记忆系统在约 10 轮对话后成本效率超过长上下文模型
- **研究热点**：长期记忆（90 篇）> 记忆框架（53）> 基准测试（43）> 模型架构（42）> 记忆检索（40）

## Key Survey Insights

1. **外化理论** — 记忆外化跨时态状态，技能外化程序能力，协议外化交互结构
2. **模块化记忆** — 整合 in-context learning 与权重更新的模块化架构是持续学习的关键
3. **人类策略涌现** — LLM 中已确认存在类人的语义记忆搜索策略
4. **个性化路线** — 用户画像建模 → 记忆 → 规划 → 行动执行的四组件分类
5. **三维分类法** — 按对象、形式、时间的记忆分类体系

## Notable 2026 Methods

- **MemCoT** — 记忆驱动的思维链，测试时扩展
- **ClawVM** — 虚拟内存管理用于有状态工具调用 Agent
- **FadeMem** — 生物启发的遗忘机制
- **ShardMemo** — MoE 路由的分片 Agent 记忆
- **OBLIVION** — 衰减驱动的自适应记忆控制
- **ParamMem** — 参数化反思记忆增强语言 Agent
- **MemPO** — 自记忆策略优化用于长 horizon Agent

## Concepts

- [[ai-memory-taxonomy]]
- [[memory-system-architecture]]
- [[memory-forgetting]]
- [[memory-retrieval-pipeline]]
- [[memory-compression]]
- [[ai-agent-memory]]
- [[multimodal-memory]]
- [[ai-memory-benchmarks]]
- [[ai-memory-open-source-landscape]]
