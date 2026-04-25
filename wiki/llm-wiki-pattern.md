---
title: "LLM Wiki 模式"
tags: [ai, knowledge-management, obsidian, claude-code, productivity]
date_created: 2026-04-11
date_modified: 2026-04-19
related: ["[[andrej-karpathy]]", "[[ai-impact-on-industry]]", "[[claude-code]]", "[[context-management]]"]
---

# LLM Wiki 模式

由 [[andrej-karpathy]] 提出的个人知识库构建模式。核心思想：LLM 不只是查询工具，而是**持续构建和维护一个结构化的 Wiki**。

## 与传统 RAG 的区别

| | 传统 RAG | LLM Wiki |
|---|---------|----------|
| 知识检索 | 每次从零开始 | 已预编译 |
| 交叉引用 | 无 | 自动维护 |
| 矛盾检测 | 无 | 主动标记 |
| 知识积累 | 不积累 | 持续复利 |

## 三层架构
- **Raw Sources** — 不可变的原始资料
- **Wiki** — LLM 维护的 Markdown 页面
- **Schema** — 配置文件（如 CLAUDE.md）

## 三种操作
- **Ingest** — 摄入新资料，更新 10-15 个页面
- **Query** — 查询并综合回答，好的回答存回 wiki
- **Lint** — 健康检查（矛盾、孤立页面、过时内容）

## 核心洞察

> "人类放弃 wiki 是因为维护负担增长快于价值。LLM 不会厌倦，不会忘记更新交叉引用，一次可以修改 15 个文件。"

## 灵感来源

Vannevar Bush 1945 年提出的 Memex — 一个私人策展的知识存储，文档间的连接与文档本身同等重要。Bush 无法解决的部分是"谁来维护"。现在 LLM 解决了这个问题。

## 运行时

这套模式需要一个能跨多文件读写、维护 wikilinks 的 agent 化工具。参见 [[claude-code]]。它的健康运转依赖 [[context-management]]：
- Ingest 按"新任务 = 新 session"规则切分
- Lint 可委托给 subagent 并行扫描
- Query 用轻量 session，答完 clear

## 来源
- [[claude-obsidian-second-brain]]
- [[claude-code-session-management]]
