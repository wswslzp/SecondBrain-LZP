---
title: "Headless Agent 模式"
tags: [ai-agents, claude-code, automation, headless, no-code]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[context-farming]]", "[[agentic-micro-company]]", "[[claude-code]]", "[[lidang]]"]
---

# Headless Agent 模式

[[lidang]] 给「不会编程的 99% 人」的**通用方法**（他称之为"价值 10 万–30 万刀的想法"）：不要手搓 bespoke agent，直接把一个买得起的最好的通用 agent（如 [[claude-code]]）以 **headless 模式**驱动起来，端到端解决任务。

> 这正是 Claude Code 被设计出来的用法。很多人不懂，所以要用中文掰开揉碎讲一遍。

## 万能方法：一步步

1. **绑卡**：给你的 Claude Code 绑好银行卡（充够钱）。
2. **建 temp folder**：建一个临时文件夹，把**所有任务相关的东西**全放进去——文档、表格、报表、图表、报告、SQLite / Access 数据库、PDF 扫描件、数据、markdown、代码、图片，外加**指令 prompt、config、skills**。
3. **写脚本**：写一个 Node / Bun / Python 脚本，从 terminal 以 **headless 模式**调用 Claude Code，用 `--dangerously-skip-permissions` 开启全部权限。
4. **状态写 JSON**：让所有状态和输出写入一个 **JSON file**——成功写进去，失败也更新状态到同一个 file。
5. **让 agent 自己跑**：配好 Claude Code 的 authentication 和 MCP 后，让它自己 authenticate、端到端解决整个问题、汇报结果。"可能跑一分钟，也可能跑三年。"
6. **读 JSON 进入下一步**：进程结束后读取那个 JSON body，进入下一步。

> 这是高中生都能干的活。

## 心法

- **把 agent 抽象成一个人**：一个有人格、能解决问题、办事自动化的人。你不需要为"蔬菜水果销售""算账""防盗门""装修材料"分别设计 agent——agent 就是一个人，喂足数据 + 足够强的模型，它能解决任何问题。
- **通用 agent > 手搓 bespoke agent**：对 **99% 的场景**，一个好的通用 agent 框架 + 你买得起的最好模型，胜过自己随手拼一个 agent。剩下 1% 场景（你很懂业务、有自己的上下文管理与省钱妙招、能做出比手工 function calling 更好的设计）才值得自己搭。
- **多花点钱，省你自己的时间**：用差一点的模型也花不了多少钱，但省下大量调试时间，且更通用、更强大、更可维护。

## 适用范围

同样的方法适用于所有主流 coding agent：**Claude Code / Codex / OpenCode / Kimi code / z code**。立党认为这是"绝大多数不在大厂、不做核心 agent 业务、对 agent 没有信仰的人这辈子能设计出来的最简单、最强大、最可靠、最省事的宇宙级通用 AI agent"。

## 与相关概念的关系

- **[[context-farming]]** —— 人的角色退化为**策展 / 喂 context**：你负责把对的材料塞进 temp folder，agent 负责执行。这与 context farmer 同构——价值从"写代码"迁移到"喂对上下文"。
- **[[agentic-micro-company]]** —— 一个被 headless 驱动、能端到端办事的通用 agent，是"一人公司 / 微型公司"的基本执行单元。
- 与 [[build-your-own-agent]] 互补：那条路线给会编程的人，这条路线给不会编程的人。

## References

- [[lidang-ai-agent-tutorial]] —— 立党AI学习研究完整教程（第一期）
- [[claude-code]]
