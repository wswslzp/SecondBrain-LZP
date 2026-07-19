---
title: "Stanford CS153 | Sam Altman on Scale, AGI, and the Future of Everything"
author: "Sam Altman"
date_ingested: 2026-07-19
date_published: 2026-06
tags: [ai, openai, scale, agi, agents, economics]
url: "https://www.youtube.com/watch?v=F_7M4Hc-usM"
---

# Stanford CS153 | Sam Altman on Scale, AGI, and the Future of Everything

[[sam-altman|Sam Altman]]（[[openai|OpenAI]] CEO）回到 [[frontier-systems|Stanford CS153]] 的 guest 对谈（playlist #2，主持人为课程讲师 [[anjney-midha]] 一侧）。全场围绕一个母题展开——**scale（规模）作为一种独立的「系统设计属性」**——再从这条主线延伸到 ChatGPT / Codex 的起源故事、把「智能」当作**新公用事业（utility）**来卖的框架、未来 10 年的「民主化 vs 集中」分叉、经济再分配、以及史上最大的 **compute shortage**。

Altman 自陈这一场的立场是「offer no theory I find satisfying」——他讲的多是**经验观察**而非理论，尤其在 scale 这件事上。因为是对 Stanford CS 学生讲，落点偏「systems 视角 + 创业方法论」，与本库 [[cs153-jensen-huang-compute|Jensen 那一讲]]（compute 侧）恰好互补：**Jensen 讲 compute-as-utility，Sam 讲 tokens/intelligence-as-utility**（见 [[intelligence-as-utility]]）。

## 核心论点

### 1. Scale：quantity is its own quality
- **「Scale is its own beast; its quantity is its own quality.」** 职业生涯里最有趣的东西，几乎都来自 **scale 上的 emergent properties**，或 scale 在远超共识的地方继续给回报。empirically 成立，但他「没有满意的理论」。
- 适用面极广：AI [[scaling-laws]]、research（把更多聪明人放到同一个问题上）、economies of scale，以及 **YC batch 的 network effects**——「funding startups at scale」本身涌现出的魔力，是 1/10、1/100 规模下根本不存在的（cross-link [[network-effects]]、[[venture-capital-systems]]、[[y-combinator]]）。当年很多聪明人劝 YC「太大了该缩小」，但 batch 内部的网络效应正是没人试过的 scale 才撞见的。
- **人们对 scale 探索不足**，因为「stuff breaks at an accelerating, unpredictable rate」；scaling 因此是个 **systems problem**——把「每一个不该做的理由」逐条拆解、逐个击破（技术能不能做、资本、商业模式、研究文化上的阻力）。
- 深层原因：人类**「did not evolve to think about exponentials」**——很难想象 scaling law、营收、组织复杂度都能指数级延续；要花大量时间用 first principles 陪人把这件事推一遍。组织侧要靠**清晰的目标 + 清晰的路径 + 清晰的决策方式**才扛得住指数级复杂度。

### 2. OpenAI 是个「反着来」的怪胎
- 正常创业：先做产品公司 → 增长放缓 → 才 bolt on 一个 research lab。**OpenAI 相反**：先是 research lab，后来才被迫 bolt on 一个 startup——「I don't really recommend that.」创办时全球「慷慨地说也就四家 AGI 努力」。
- **CS183 该重讲**：如今用「可负担的 token 花费」，一个创业者就能干过去「100 人顶级工程团队」才能干的事；创业的野心、速度、并行度都完全不同了。「someone should do that class again」（他大概不会亲自做）。

### 3. Intelligence as a new utility（本讲概念锚点 → [[intelligence-as-utility]]）
- 真正的 utility 极少：electricity、internet、water。电力公司当年**不卖「电」**（听着吓人、会电死人），而是卖 **「light at night」**。OpenAI 还没找到自己卖智能的「light at night」类比。
- 未来你会有一个 **「OpenAI token subscription，plug into everything」**。
- **Compute-as-utility（Jensen） vs tokens-as-utility（Sam）**：作为消费者/企业，你思考的单位是 **tokens**（甚至再上一层——像话费账单里的 airtime / GB），而不是「哪块芯片、什么硬件」；**hardware 会被抽象掉**（cross-link [[token-economics]]、[[jensen-huang]]、[[compute-infrastructure]]）。

