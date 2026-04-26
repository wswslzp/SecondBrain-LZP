---
title: "Letta Sleep-Time Compute"
type: concept
aliases:
  - Sleep-Time Compute
  - MemGPT Sleep
created: 2026-04-26
---

## Overview

Letta Sleep-Time Compute 是由 UC Berkeley MemGPT 团队开发的双 Agent 异步记忆整合框架。核心思想是用"空闲时间计算"替代"推理时间计算"——不是在回答问题时消耗更多 token 来思考，而是在没有对话时预先消化和整理知识。

### 架构

- **Primary Agent**：处理用户对话，不能修改自己的核心记忆
- **Sleep-Time Agent**：在空闲期异步运行，重写/整合两个 Agent 的记忆块
- 模型无关：sleep agent 可以使用与 primary agent 不同的模型

### 技术细节

- 论文：[arXiv:2504.13171](https://arxiv.org/abs/2504.13171)
- 代码：[github.com/letta-ai/sleep-time-compute](https://github.com/letta-ai/sleep-time-compute) (MIT, ⭐130)
- 主框架：[github.com/letta-ai/letta](https://github.com/letta-ai/letta) (⭐21.7K)
- 首发于 Letta 0.7.0

### 与 Hermes 的关系

Hermes 的 [[hermes-sleep-implementation-plan]] 借鉴了 Letta 的双 Agent 思路，但采用更轻量的 Cron Job + Skill 方案实现，无需 fork 源码。

## Sources

- [[ai-sleep-memory-research-survey]]
- [[scm-sleep-consolidated-memory]]

## Related

- [[sleep-consolidated-memory]]
- [[memory-consolidation]]
- [[ai-agent-memory]]
- [[complementary-learning-systems]]
