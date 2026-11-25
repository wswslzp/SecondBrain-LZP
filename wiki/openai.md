---
title: "OpenAI"
tags: [openai, ai, agi, company, chatgpt, codex, cs153]
date_created: 2026-07-19
date_modified: 2026-10-29
related: ["[[sam-altman]]", "[[intelligence-as-utility]]", "[[scaling-laws]]", "[[anthropic]]", "[[compute-infrastructure]]", "[[frontier-systems]]", "[[vitalik-buterin]]", "[[effective-altruism]]", "[[d-acc]]", "[[silicon-valley-101-vitalik-ea-ai-safety]]", "[[gpt-6-astra]]", "[[huazhe-xu]]", "[[zheqing-zhu]]", "[[sheng-wang]]", "[[wet-lab-verification-loop]]", "[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]"]
---

# OpenAI

前沿 AI 实验室，[[sam-altman|Sam Altman]] 任 CEO。约 2016 年成立;在 [[frontier-systems|AI 全栈]]的**模型层**与 [[anthropic|Anthropic]] 并列。本页以 [[cs153-sam-altman-scale|CS153 一讲]]为主线，记录它**反常的起源、ChatGPT/Codex 的系统故事、以及它对未来的定位**。

## 一个「反着来」的怪胎

正常创业顺序：产品公司 → 增长放缓 → 才 bolt on 一个 research lab。**OpenAI 相反**——**先是 research lab，后来才被迫 bolt on 一个 startup**。

> "We were a research lab first that later had to bolt on a startup. And I don't really recommend that."

- 创办时全球「慷慨地说也就四家 AGI 努力」。
- 早年仍套用**「pre-AI 的创业规则」**，因为「we were trying to make it, we didn't have it yet」。
- 关键战略赌注：**all-in on scaling deep learning**——当时领域内多数天才认为「这算不上科学结果」「已经证明了会随 scale 变好，为何还要继续 scale」。OpenAI 反其道押注（见 [[scaling-laws]]、[[sam-altman]] 的 scale 框架）。

## ChatGPT 的起源（意外命中）

1. 做出 **GPT-3**，需要赚钱去 scale 到数十亿美元超算，却**找不到围绕它的产品**——「a cool demo」。
2. 决定丢进 **API**，寄望别人想出产品——**summer 2020** 上线。
3. 起初零 traction，约一月后**在 Twitter 意外病毒式扩散**;但模型「shockingly bad」，唯一跑通的生意是 **copywriting**（$10–20M run-rate 量级）。
4. 关键观察：**很多人用 API key 只是为了 chat**。
5. 用 in-between 的 **GPT-3.5**（新 instruction-following post-training）包成 chatbot，本意只是 **research demo**（为卖 API），结果**「went crazy viral」**。
6. **「when something starts growing and it's not very good, you have a guaranteed hit.」** 第 4-5 天确认真命中 → 宣布 **emergency**，「build a company and a product all at once」，商业模式 later（先收费只为不烧爆 compute 账单）。

底层 YC 原则：**「see what your users love and do that.」**

## Codex 与能力管线

- ChatGPT 之前的 Plan A 是**全押 code**:内部信念是 **code = 计算机世界的 actuator，robots = 物理世界的 actuator**——给足够聪明的模型这两个 actuator，intelligence 就能在世界里做事。
- **Codex 今年初变好，5.5 是真正的 inflection point**。
- **能力管线**（pre-training / mid-training / post-training + RL 与 supervised 回路）是「definitely the current pipeline」，但 Altman 觉得它「不像最优解」，**预期一次 major rewrite**——「a research problem for the AIs to figure out.」
- 里程碑目标：**2026-09** 用 **500k A100-equiv GPU** 跑一个 **AI research intern**;**2028-03** 得到端到端、能发明**全新架构**的 talented researcher。

## 定位：从卖模型到卖 utility

- Altman 认为 OpenAI 在**创造一个新 utility**（智能），未来每个消费者会有**「OpenAI token subscription, plug into everything」**;但还没找到卖智能的 **「light at night」** 类比。详见 [[intelligence-as-utility]]、[[token-economics]]。
- 用可负担的 token 花费，一个创业者今天能干过去「100 人顶级工程团队」的活——OpenAI 因此认为 **CS183 该重讲**。
- **民主化 vs 集中**：OpenAI 主张推 utility model、把技术推向全世界;即便自己会是集中受益者之一，Altman 说这个集中风险「not something we should tolerate」（见 [[sam-altman]]）。

## compute 侧

- 承认存在**「gigantic compute shortage」**（H100/Blackwell 长约 vs spot 价差约 5×）;只要模型持续变便宜变强，需求就 uncapped → **shortage forever**。
- 前沿实验室「will have to become insurance companies to a degree」。cross-link [[compute-infrastructure]]、[[ai-energy-bottleneck]]、[[value-per-gigawatt]]。

