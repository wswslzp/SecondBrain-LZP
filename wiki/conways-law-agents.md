---
title: "康威定律与 agent 设计"
tags: [ai-agents, multi-agent, organization, conways-law, agentic-engineering]
date_created: 2026-07-21
date_modified: 2026-07-21
related: ["[[multi-agent-patterns]]", "[[openclaw]]", "[[ai-native-company]]", "[[agentic-engineering-primitives]]", "[[tasks-vs-jobs]]"]
---

# 康威定律与 agent 设计

**康威定律（Conway's Law）**：组织造出的软件，其结构会**镜像组织自身的沟通结构**。[[vincent-koc|Vincent Koc]] 用它解释一个反直觉现象——**为什么复杂组织的 multi-agent 设计往往不是最优**，以及为什么 OpenClaw 刻意保持「务实的小核心」而非上马 manager/planner/嵌套子团队。来源：[[silicon-valley-101-vincent-koc-openclaw|硅谷101 访谈]]。

## 组织把自己镜像进 agent

> 例：市场团队有 growth 组和 retention 组 → 建代码时就分出「促销系统」和「留存数据系统」，只因团队是这么分的。

复杂组织于是把**既有组织架构**照搬进 agent（manager、planner、sub-agent、nested teams）——

- 这**不代表**是解决问题的最优方式；
- 本质是**继承过去的包袱**，而非从**一张白纸**问「理想方式是什么」。

## 为什么 startup 能 agent-first 地快

- **新组织/startup** 能从白纸出发 **agent-first**、快速迭代；
- **老组织**要走完整的 change management，先搞懂「这对我们意味着什么」。
- **COO 之问**（Vincent 转述一位做 AI transformation 的朋友）：CTO 手里有一堆 agent 设计和框架，但**如果我是 COO——未来的工作场所、团队结构、agent 编排长什么样？** 这才是真正该有的对话；很多人只是把现有东西塞进 agent 期待它「变魔术」。

## 方法：白纸 + 实验 + 迭代，而非追求完美

> 别拿现有小块去死磕完美。**从一张白纸重新设计这个团队/问题 → 一天内搭个能跑的 agent → 它不会完美 → 学到什么 → 迭代。**

Vincent 的元判断：**2026 年的 agentic engineering 与此前根本不同**，很多组织和开发者「还没跨到另一边」——其实 SOTA 模型对这个问题理解很好，可以**直接和它对话、和 agent 一起把 agent 搭出来**，再从经验里学，而不是先造一堆小 skill 碰运气。

## 与本 vault 的互证

- **[[multi-agent-patterns]]**：与 [[lidang|立党]]「(c) 公司/组织/团队架构模拟是天坑」**正面互证**——一堆 agent 你一句我一句、没有 manager/决策者 → 一团糟。康威定律给出**原因**：那种设计只是把人类组织的沟通结构镜像了进去。两人共识：**多数「组织模拟型」multi-agent 不该进生产**。
- **OpenClaw 的务实小核心**：Vincent 说 9/10 单 agent 足够，多智能体瓶颈是 **context** 而非成本；只在有独立 system prompt 的可重复任务时才切出专门 agent（心法「管理一个员工」）。见 [[openclaw]]。
- **[[ai-native-company]] / [[agentic-engineering-primitives]]**：[[garry-tan|Garry Tan]] 的 resolver「扮演 org chart」、原语↔组织同构，是康威定律的**正向**用法——先想清组织，再让 agent 结构与之对齐；Vincent 的警告是其**反面**——别把**旧**组织的包袱照搬。
- **[[tasks-vs-jobs]]**：COO 之问指向工作场所与团队结构的重构，与「tasks vs jobs」的组织层影响相接。

## References

- [[silicon-valley-101-vincent-koc-openclaw]] — 硅谷101 对话 Vincent Koc（WAIC 2026）
