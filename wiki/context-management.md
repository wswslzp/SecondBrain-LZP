---
title: "Context Management (Agent 会话管理)"
tags: [ai, claude-code, context-management, productivity, workflow]
date_created: 2026-04-19
date_modified: 2026-04-19
related: ["[[claude-code]]", "[[context-rot]]", "[[llm-wiki-pattern]]", "[[context-feedback-loops]]"]
---

# Context Management

在使用 Claude Code 等 agentic coding 工具时，**如何经营 context window** 决定了交互质量。1M token context 让任务能跑更久，但同时放大了 context pollution 的风险。

> 注意：此处"context"指单个会话内的 prompt/token 窗口，与 [[context-feedback-loops]] 中"训练用 context（用户数据、monorepo、交互信号）"是不同层次。两者都以"context 稀缺且关键"为核心。

## Context window 包含什么

- system prompt
- 当前对话历史
- 每次 tool call 输入与输出
- 已读取的所有文件

Context 增长会引发 [[context-rot]]（性能随 context 变大而下降）。

## 五个分支点

每当 Claude 完成一次工作，你有五个选择：

| 操作 | 何时用 |
|------|-------|
| **Continue** | 任务延续且 context 仍干净 |
| **/rewind** (`esc esc`) | 发现方向错了、想带着新知识重试 |
| **/clear** | 切换到新任务 |
| **/compact** | Context 接近满，但需要摘要延续 |
| **Subagent** | 有明确的子任务、不需要共享主 context |

**继续最自然；其他四个都是在主动管理 context。**

## 核心原则

### 1. 新任务 = 新 session
不要因为 context 还没满就不切。**灰色地带**：强相关后续（如给刚写的功能写文档）——此时重读文件的代价可能高于 context 冗余的代价。按任务对智能的敏感度决定。

### 2. Rewind 优于纠错
错误路径上的修正会把"失败尝试"留在 context 里，污染后续推理。更好的做法：
- **rewind** 到方法选择之前
- 用新知识重新 prompt："别用 A，foo 模块没暴露那个，直接用 B"

可以让 Claude `summarize from here` 写一封**给过去自己的交接信**。

> "If I had to pick one habit that signals good context management, it's rewind." — Thariq

### 3. Compact vs Clear

| | /compact | /clear |
|---|---------|--------|
| 机制 | 摘要历史并替换为摘要 | 彻底重来 |
| 是否有损 | 是 | 取决于 brief 质量 |
| 手动成本 | 低（可加指令） | 需要写 brief |
| 风险 | 坏 compact | brief 遗漏关键细节 |

Compact 可以 steer：`/compact focus on the auth refactor, drop the test debugging`。

### 4. Bad compact 的成因
- 任务对单一 session 太复杂（根源）
- 保留了过多无关 context
- 摘要丢失了任务目标的关键信息

**解法**：任务太大时分治（subagent 或 clear + new session），而不是硬 compact。

### 5. Subagents = Context 隔离
- 每个 subagent 拿到**全新 context**
- 只有结果回流主 session
- 适合可并行、不依赖主对话的任务
- 配合 [[llm-wiki-pattern]]：比如同时 lint 多个 wiki 目录

## 与 LLM Wiki 模式的关系

[[llm-wiki-pattern]] 的健康运转依赖好的 context 管理：
- **Ingest**：每个 source 一个 session（新任务 = 新 session）
- **Query**：轻量 session，可 clear
- **Lint**：适合 subagent 并行扫描

## 关键引语

> "The 1M token context window is a double-edged sword. It lets Claude Code operate autonomously for longer, but it also opens the door to context pollution if you're not deliberate about managing your sessions."

> "Every turn is a branching point."

## 来源
- [[claude-code-session-management]]