### 4. 民主化 vs 集中：未来 10 年最大的分叉（~80%）
- 十年尺度上最重要的 fork = **技术被广泛民主化 vs 集中在少数公司手里**。
- 集中是个 **attractor state**：不稳定、不公平、既是 **alignment failure** 风险也是**脆弱世界**的风险。即便 OpenAI 会是那几家公司之一，这个风险「**not something we should tolerate**」。
- 解法是推 **utility model**，让人人受益、人人有 agency。他给民主路径 **~80%** 概率，但预计会遇到很强的「safety/stability」反向论证 + power-seeker 的逆风。

### 5. 经济：所有权 vs UBI
- 比起固定的月度现金红利（UBI），他更偏爱**所有权份额 / 「citizens' wealth fund」**——「own a slice of capitalism」。曾资助过一项 UBI 研究，也观察过「创业股权」对人的心理作用，「I know which model hits human psychology better.」
- 引 **Norway 主权财富基金**（Nicolai Tangen，也是本课讲者；该基金持有全球上市公司 ~1.5%）。核心趋势：**leverage 正从 labor 转向 capital**。
- 一个被低估的公平性问题：**compute 如何分配**——他认为 compute 可能成为「人们最需要的那种 utility」。

### 6. Compute shortage：COVID for compute
- **「a gigantic compute shortage」**；H100 / Blackwell 的**长约 vs spot 价差约 5×**，「COVID for compute」，H100 今年基本被订光。
- 只要模型持续变便宜、变强，**需求就是 uncapped → shortage forever**（类比电力：需求随价格剧烈变化）。「people should be freaking out somewhat.」
- 前沿实验室「will have to become insurance companies to a degree」（对冲/承保 compute 供给）。cross-link [[ai-energy-bottleneck]]、[[compute-infrastructure]]。

### 7. 回应 Yann LeCun「LLMs are a dead end」
- 模型在某些方面**已经 superhuman**，在 long-horizon、高判断力的任务上又远逊于人;但**昨天一个模型刚 disprove 了一个难 conjecture**（数学家开始问「is math over?」）。
- world models 对 robotics 很重要，但 **「betting against LLMs scaling at this point feels quite misguided」**。
- 元教训：这个领域「被一代对 scaling 过于笃定其做不到什么的科学家拖累了」；**把身份认同押在某个信念上，会让你看不见数据**——「an important reminder in both directions.」

### 8. 教育：一个 prediction error
- 他曾预测 ChatGPT 上线一年内学校会重设课程；**3.5 年过去，几乎没有实质性的系统级改变**——「that was a prediction error for me.」
- 若继续「pre-AGI」地教与评，会导致 **critical thinking 的 atrophy**。有些技能（写作、编程）仍值得教——作为「思考/学习」这个 **meta-skill** 的载体（cross-link [[cognitive-atrophy]]、[[ai-for-learning]]）。

### 9. 最辣的观点 + one-person frontier lab
- Spiciest take：**「AI is just going to keep going」**——若这被广泛相信，社会现在就该有远多得多的连锁反应。他已「much less of a short-term jobs doomer」（cross-link [[tasks-vs-jobs]]）。
- CS153 的 final project 是 **one-person frontier lab**。若他是学生，会去做 **inference part of the stack**——「交付海量、廉价、abundant 的 intelligence」被严重 under-invested（呼应 [[intelligence-as-utility]] 的 demand-uncapped 逻辑）。

## ChatGPT / Codex 的系统故事

