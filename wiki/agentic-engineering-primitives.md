---
title: "Agentic 工程原语"
tags: [ai-agents, coding-agents, skills, evals, memory, claude-code]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[ai-native-company]]", "[[garry-tan]]", "[[claude-code]]", "[[hermes-agent]]", "[[llm-wiki-pattern]]", "[[company-brain]]"]
---

# Agentic 工程原语

**Code 层（code level）** 的论点：用 agent 做**真实工作**需要一小组可复用的原语。这些是 [[garry-tan|Garry Tan]] 通过 **OpenClaw / [[hermes-agent|Hermes agent]] 一周一周学到**、并在 [[cs153-garry-tan-diana-hu-ai-native|CS153 讲座]]里公开的：**skill / resolver / skillify / GBrain**。

> 一句话对照：本页 = **code 层**（怎么造 agent）；[[ai-native-company]] = **org 层**（怎么把公司变成 agent 增强的组织）。两页在结尾的"组织同构"处交汇。

## 第一纪律：分开 deterministic 与 latent work

每一个崩掉的 agentic 系统，几乎都是把两类工作混淆了：

- **Deterministic work** → 应该是 **code**（确定、可测、不该幻觉）。
- **Latent work** → 应该交给 **LLM**（模糊、需理解、靠 latent space）。

**经典例子**——晚宴排座：**8 人**用 latent space（"查一下每个人 bio、决定谁挨着谁坐"）没问题；**800 人 / Startup School 6000 人**就 hallucinate、装不下 → 必须让 latent space 和 deterministic code 协作。另一个例子 `context-now.mjs`（带 tests）：OpenClaw 老以为你在英国 Greenwich、报错时间，就用 code 把"当前时间 + 日程"确定化，不再依赖 latent space。

## Skill = 会调用 code 的 runbook

- **本质**：一个 markdown 文件，像"反复办活动的手册"——任何人 / agent 读完 1-2-3…步就知道怎么做（可以分支、可以很复杂）。
- **大转变**：以前"一堆 markdown 文件"被嘲笑没用；**有了 LLM，现在能用 markdown + LLM 做真实工作**——而且 skill **可以调用 code**（Twilio 打电话、Gemini Live 下单/预约……）。
- 与 [[claude-code|Claude Code]] 让人不再打开编辑器同理，OpenClaw / Hermes 让人不再亲自打电话做流程性知识工作。

## Resolver = 治 bloated CLAUDE.md 的解药

- **问题**：CLAUDE.md 塞满指令 → "40,000 tokens" 警告，context 被拖垮。
- **解法**：不把所有指令塞进 context，而是做一个 **master directory**，**按需 lazily load**——"要写 changelog 时才加载 changelog.md"、"要查签名时才走 executive-assistant skill pack"。
- **类比**：**resolver ≈ org chart（组织架构图）**——"谁负责什么、怎么发生"。这是"拥有一个真正好用的 agent"的核心。

## Skillify = 升一层抽象

先**手动把一件事做对一次**（如"保存这篇文章"：看 input、看 output、调到你满意），然后说 **"skillify"**。agent 自动产出的**不止是 skill + code**——真正的重头是那些"像人类系统一样"的 compliance/audit 脏活：

| 步骤 | 内容 |
|------|------|
| 1 | 写 **skill**（markdown） |
| 2 | 写 **code** |
| 3 | 写 **unit tests**（测 code） |
| 4 | 写 **LLM evals**（测 skill 文件） |
| 5 | 写 **integration test** |
| 6 | 建 **resolver trigger**（agents.md） |
| 7 | 写 **trigger eval**（LLM-as-judge，确保够宽、真会被触发） |
| 8 | **check-resolvable**（DRY 去重，否则会长出 1000 个重复 skill） |
| 9 | 端到端 **smoke test** |
| 10 | 定 **schema / memory 存放位置** |

**~10 步里只有 2 步（1、2）是写 skill/code**，其余全是让"这个乱糟糟、更像人类系统而非完美光束代码"的东西真正 work。Garry：直到亲手做 skillify，"我才理解为什么 finance org 里 10–20% 的人只做 compliance"。

## GBrain = 三层记忆系统，长在 LLM Wiki 之上

Garry 的开源记忆项目，**字面上建在 [[andrej-karpathy|Karpathy]] 的 [[llm-wiki-pattern|Knowledge Wiki]] 之上**（也就是**本 vault 运行的同一套模式**）：

1. **起点**：Karpathy 的 wiki，只有 **grep** → 规模一大就 "fell over"。
2. **加检索**：**vector search + RRF fusion + backlinks**。
3. **加结构**：**graph database（typed knowledge graph，类型化知识图）**。
4. **加认识论**：**epistemology layer**——区分 **hunch / 某人的 belief / world knowledge**，并追踪"某人的 contrarian hunch 后来被证明对了"（Garry 最着迷的部分：捕捉一个创始人从"没人信"到"证明它对"的旅程）。
5. **下一步**：**dynamic ontology**——每个用户一套 schema（researcher / journalist / politician 各不同）。

GBrain 里有 ~40 个可试的 skill。参见 [[company-brain]]、[[ai-agent-memory]]。

## 组织同构（与 org 层的交汇点）

最惊人的发现：这些 code 原语**一一映射到公司组织**——也是通往 [[ai-native-company]] 的桥。

| Agentic 原语 | 组织对应物 |
|--------------|-----------|
| **skill** | 有某项能力的**员工** |
| **resolver** | **org chart（组织架构图）** |
| filing rules / memory 存放 | **内部流程**（信息住在哪） |
| **check-resolvable** | **audit & compliance（审计与合规）** |
| **trigger eval** | **绩效评估（performance reviews）** |

> "人类系统很乱——我 45 岁、建了大量 agentic 系统后，才终于理解企业为什么要花那么多人做审计合规。"

## References

- [[cs153-garry-tan-diana-hu-ai-native]] — 讲座源页
- [[ai-native-company]] — 配套的 org 层论点
- [[llm-wiki-pattern]] · [[andrej-karpathy]] — GBrain 的直接祖先（也是本 vault 的模式）
