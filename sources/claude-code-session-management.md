---
title: "Using Claude Code: Session Management & 1M Context"
author: "@trq212 (Thariq)"
date_ingested: 2026-04-19
date_published: 2026-04-16
tags: [claude-code, context-management, ai, productivity]
url: "https://x.com/trq212/status/2044548257058328723"
type: twitter-thread
---

# Using Claude Code: Session Management & 1M Context

## 核心论点

1M context window 是一把双刃剑——它让 Claude Code 能更长时间自主工作，但也让 **context pollution** 风险倍增。会话管理（session management）是使用 Claude Code 的关键技能，几乎全部从**如何经营 context window** 出发。

## Context 基础概念

### Context window 包含什么
- system prompt
- 迄今为止的对话
- 每次 tool call 及其输出
- 每个已读的文件

### Context rot
模型性能随 context 增长而下降——注意力被稀释，旧的无关内容干扰当前任务。1M 模型的观察经验：**大约在 300-400k tokens 开始明显**，但高度任务相关，不是硬规则。

### Compaction
接近 context 上限时的压缩：把已做工作摘要到更小描述，在新 context 继续。可主动触发。

## 每次回合的五个分支点

完成一个 Claude 交互后，下一步的选项：

| 操作 | 含义 |
|------|------|
| **Continue** | 继续在同一 session 发送消息（最自然） |
| **/rewind (esc esc)** | 跳回先前某条消息重试，之后的消息被丢弃 |
| **/clear** | 开启新 session，通常附带刚学到的简要 brief |
| **/compact** | 把当前 session 摘要化后在摘要之上继续 |
| **Subagents** | 委托给拥有干净 context 的 agent，只回收结果 |

**继续是最自然的；其他四个都是在管理 context。**

## 关键启发法

### 1. 新任务 = 新 session
1M context 允许更长任务，但"context 没满"≠"应该继续用"。规则：**新任务就开新 session**。
- 灰色地带：强相关的后续任务（如给刚写的功能写文档）—— 重读文件的代价 vs 保留 context 的效率，按任务智能敏感度权衡。

### 2. Rewind 优于纠错
> "If I had to pick one habit that signals good context management, it's rewind."

示例：Claude 读了 5 个文件尝试方法 A 失败。直觉是说"不行，试 B"。更好的做法：
- **rewind 到文件读取之后**
- 用新信息重新 prompt："别用 A，foo 模块没暴露那个 API，直接用 B"

可以用 `summarize from here` 让 Claude 写一封**自己给过去自己的交接信**（"我尝试了 X，失败原因是 Y"）。

### 3. Compact vs Clear

| | /compact | /clear |
|---|---------|--------|
| 机制 | Claude 摘要历史并替换 | 扔掉一切重开 |
| 优点 | 无需手动写 brief，Claude 可能更全面 | 彻底干净 |
| 缺点 | 有损，信任 Claude 取舍 | 需要自己写 brief |
| 可操控 | 可加指令：`/compact focus on auth refactor, drop test debugging` | — |

### 4. 什么导致坏 compact
- 任务对单一 session 太复杂
- 保留了过多无关 context
- 摘要丢失了任务目标的关键信息

### 5. Subagents 做隔离
- 每个 subagent 拿到全新 context
- 结果被拉回主 session
- 适合**不需要共享 context** 的并行任务

## 五条 Takeaways

1. **Context 有限但大** — 1M tokens，但 context rot 在 300-400k 开始
2. **新任务 = 新 session** — 切换任务时不要犹豫
3. **Rewind 优于纠错** — 跳回而不是在错误之上继续
4. **主动 compact** — 用 focus 指令引导压缩
5. **Subagents 做隔离** — 需要干净 context 的并行工作

## 关键引语

> "The 1M token context window is a double-edged sword."

> "If I had to pick one habit that signals good context management, it's rewind."

## 相关页面
- [[context-management]]
- [[context-rot]]
- [[claude-code]]
- [[llm-wiki-pattern]]