## 与 Anthropic 的关系

[[dario-amodei|Dario Amodei]] 及一批人曾是 OpenAI 早期核心研究团队（scaling laws 正源于此），后因**信任与价值观**分歧出走，2021 年创立 [[anthropic|Anthropic]]。两家如今是模型层的主要对位者。

## 嘉宾视角：从研读 LessWrong 到“为安全牺牲开放，又为加速牺牲安全”（Vitalik，2026-10-29）

在《硅谷101》E257 期（[[silicon-valley-101-vitalik-ea-ai-safety]]）中，主持人与 [[vitalik-buterin|Vitalik Buterin]] 从 [[rationalism-and-ai-safety|理性主义]] 与 [[effective-altruism|EA]] 的视角复盘了 OpenAI 的基因演变：

- **早期理性主义基因与董事会政变**：主持人引述《纽约时报》报道称，OpenAI 早期联创 Greg Brockman 曾每天带领员工研读 Eliezer Yudkowsky 在 LessWrong 上的文章；2023 年底 [[sam-altman|Sam Altman]] 被短暂踢出局再回归，可视为非营利董事会里的 EA/安全派与 e/acc（加速派）之间的一场正面交锋。
- **Vitalik 的一句话判词**：*“他们一开始是 OpenAI，然后为了安全牺牲了开放（Sacrificed openness for safety），接着又为了加速牺牲了安全（Sacrificed safety for acceleration）。”* 2020 年 GPT-3 时以安全为由放弃开源，后来又因妨碍发展速度而放弃多项曾向政府和公众许下的安全承诺（safety pledges）。
- **2024–2026 竞赛节奏变化（Vitalik 口述观察）**：2024–2025 年 OpenAI 一度愿意放慢单一前沿基座模型的节奏，将资源分流到 Sora 视频模型等支线项目（side projects）；直到 2026 年初 [[anthropic|Anthropic]] 推出 Mythos 与 Fable 让外界感觉 Claude 即将反超并赢下比赛，OpenAI 才紧急关停大量支线，重新把全部火力集中回前沿大模型的极限竞速。

## 嘉宾视角：GPT-6 Astra 跨界冲击、万级子 Agent 烧钱解数学题与原始数据采购（硅谷101 E256，2026-10-20）

在《硅谷101》E256 期（[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]）中，主持人泓君与 [[huazhe-xu|许华哲]]、[[zheqing-zhu|朱哲清]]、[[sheng-wang|王晟]] 复盘了 OpenAI 发布 **[[gpt-6-astra|GPT-6 Astra]]**（总裁 Greg Brockman 宣称“AGI 已经到来”）后的产业震荡：

- **“机器人的 GPT 时刻居然是 GPT 自己”**：Astra 发布报告中未提机器人，却直接空降 **RoboDojo** 等机器人仿真评测榜首，使大批传统 Benchmark 失效；但 [[zheqing-zhu|朱哲清]] 指出其在纯 Coding 上仅属渐进升级，定价却高达输入 **$10/M**、输出 **$50/M**（约为 GPT-6 Sol 的 4–5 倍）。
- **单道数学题消耗 2200 万美元 Token**：泓君引述第三方测算指出，当前真正消耗前沿 Lab 算力的不是 C 端消费级 Agent，而是 AI for Science 与未解数学题——OpenAI 内部调用约 **1 万个子 Agent** 攻克**纳维-斯托克斯（Navier-Stokes）方程**，共发送约 270 万条消息、消耗约 **1300 亿输出 Token**，按零售价折算高达 **2200 万美元**。
- **具身数据只买“生肉”与快系统布局**：[[huazhe-xu|许华哲]] 透露传言称，OpenAI 目前在机器人领域只采购未标注的原始数据（嫌外部标错且防自家标注品味泄密）回内部重标；同时传闻 OpenAI 即将发布类似 Jev 但支持图像多模态输入的“系统1”快决策模型。

## 相关页面

- [[sam-altman]]
- [[intelligence-as-utility]]
- [[scaling-laws]]
- [[anthropic]]
- [[compute-infrastructure]]
- [[frontier-systems]]

## References

- [[cs153-sam-altman-scale]] — Stanford CS153「Scale, AGI, and the Future of Everything」
- [[silicon-valley-101-vitalik-ea-ai-safety]] — 《硅谷101》E257 对话 Vitalik Buterin 与 Afra：AI安全背后的哲学思想与有效利他主义（2026-10-29）
- [[silicon-valley-101-gpt6-astra-agent-robotics-pharma]] — 《硅谷101》E256 Agent、机器人与制药，谁先被GPT-6 Astra改写？（2026-10-20）
