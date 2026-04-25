---
title: "Hindsight"
tags: [tools, memory, ai-agents, context-management]
date_created: 2026-04-20
date_modified: 2026-04-20
related: ["[[hermes-agent]]", "[[context-feedback-loops]]"]
---

# Hindsight

External memory provider for AI agents.

## Why Hindsight?

根据 [[0xjeff|0xJeff]] 的推荐：

> I use Hindsight because it **consistently ranks #1 for recall accuracy**, especially on long-horizon, multi-session, and large-scale memory tasks.

## Use Case: Reflect

在 [[hermes-agent]] 中，Hindsight 支撑 "Reflect" 功能：

- 综合历史信息
- 检测用户偏好
- 连接关系网络
- 识别模式
- 产出 actionable analysis（如 Top 5 Daily Insights）

## ⚠️ Cost Warning

> Don't link Hindsight to Openrouter, I did this and connected it to Claude Sonnet 4.6. It burned through **$50+ worth of tokens in a day**. RIP

Hindsight 的 recall 能力强大，但与昂贵模型组合时 token 消耗惊人。建议：

- 使用开源模型或更便宜的推理服务
- 监控 token 使用量
- 设置每日消耗上限

## Key Strength

- Long-horizon memory（跨越长时间段）
- Multi-session recall（跨会话检索）
- Large-scale memory tasks（大规模知识库）

## References

- [[3-highly-useful-hermes-skills]] — 0xJeff 的使用经验
