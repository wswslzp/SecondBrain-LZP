---
title: "Generative Agents"
type: concept
aliases:
  - Stanford Generative Agents
  - Smallville
created: 2026-04-26
---

## Overview

Generative Agents 是 Stanford 团队（Joon Sung Park et al.）于 2023 年提出的交互式 AI Agent 架构（UIST 2023, ⭐21.2K）。25 个 LLM 驱动的 Agent 在虚拟小镇"Smallville"中自主生活、社交、规划日程。

### 记忆架构

该工作是 LLM Agent 记忆管理的先驱，引入了"反思即巩固"模式：

- **Memory Stream**：追加写入所有观察（append-only）
- **Reflection**：定期从积累的记忆中综合高层洞察
- **日计划**：睡眠/觉醒周期中自然巩固
- **三维检索评分**：Recency × Importance × Relevance → 自然遗忘

### 影响

- 论文：[arXiv:2304.03442](https://arxiv.org/abs/2304.03442)
- 代码：[github.com/joonspk-research/generative_agents](https://github.com/joonspk-research/generative_agents) (⭐21.2K)
- 启发了后续大量 Agent 记忆系统的设计，包括 [[letta-sleep-time-compute]]、[[sleep-consolidated-memory]] 等

## Sources

- [[ai-sleep-memory-research-survey]]

## Related

- [[ai-agent-memory]]
- [[memory-retrieval-pipeline]]
- [[sleep-consolidated-memory]]
- [[memory-forgetting]]
