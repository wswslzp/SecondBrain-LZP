---
title: "Scaling Laws"
tags: [ai, scaling-laws, compute, llm, concept]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[compute-infrastructure]]", "[[frontier-systems]]", "[[ai-factory]]", "[[dario-amodei]]", "[[jensen-huang]]", "[[nvidia]]"]
---

# Scaling Laws

[[dario-amodei|Dario Amodei]] 在 OpenAI 期间提出的核心思想：**即使底层算法不变，LLM 也会随 data + compute 增加而可预测地变强**。

> "At OpenAI, Dario developed the concept of scaling laws, predicting that large language models would improve simply by adding more data and computing power, even if the underlying algorithm stayed the same."

## 当时是「反主流」的科学观点

在提出之时，「相信 scale up 是模型变聪明变强之路」的人并不多。

> "I know it sounds crazy now looking back, not a lot of people believed, hey, scale up is the way that these models are gonna get smarter and better. That was sort of an unusual counter-cultural scientific perspective." — Dario

这套观点由 OpenAI 的 founding research team 持有，最终「supercharge」了 OpenAI 的模型，**为 GPT / ChatGPT 铺路**。

## smooth exponential 现象学

Dario 用「smooth exponential」描述亲历 scaling 的主观体验——曲线在很长时间里看似平坦，然后突然起飞：

> "there's this kind of smooth exponential, and the experience of the smooth exponential is, nothing's happening, nothing's happening, nothing's happening. Little things happen, and then zoom, it goes crazy." — Dario

这条曲线的可预测性强到他能提前判断 [[anthropic]] 会「在大约这个时间」成为收入与估值最高的 AI 公司——「indeed, it has happened」。到今年，Anthropic「第一年增速**超过 exponential**」（Q1 年化约 80×）。

## [[jensen-huang|Jensen Huang]] 的「四条 scaling laws」

Dario 首创 scaling laws 的**概念**（算法不变、data+compute 即可变强）；[[jensen-huang|Jensen]] 在 Lex Fridman 访谈里把它扩展为**四条**，并强调最终只有一个约束——compute：

1. **Pre-training（预训练）** — 更大模型 + 更多数据 = 更聪明。Ilya「we're out of data / pre-training is over」引发行业恐慌，但 Jensen 反驳：未来大量数据将是 **synthetic**（人类互相教学的数据本就多是「合成」的——你创造、我消费、再改写再生成）。于是训练从「受数据限制」转为「**受 compute 限制**」。
2. **Post-training（后训练）** — 用 AI 把 ground truth 增强 / 合成出海量数据，继续 scale。
3. **Test-time / inference（测试时 / 推理）** — 「**inference is thinking, and thinking is hard**」。推理 = reasoning + planning + search，极其 compute-intensive；反驳了当年「推理很简单、会被 commoditize、只需小芯片」的说法。
4. **Agentic scaling（智能体扩展）** — 一个 agentic system spawn 大量 sub-agents = 「**multiplying AI**」（像招更多员工一样扩展）。产生的经验数据再回流到 pre-/post-/test-time，形成一个不断自我强化的循环。

> "Intelligence is gonna scale by one thing, and that's compute." — Jensen Huang

> 另一句精炼定义（[[cs153-jensen-huang-compute|CS153]]）：「**thinking is generating tokens you consume internally; tool use is generating tokens you consume externally.**」——test-time 与 agentic 两条 law 本质都是「多产 token」。

这四条正是 [[nvidia]] 押注 [[compute-infrastructure]] 与 [[extreme-co-design]] 的底层逻辑，也解释了为何 test-time 与 agentic 阶段需要不同的硬件（Grace Blackwell → Vera Rubin 从跑 LLM 转向跑 agents）。

## 与基础设施的关系

scaling laws 把「更多 compute」直接转化为「更强模型」，因此是 [[compute-infrastructure]] 资本狂潮的底层逻辑——Big Tech 三年 CapEx 从 $300B 冲向 $1.2T，本质是在为这条曲线加燃料。相关工程/系统视角见 [[frontier-systems]] 与 [[ai-factory]]。

## 相关页面

- [[compute-infrastructure]]
- [[frontier-systems]]
- [[ai-factory]]
- [[dario-amodei]]

## References

- [[inside-anthropic-the-circuit]] — Bloomberg「The Circuit」深访（2026-06-10）
