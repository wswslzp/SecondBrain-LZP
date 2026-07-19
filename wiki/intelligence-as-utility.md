---
title: "智能作为新公用事业（Intelligence as a Utility）"
tags: [ai, openai, utility, tokens, economics, agi, concept, cs153]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[sam-altman]]", "[[openai]]", "[[token-economics]]", "[[compute-infrastructure]]", "[[jensen-huang]]", "[[satya-nadella]]"]
---

# 智能作为新公用事业（Intelligence as a Utility）

[[sam-altman|Sam Altman]] 在 [[cs153-sam-altman-scale|Stanford CS153]] 提出的框架：我们正在**创造一种新的 utility（公用事业）**——**智能（intelligence）**。这类东西极少——electricity、internet、water——所以可供参考的历史比喻也很少。

> "This doesn't happen very often. Electricity is a utility, internet is a utility, water... there's not a lot of these."

## 「Light at night」：卖体验，不卖底层

Altman 研究了「电力成为 utility」的历史：早期电力公司**不卖「电」**——因为没人知道电是什么、听着还很吓人（「会以某种可怕方式电死你」）。

> "They didn't talk about selling electricity... what they started marketing, selling to people was light at night."

- 他们卖的是 **「light at night（夜里的光）」**——一个具体、可欲的**结果**;「顺便，同一样东西以后还能替你洗衣服」这种跳跃太远、当时没人信。
- **OpenAI 还没找到自己卖智能的「light at night」类比**——直接说「we're selling intelligence」，人们「somehow not resonating」。这是把智能变成 utility 的**关键叙事缺口**。

## Tokens-as-utility（Sam） vs Compute-as-utility（Jensen）

CS153 系列里「utility」这个词被多位讲者用在**不同层**上，构成一组有意思的对位：

| | **Sam Altman** | **[[jensen-huang|Jensen Huang]]** |
|---|---|---|
| 什么是 utility | **tokens / intelligence** | **compute（芯片）** |
| 消费者思考的单位 | tokens，或再上一层（agent 时长） | 算力接入 |
| 抽象掉什么 | 硬件（哪块芯片、在哪、谁供电） | — |

Altman 的判断：作为消费者/企业，你思考的单位会**接近 tokens**，甚至再上一层——就像**话费账单**里你买的是 airtime + 若干 GB，而不关心基站是哪块硬件、怎么连上网的。**hardware gets abstracted out。**

> "You will have an OpenAI token subscription that you will plug into everything."

两种说法**不冲突**：compute 是供给侧的 utility（[[compute-infrastructure]]、[[token-economics]]、[[value-per-gigawatt]]），tokens/intelligence 是需求侧、面向终端用户的 utility。参见 [[cs153-jensen-huang-compute]] 的 compute-as-utility 论证。

> **[[satya-nadella|Satya Nadella]] 在本 CS153 系列中独立用了同一个「电力 → light at night」比喻**——三位讲者（Sam、Jensen、Satya）都把 AI 类比为一次公用事业级的转变，只是各自站在栈的不同层。

## 民主化 vs 集中：utility model 的政治含义

把智能做成 **utility** 不只是营销问题，而是**未来 10 年最大的分叉**（Altman 给民主路径 **~80%** 概率）：

- **集中是个 attractor state**——默认情形是技术集中到少数公司，令它们占据地球财富的一大块。这既 **unfair/unstable**，也是 **alignment failure** 与**脆弱世界**的风险。
- **utility model 是解药**：把技术推向全世界，让「everybody winning、everybody's values represented、everybody having agency」。
- Altman 的立场之所以有分量：**即便 OpenAI 会是那几家集中受益者之一**，他仍说这个集中风险「**not something we should tolerate**」。
- 逆风：会有很强的 **safety/stability** 论证反对「把技术推出去」，以及大量 **power-seeker** 想集中权力。

## Demand uncapped → shortage forever

utility 框架的经济学后果：**需求无上限**。

- 类比电力：**离开价格谈不了全球电力需求**——价格降 10× 或升 10×，需求天差地别。
- 智能同理：**「if we can make models sufficiently smart and at sufficiently low cost, demand is kind of uncapped.」**
- 推论：**「there will be a shortage forever」**——只要能持续把智能做得更强更便宜，价格就会一直略高于「应有」水平（有了廉价个人 agent，你会想同时跑 10 个、100 个）。
- 因此 Altman 认为**交付海量、廉价、abundant 的 intelligence（inference 侧）被严重 under-invested**——这是他会推荐 CS153 学生做的方向。与当前**「gigantic compute shortage」**（[[compute-infrastructure]]、[[ai-energy-bottleneck]]）直接相扣;前沿实验室「will have to become insurance companies to a degree」。

## 相关页面

- [[sam-altman]]
- [[openai]]
- [[token-economics]]
- [[compute-infrastructure]]
- [[jensen-huang]]
- [[satya-nadella]]

## References

- [[cs153-sam-altman-scale]] — Stanford CS153「Scale, AGI, and the Future of Everything」
- [[cs153-jensen-huang-compute]] — compute-as-utility 对位
