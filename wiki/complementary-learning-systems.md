---
title: "Complementary Learning Systems (CLS)"
tags: [neuroscience, memory, learning-theory, ai-memory]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[memory-consolidation]]", "[[sleep-consolidated-memory]]", "[[ai-agent-memory]]", "[[working-memory]]"]
---

# Complementary Learning Systems (CLS)

McClelland, McNaughton & O'Reilly (1995) 提出的**双系统记忆理论**，是 SCM 和众多 AI 记忆架构的理论基础。

## 核心理论

大脑使用**两个互补的学习系统**：

| 系统 | 脑区 | 特点 | 类比 |
|---|---|---|---|
| **快速学习系统** | 海马体 (Hippocampus) | 快速编码单次经历，模式分离 | 工作记忆 / RAM |
| **慢速学习系统** | 新皮层 (Neocortex) | 缓慢提取统计规律，泛化能力强 | 长期记忆 / 硬盘 |

**关键洞察**：如果只有一个系统，新学习会**灾难性覆盖**旧知识（灾难性遗忘）。两个系统互补才能同时做到快速学习和稳定存储。

## 睡眠的桥梁作用

睡眠是两个系统之间的**信息传递窗口**：
1. **NREM 慢波睡眠**：海马体向新皮层"教学"——重播白天经历
2. **REM 快速眼动**：新皮层内部整合——建立跨概念联想
3. **突触下调**：防止新皮层饱和——类似正则化

## 在 AI 中的实现

### SCM (2026)
[[sleep-consolidated-memory]] 最完整地实现了 CLS：
- WorkingMemory = 海马体（快速，7 项限制）
- LongTermMemory = 新皮层（慢速，图结构）
- SleepCycle = 睡眠桥梁（NREM 巩固 + REM 做梦 + 遗忘）

### 其他实现
- **MemGPT/Letta** — 分层存储但无睡眠机制
- **EWC** — 参数级别的灾难性遗忘解决方案
- **WSCL** — Weight-Space Consolidation with sleep-like mechanisms

## 对 AI Agent 的启示

CLS 理论暗示 AI Agent 需要：
1. 一个**快速但不稳定**的编码层（类似 context window）
2. 一个**慢速但稳定**的存储层（类似 vector DB / knowledge graph）
3. 一个**离线整合过程**把 1 的内容迁移到 2（类似"睡眠"）

目前大多数 AI Agent 缺少第 3 点。

## References

- McClelland, J.L., McNaughton, B.L., & O'Reilly, R.C. (1995). "Why there are complementary learning systems in the hippocampus and neocortex"
- [[sleep-consolidated-memory]]
- [[memory-consolidation]]
- [[ai-agent-memory]]
