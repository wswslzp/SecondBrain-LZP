---
title: "手写你自己的最小 Agent"
tags: [ai-agents, coding-agent, education, claude-code, learning-path]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[claude-code]]", "[[lidang]]", "[[agent-comfort-zone]]", "[[vibe-coding]]"]
---

# 手写你自己的最小 Agent

[[lidang]] 主张：**当代计算机 / AI 专业大学生的「第一节课」= 从头手写一个 minimum SWE/coding agent 并跑通**。这类比过去几十年计算机系学生"手搓"的传统——写一个 Lisp interpreter、编译器、操作系统、数据库、JavaScript transpiler。从 2024/2025 年起，这个"手搓项目"应该换成 **agent**。

> 你不写这个东西，你大学可以说是白读或者不及格。

## 最小 agent 的核心功能清单

一个最小可运行的 coding agent，需要你自己实现这些核心机制：

| 功能 | 说明 |
|------|------|
| **prompt 拼接** | 把用户 input 拼接成正确的 prompt 喂给大模型 |
| **function calling / MCP** | 把 function calling、MCP 工具定义正确喂进去 |
| **task 拆分与调度** | 一个 prompt 进来，拆成几个 task（task scheduling）|
| **loop 与流程控制** | agent 如何持续完成任务、何时需要用户输入、如何写 loop |
| **parse API output** | 正确 parse 大模型 API 返回的 output |
| **terminal / bash 执行** | 在 terminal 执行 bash 命令、读取 output |
| **文件 I/O** | 基本的文件读写 |

> 最小的 SWE agent 其实就是：**terminal 执行 + terminal 读取 output + 文件 I/O**。把这些实现好，你的 agent 就能正确运行。

## 三步法

1. **看懂** —— 参照 [[claude-code]] / Codex 的实现（不是抄，是当课本读，看它们如何写）。
2. **想明白 / 设计** —— 自己把这部分功能正确地设计出来。
3. **实现并通过测试** —— 让它跑起来、通过测试。

三步走完，你就是一个"合格的入门 agent 大学生"。

## 对照现代 coding agent：它们已经历「四五次工业革命」

你的第一版 agent 相当于"发明了马车"。接着要去看今天的"高铁"（[[claude-code]] / Codex / OpenCode / Kimi code）如何设计。看不懂它的 codebase（如 Codex 用 Rust 写）就让 Claude Code / Codex 自己帮你读懂。要看懂的**主要机制**：

- **plan mode**
- **TUI**（terminal UI，人机交互体验）
- **long-term memory** —— 每个 agent 与每个 sub-agent **各自**的长期记忆
- **multi-agent / sub-agent 调度与状态管理** —— 如何调度、读取状态、看工作环境、看输出、管理它们
- **background tasks 管理** —— 后台跑十几个 terminal 任务如何管理
- **skills / plugins** —— 一堆 markdown，如何读 title / description，在正确时机 pick up 正确的 skill
- **context auto-compression** —— 上下文过长时的手动/自动压缩
- **loop / workflow 控制** —— 不是无限 loop、也不是随便停，如何判断何时停止
- **sandbox 控制** —— 在 Docker 里如何启动、监控、停止、传参
- **MCP 配置** —— 自由配置 MCP
- **可视化与可观测性** —— 哪些给用户看、哪些自己判断、哪些千万别给用户看

> 先把这些学好、实现一遍、有个基本轮廓，**然后**才能提出你自己的创新。

## 选模型：85 分 vs 95 分

- 对**日常 agentic coding**，85 分和 95 分模型**没有显著差异**——普通人感知不到差距。
- 写前端、写全栈 App 这类工作不需要"那么聪明"的模型；大家都用 Claude Code / Codex / OpenCode 这类工具时，好模型和差模型差距被拉平。
- 普通人**不必为 95 分模型多花钱**，85/90 分性价比最高；95 分只对"世界级难题"才必要（类比：初中数学题不需要陶哲轩）。
- 中国大陆用户可直接买国产 coding plan（智谱 / Moonshot / 阿里 / DeepSeek / 小米 / 快手 / MiniMax / 阶跃星辰）。

## 与 headless 用法的关系

手写 agent 是给**会编程、对 agent 有信仰**的人的路线。对"不会编程的 99% 人"，立党的建议是反过来——不要手搓 bespoke agent，直接用通用 agent 的 [[headless-agent-pattern]]。

## References

- [[lidang-ai-agent-tutorial]] —— 立党AI学习研究完整教程（第一期）
- [[claude-code]]、[[agent-comfort-zone]]、[[vibe-coding]]
