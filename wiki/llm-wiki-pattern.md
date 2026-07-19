---
title: "LLM Wiki 模式"
tags: [ai, knowledge-management, obsidian, claude-code, productivity]
date_created: 2026-04-11
date_modified: 2026-07-19
related: ["[[andrej-karpathy]]", "[[ai-impact-on-industry]]", "[[claude-code]]", "[[context-management]]", "[[garry-tan]]", "[[agentic-engineering-primitives]]", "[[company-brain]]"]
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

## 真实世界的延伸：GBrain 建在「知识 Wiki」之上（CS153）

一个可爱的自指链接：YC 的 [[garry-tan]] 把他的三层记忆系统 **GBrain 直接建在 [[andrej-karpathy]] 的「Knowledge Wiki」之上**——也就是本页所讲的 LLM-Wiki 模式。当纯 grep 检索「扛不住」时，他加上了**向量检索、RRF 融合、backlinks、一个带类型的图数据库，以及一层 epistemology 层**（区分 hunches / beliefs-by-person / world-knowledge），并朝着**动态本体（dynamic ontology，每个用户一套 schema）**演进。这是本仓库所运行模式的一个真实世界扩展。详见 [[agentic-engineering-primitives]]、[[company-brain]]。

## 来源
- [[claude-obsidian-second-brain]]
- [[claude-code-session-management]]
