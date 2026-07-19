---
title: "Claude Code"
tags: [ai, claude-code, tool, anthropic, productivity]
date_created: 2026-04-19
date_modified: 2026-07-19
related: ["[[context-management]]", "[[context-rot]]", "[[llm-wiki-pattern]]", "[[vibe-coding]]", "[[anthropic]]", "[[claude-constitution]]", "[[headless-agent-pattern]]", "[[garry-tan]]", "[[ai-native-company]]", "[[agentic-engineering-primitives]]"]
---

# Claude Code

[[anthropic|Anthropic]] 官方的终端 CLI / IDE 扩展，把 Claude 模型接入**真实的文件系统、shell 和工具调用**，使其从"聊天机器人"变成**agentic coding agent**。据 Anthropic 说法，Claude Code（连同 Claude Cowork）自动化了大部分软件工程，是公司近期增长与「SaaSpocalypse」的关键推手（背后工程师 Boris Cherny）。

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

## 作为通用 agent 的两条使用路线（立党）

[[lidang|立党]] 把 Claude Code 之类的工具定位为「宇宙级通用 agent」，并给出两条路线：
- 会编程的人 → [[build-your-own-agent]]：先手写最小 SWE agent，再对照 Claude Code / Codex 学习现代机制；
- 不会编程的人 → [[headless-agent-pattern]]：headless 驱动 Claude Code + temp folder + JSON 状态回传，端到端办事。「这正是 Claude Code 被设计出来的用法。」

## YC 创始人的「软件工厂」（CS153）

在 CS153，YC 的 [[garry-tan]] 用一个 **\$200/mo 的 Claude Code Max 计划**、**独自约 5 天**重建了他当年的创业公司 Posterous（当年是 10 人 + \$4M + 2 年才做出来），并把这套配置称为**「软件工厂」（software factory）**。他的 **plan-review skill**（每天跑约 20 次）把测试覆盖率推到 **80–90%**，用以逃离所谓的「AI slop」。YC 创始人们的调侃：**"Claude Code is my ADHD CEO, Codex is my near-non-verbal 200-IQ CTO"**。详见 [[ai-native-company]]、[[agentic-engineering-primitives]]（来源 [[cs153-garry-tan-diana-hu-ai-native]]）。

## 相关来源
- [[claude-code-session-management]] — Thariq 讲 context/session 管理
- [[claude-obsidian-second-brain]] — @defileo 讲 Claude Code + Obsidian 搭建第二大脑
- [[a-motorcycle-for-the-mind]] — Naval 将 Claude Code 视为 vibe coding 的典型
- [[inside-anthropic-the-circuit]] — Anthropic 视角：Claude Code/Cowork 的诞生与影响
- [[jensen-huang-lex-fridman]] — Jensen Huang 称 agentic coding（他叫「OpenClaw」）是「the iPhone of tokens」、史上增长最快的应用
- [[cs153-jensen-huang-compute]] — Jensen 对学生：「Claude is a product, and Claude Code is a whole harness around it」，开源下载难以匹敌
