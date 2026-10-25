---
title: "Language Agent（语言智能体）"
tags: [ai-agents, language, concept, reasoning, tool-use]
date_created: 2026-10-25
date_modified: 2026-10-25
related: ["[[yu-su]]", "[[specialized-intelligence]]", "[[openclaw]]", "[[claude-code]]", "[[agi-roadmap-ladder]]"]
---

# Language Agent（语言智能体）

[[yu-su|苏煜]] 给 2022 年以后这一代 agent 的名字。2024 年他与 Diyi Yang、姚顺宇、Tao Yu 做过一个 tutorial 来定义它。定义性特征不是“用了大模型”，而是**语言成了脚手架**。

## 语言撑起的四件事

- **感知**：人和系统可以用灵活的语言交互，不再被固定动作空间卡住。
- **推理**：chain-of-thought 让计算量跟着任务走。难的任务多生成 token，每个 token 都是一次前向传播。早期游戏 agent 无论局面多难，都只有一次 forward pass。
- **行动**：自然语言、形式语言和代码都是行动媒介。在数字世界里，这几乎是全能接口。
- **记忆**：预训练是一次以语言为材料的压缩，把表层形式压成对世界的表示。他不再接受“随机鹦鹉”作为完整描述。

## 和前代的差别

| 代际 | 记忆 | 自主 | 失败方式 |
|---|---|---|---|
| Logical agent（约 1950–1990） | 有限逻辑陈述 | 问答式推理引擎 | 表达力不够，知识获取太贵，专家系统带来 AI 冬天 |
| Neural agent（深度强化学习） | 一个游戏的规则 | 一次前向传播 | 样本效率差，计算量不随难度变化 |
| Semantic parsing | 某一个库、图或网站的形式表示 | 把话变成可执行动作 | 没有能带去新环境的先验 |
| Language agent | 压缩进模型的语言世界模型 | 理解、弹性推理、代码行动 | 通用但不可靠，还没学会具体的小世界 |

语义解析和 language agent 的差别不是“突然想到用语言”。NLP 一直在用语言。差别是 LLM 提供了一个能放进陌生环境、并立刻产生还算合理行为的先验。

## 不是另一个物种的 coding agent

编程语言、图表、手势都是符号系统。苏煜拒绝把 coding agent 当成定义更换。终点是 universal digital agent：在数字世界里做人能做的事。浏览器、桌面、GUI、CLI、API 是正在消弭的手段。代码是数字世界的织物，也是打破这些边界的工具。

Language agent 这个词以后可能变得多余——大家默认 agent 就该有这种能力——但能力不会退场。即使底层不再是 LLM，而是某种世界模型，以语言理解、推理和交互仍然必要。他的一句压缩是：个体思考可以不需要语言，文明需要语言。

## 一条口述时间线

Chain-of-Thought（2022 初）→ ReAct、LLM-Planner、Mind2Web（2022 末到 2023 初）→ Toolformer、AutoGPT（2023 初）→ SWE-bench、WebArena、GPT-4o、SeeAct（2023）→ OSWorld、UGround、Claude computer use（2024）→ Operator、Claude Code（2025）→ OpenClaw 爆火（2026 初）。年份是嘉宾口述，不是重新核定的发表日。完整论证见 [[yu-su-xiaojun-chinese-article]]。

## References

- [[yu-su-xiaojun-agent-history]]
- [[yu-su-xiaojun-chinese-article]]