**ChatGPT 的起源（教科书级「意外命中」案例）**
1. 做出 GPT-3，需要赚钱去 scale 到十亿、数十亿美元的超算，但**找不到围绕它的产品**——「a cool demo」。
2. 决定「既然我们想不出产品，就丢进 **API**，寄望别人想出来」——**summer 2020** 上线 GPT-3 API。
3. 起初**零 traction**；约一个月后**在 Twitter 上意外病毒式传播**（同一天几个开发者各自做出酷东西并发帖）。
4. 但模型「shockingly bad」；唯一真正跑通的生意是 **copywriting**（$10–20M run-rate 量级），「not that great」。
5. 关键观察：很多人**用 API key 只是为了 chat**——「people clearly want that.」
6. 恰好有个 in-between 模型 **GPT-3.5**（新的 instruction-following post-training，更好聊），于是按 **YC 原则「see what your users love and do that」**，把它包成 chatbot。
7. 本意只是**「research demo」**——为了说服别人来做 chat 产品、付费用 API;结果**「went crazy viral」**。
8. **「when something starts growing and it's not very good, you have a guaranteed hit.」** 连续 5 天流量冲高回落，第 4-5 天他确认这是真命中 → 宣布 **emergency（好的那种）**，「build a company and a product all at once」，商业模式「later」（先收费只为不烧爆 compute 账单）。

**Codex（原本的 Plan A）**
- ChatGPT 之前，原计划**全押 code**：内部信念是 **code = 计算机世界的 actuator，robots = 物理世界的 actuator**;给足够聪明的模型这两个 actuator，就能让 intelligence 在世界里真正做事。
- **Codex 今年初开始变得很好，5.5 是真正的 inflection point**，人们开始用它做「incredible things」。

**能力管线（pipeline）**
- 当前形态：pre-training / mid-training / post-training + RL 与 supervised 的反馈回路——「definitely the current pipeline」，但他觉得它「不太像最优解」，**预期会有一次 major rewrite**——「a research problem for the AIs to figure out.」
- 目标：**2026 年 9 月**用 **500k A100-equiv GPU** 跑出一个 **AI research intern**;**2028 年 3 月**得到一个端到端、能发明**全新架构**的 talented researcher。

## 金句

> "Scale is its own beast. Its quantities, its own quality."

> "We were a research lab first that later had to bolt on a startup. And I don't really recommend that."

> "With an affordable amount of spend on tokens, you can do what a 100-person, incredibly great engineering team would do as a startup."

> "When something really starts growing and it's not very good, you have a guaranteed hit on your hands."

> "This is an emergency. This is the good kind of emergency, but we have to build a company and a product all at once."

> "Coding was how these models would control things on computers, and robots were how these models would control things in the physical world."

> "That's a research problem for the AIs to figure out."

> "They didn't talk about selling electricity... what they started marketing, selling to people was light at night."

> "You will have an OpenAI token subscription that you will plug into everything."

> "Betting against LLMs scaling at this point feels quite misguided to me."

> "The field was, honestly, held back by a generation of scientists who just were way too certain on what scaling was not going to produce."

> "The risk of keeping is concentrated in a handful of companies — even though we would be one of these companies — is not something we should tolerate."

> "As long as we can continue to make progress on this, there will be a shortage forever."

> "I think AI is just going to keep going."

> "You basically own a slice of capitalism, you own a slice of these companies."

## 关联页面

- [[sam-altman]] — 人物页
- [[openai]] — 公司页
- [[intelligence-as-utility]] — **本讲新建**：智能作为新公用事业（含 tokens-vs-compute-as-utility、light at night、民主化分叉、shortage forever）
- [[scaling-laws]]、[[network-effects]]、[[token-economics]]、[[compute-infrastructure]]、[[ai-energy-bottleneck]]、[[tasks-vs-jobs]]、[[venture-capital-systems]]、[[value-per-gigawatt]]
- 系列同源：[[frontier-systems]]（[[anjney-midha]] 主讲）、[[cs153-jensen-huang-compute]]（compute-as-utility 对位）、[[cs153-frontier-systems]]
- 对照人物：[[jensen-huang]]（[[nvidia]]）、[[dario-amodei]]（[[anthropic]]）、[[satya-nadella]]

## References

- Stanford Online / CS153 Frontier Systems, YouTube: https://www.youtube.com/watch?v=F_7M4Hc-usM
- Raw transcript: `raw/Stanford CS153 Frontier Systems  Scale, AGI, and the Future of Everything.md`
