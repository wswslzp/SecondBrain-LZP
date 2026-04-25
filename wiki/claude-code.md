---
title: "Claude Code"
tags: [ai, claude-code, tool, anthropic, productivity]
date_created: 2026-04-19
date_modified: 2026-04-19
related: ["[[context-management]]", "[[context-rot]]", "[[llm-wiki-pattern]]", "[[vibe-coding]]"]
---

# Claude Code

Anthropic 官方的终端 CLI / IDE 扩展，把 Claude 模型接入**真实的文件系统、shell 和工具调用**，使其从"聊天机器人"变成**agentic coding agent**。

## 定位

Claude Code 是 [[llm-wiki-pattern]] 与 [[vibe-coding]] 的运行时：
- Karpathy 的"LLM 持续维护 Wiki"需要一个能读/写文件、跨多文件同步的 agent
- Naval 的"英语是新编程语言"需要一个能直接执行的接口

## 关键能力

- 1M token context window（Opus 4.7 1M）
- 文件读写、shell 执行、web 抓取、git 操作
- Subagents（委托到全新 context）
- Hooks（settings.json 中定义的自动化行为）
- Slash commands / skills（可复用的任务模板）
- MCP（Model Context Protocol）外部工具集成
- Session 管理：continue / rewind / clear / compact

## 会话管理原语

| 命令 | 作用 |
|------|------|
| `/rewind` 或 `esc esc` | 跳回历史某一点重 prompt |
| `/clear` | 开新 session |
| `/compact` | 摘要化历史并延续 |
| Subagents | 委托到干净 context |

详见 [[context-management]]。

## 与 [[context-feedback-loops]] 的关系

Anthropic 的 RL 飞轮示例（[[anjney-midha]] 在 CS 153）：
1. 训练代码模型 → 程序员用 Claude Code
2. 推理收入 → 下一轮 compute
3. **Claude Code 观察的 context**（monorepo、git history、文件系统、tool call 成功/失败）→ RL 改进

Claude Code 既是产品，也是 Anthropic 的 **context 采集前端**。

## 与 [[llm-wiki-pattern]] 的结合

- `raw/` 目录放原始资料
- Claude Code 跨 session ingest、建立 wikilinks
- 每个 ingest 可能触及 10-15 个页面——只有 agent 化工具能胜任
- Hooks 可定义 "每次 /clear 之前自动 lint index" 之类的自动化

## 相关来源
- [[claude-code-session-management]] — Thariq 讲 context/session 管理
- [[claude-obsidian-second-brain]] — @defileo 讲 Claude Code + Obsidian 搭建第二大脑
- [[a-motorcycle-for-the-mind]] — Naval 将 Claude Code 视为 vibe coding 的典型
