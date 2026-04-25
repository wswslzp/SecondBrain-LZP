---
title: "AI Agent Memory Architecture"
tags: [ai-agents, memory, cognitive-science, hermes]
date_created: 2026-04-25
date_modified: 2026-04-25
related: ["[[human-memory-systems]]", "[[working-memory]]", "[[forgetting-mechanisms]]", "[[memory-consolidation]]", "[[hermes-agent]]"]
---

# AI Agent Memory Architecture

AI Agent 记忆系统与人类认知记忆的对比分析，以及改进方向。

## 当前 Hermes 记忆映射

| 人类记忆 | Hermes 组件 | 匹配度 |
|---|---|---|
| 工作记忆 | 上下文窗口 | ⭐⭐⭐ |
| 语义记忆 | Memory + Hindsight | ⭐⭐⭐ |
| 情景记忆 | Session History | ⭐⭐⭐ |
| 程序记忆 | Skills | ⭐⭐⭐⭐ |
| 前瞻记忆 | Cron Jobs | ⭐⭐ |
| 感觉记忆 | ❌ | — |
| 遗忘机制 | ❌ | — |
| 自动巩固 | ❌ | — |
| 情绪加权 | ❌ | — |
| 元记忆 | ❌ | — |

## 核心差距

1. **无遗忘** — 所有记忆权重相同，Memory 空间满溢
2. **无自动巩固** — 不会在"空闲期"提炼短期经历为长期知识
3. **无情绪/重要性加权** — 缺少内在的"这件事重要"信号
4. **无再巩固** — 回忆不会修改已存储的记忆

## 相关项目

- **MemGPT/Letta** — LLM Agent 分层记忆管理
- **OpenChronicle** — 开源屏幕观察 + 记忆层，MCP 接口
- **SOAR / ACT-R** — 经典认知架构的记忆子系统

## 改进路线图

| 机制 | 方案 | 难度 |
|---|---|---|
| [[forgetting-mechanisms]] | 时间戳+访问计数，低频降权 | ⭐⭐ |
| [[memory-consolidation]] | 定时后台任务提炼高频模式 | ⭐⭐⭐ |
| 再巩固 | 访问时检查准确性并更新 | ⭐⭐ |
| 情绪加权 | 用户纠正/重复提及赋予更高权重 | ⭐⭐ |
| 元记忆 | 标注置信度，提示确认不确定项 | ⭐⭐⭐ |

## References

- [[human-memory-cognitive-science]]
- [[hermes-agent]]
