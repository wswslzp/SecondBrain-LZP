---
title: "Context Rot"
tags: [ai, claude-code, context-management, model-behavior]
date_created: 2026-04-19
date_modified: 2026-04-19
related: ["[[context-management]]", "[[claude-code]]"]
---

# Context Rot

**观察**：模型性能随 context 增长而下降——注意力被稀释到更多 token 上，**旧的、无关的内容**开始干扰当前任务。

## 经验值

对 1M context 的模型（如 Claude Opus 4.7 1M），**经验**开始点约为：

> **~300-400k tokens**

这不是硬规则——严重程度**高度依赖任务**：
- 代码调试（多文件交叉推理）更容易早感到 rot
- 简单的文档续写类任务耐受度更高

## 与 context window 硬上限的区别

- **硬上限**：1M 之后模型根本放不下，必须 [[context-management|compact]] 或开新 session
- **Context rot**：还没满，但**质量已经开始下降**

也就是说，"context 还有空间"≠"现在继续最优"。

## 为什么会发生

- Transformer 注意力是 softmax over all tokens —— token 越多，每个 token 能分到的注意力越少
- 长对话里，早期 tool call 输出、被否决的方案、已失败的路径都在 context 里
- 这些"死 context"争夺注意力，让当前任务的信号更弱

## 对工作流的启示

- **主动管理** context，不要等到硬上限（参见 [[context-management]]）
- **Rewind** 比"在错误之上继续"更干净——能删掉死 context
- 高难度、智能敏感的任务（复杂 debug、架构决定）最好在 **context 较新时**做
- 低敏感度任务（写文档、整理命名）可以容忍更长 context

## 关键引语

> "Context rot is the observation that model performance degrades as context grows because attention gets spread across more tokens, and older, irrelevant content starts to distract from the current task."

## 来源
- [[claude-code-session-management]]
