---
title: "Multi-Agent 适用与不适用"
tags: [ai-agents, multi-agent, map-reduce, go-driven, scaling]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[multi-agent-research-loop]]", "[[lidang]]", "[[agent-comfort-zone]]", "[[claude-code]]", "[[garry-tan]]", "[[agentic-engineering-primitives]]", "[[ai-native-company]]"]
---

# Multi-Agent 适用与不适用

[[lidang]] 对 multi-agent 的核心判断：**大多数"多 agent 通信 / 组织模拟"是天坑，只有干净可拆分的并行任务和 go-driven 的 multi-agent 才真正有价值。**

## 不适合 multi-agent 的场景

### (a) 编程并行 → merge 地狱

多个 agent 并行给同一项目贡献代码 → **七手八脚 merge 代码**极其危险，会产生 code management / software engineering management 混乱，最后一定一团糟。

> coding 更适合**单 agent「一次走到黑」**。

注意：立党强调他反对的是 **multi-agent 做编程**，不是反对 AI agent 做编程。（他自己去年开源的 full self coding 项目、以及很多 YC 在投的方向，在这一点上都"不太适合"。）

### (b) 顺序 role-play 流水线（如 MetaGPT）

MetaGPT 把一个团队抽象成角色串行流水线：**PM → 架构师 → 程序员 → code review → QA test → 再回到程序员**。这是 **sequential** 的——一个做完交给下一个。

> 串行完成，效率一定**低于**单 agent 持续工作。唯一好处是 **context 隔离**（干净），但达不到并发级别的效率提升。

### (c) 公司 / 组织 / 团队架构模拟

CrewAI、AutoGen、agent-agency（GitLab 上爆火过）、腾讯 workbody（飞书可能也在做）这类 **multi-agent 通信协议 / agent-agency**：一堆 agent 你一句我一句、**七嘴八舌、没有 manager、没有决策者**。

> 就像《分手厨房 Overcooked（胡闹厨房）》一样一团糟——谁来决定、谁来管理？没有管理，最后一定没有产出。这是过去两三年大家**公认踩的一个超级大天坑**。

例外：扮家家、扮联合国、做管理学研究、看看"谁是大傻逼"——这些**可以**做，但别放进生产力环境。

## 适合 multi-agent 的场景

### (1) map-reduce 式大规模并行

组织结构干净、任务可独立拆分：**先 fan out（map）给多个 agent，再逐层 reduce 汇总**（源自 Google 的 MapReduce 论文）。适用：

- 大规模网页爬虫
- 文献 / research / survey / 大规模调研
- 数据清洗
- 并行客服
- 大规模审核

> 足够并行、足够独立拆分，只要一层一层汇总，架构就很干净。

### (2) 有良好流程控制与管理 + go-driven 的 multi-agent

做好流程控制与管理的 **go-driven multi-agent**——立党已在 GitHub **开源，1000+ star**（详见 [[lidang]]）。下一期他会专门讲"用管理学方式做真正合理的 multi-agent 管理"。

## 价值判断：1000× 成本要换 ≥10–100× 时间提升

> 只有当 **1000× 的成本**能换来 **≥10–100×（哪怕 10× 甚至 3–5×）的提升**才值得——因为 1000× 成本只是**钱**的问题，而 10× 的效率提升**不是钱能解决**的问题。

用 1000× 的 agent 却换不来 1× 提升，就毫无意义。

### 为什么 multi-agent 仍是唯一值得信的 scaling 路径

- token 会越来越**便宜**、越来越**快**；
- multi-agent 并发度会越来越**高**；
- 模型会越来越**聪明**。

> 在这个大前提下，**multi-agent 是你能相信的唯一的 agent scaling / post-training scaling 路径**——用 1000× agent 换 10–100× 提升是一笔极佳投资。

## 一个有产出的 multi-agent 正例

[[multi-agent-research-loop]]（[[zostaff]] 的 [[ai-quant-system]]）是"有产出"的 multi-agent 范例：不是七嘴八舌的组织模拟，而是 **generate + 对抗审查（Critic）+ 统计校正** 的单一职责流水线，每个 agent 单一职责、有明确接受标准与硬门——恰好符合立党所说"干净、可验证、有流程控制"的要求。

## YC 的代码级 agent 原语（CS153）

[[garry-tan]] 在 CS153 给出一组 [[agentic-engineering-primitives|code-level primitives]]，与本页「干净、可验证、有流程控制」的判断互补：**skill**（一份能调用代码的 markdown runbook）、**resolver**（惰性加载指令、而非把 CLAUDE.md 撑爆——扮演「组织架构图 / org chart」的角色）、**skillify**（把一次性操作提升为受测 skill：单元测试 + LLM evals + 集成测试 + trigger eval + check-resolvable），以及 **latent-vs-deterministic** 纪律（确定性工作放进代码、latent 工作留给 LLM）。详见 [[ai-native-company]]。

## References

- [[lidang-ai-agent-tutorial]] —— 立党AI学习研究完整教程（第一期）
- [[multi-agent-research-loop]]、[[agent-comfort-zone]]、[[claude-code]]
