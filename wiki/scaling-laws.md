---
title: "Scaling Laws"
tags: [ai, scaling-laws, compute, llm, concept]
date_created: 2026-07-19
date_modified: 2026-10-25
related: ["[[compute-infrastructure]]", "[[frontier-systems]]", "[[ai-factory]]", "[[dario-amodei]]", "[[jensen-huang]]", "[[nvidia]]", "[[sam-altman]]", "[[satya-nadella]]", "[[intelligence-as-utility]]", "[[liang-wenfeng]]", "[[agi-roadmap-ladder]]", "[[lindon-gao]]", "[[dyna-robotics]]", "[[lindon-gao-dyna-xiaojun]]"]
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

## CS153：Altman 的「scale is its own quality」

[[sam-altman|Sam Altman]]（[[cs153-sam-altman-scale]]）在 CS153 把 scaling 推广为一条更宽的命题——**「scale is its own quality」**：最有意思的东西都来自**规模下的涌现性质（emergent properties at scale）**，其回报超出共识（AI 模型、研究团队、经济体、YC 批次皆然）；他认为这个领域曾「held back by a generation of scientists too certain about what scaling wouldn't produce」。[[satya-nadella|Satya Nadella]] 则把 Microsoft 2019 年那笔 $1B 投资 OpenAI 描述为**押注这条 scaling-laws 的 Pareto 会持续延伸**，并由此引出「智能/算力将成为一种新公用事业」（[[intelligence-as-utility]]）的判断。

## [[liang-wenfeng|梁文锋]]：「墙是对硅谷说的，中国离墙还很远」

[[liang-wenfeng|梁文锋]]/[[deepseek|DeepSeek]]（[[liang-wenfeng-investor-meeting]]）同样**信 scaling、没看到上限**，但加了一个东西方视角的关键限定：

> 「硅谷在说 Scaling 到头，那是对硅谷说的；对中国人来讲，我们离那个还很远——我们根本没有 Scaling 到那个程度。」

- **约束是算力不是意愿**：「阻止我们 Scaling 的其实就是算力」；他们训多大模型是**按资源倒推**的，不是「这么大就够了」，「还没机会碰到 Scaling 的墙」。见 [[china-us-compute-gap]]。
- **叠加新范式（阶梯）**：在 scaling 之上，梁给出 LM→CoT→Agent→**持续学习**→奇点→具身的路线图，认为**下一代模型的核心能力是持续学习**（当前 Agent 能力受限正因不能有效持续学习）。完整见 [[agi-roadmap-ladder]]——与 Jensen 的第 4 条 agentic scaling 可对读。

## 具身数据的规模化押注

[[lindon-gao-dyna-xiaojun]] 给出机器人领域的一个口述案例：DYNA 在约 100 万小时第一人称数据上观察到规模效应，并认为应先扩大多样经验，再做质量筛选。该数字未经独立核实，也不能直接等同于语言模型的 scaling law。

## 相关页面

- [[compute-infrastructure]]
- [[frontier-systems]]
- [[ai-factory]]
- [[dario-amodei]]
- [[agi-roadmap-ladder]] — 梁文锋的 AGI 阶梯与持续学习瓶颈

## References

- [[inside-anthropic-the-circuit]] — Bloomberg「The Circuit」深访（2026-06-10）
- [[lindon-gao-dyna-xiaojun]] — 张小珺对 DYNA 创始人 Lindon Gao 的访谈（2026-10-15）
