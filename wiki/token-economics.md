---
title: "Token 工厂经济学（AI 作为营收引擎）"
tags: [nvidia, ai, economics, tokens, ai-factory, revenue, concept]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[nvidia]]", "[[compute-infrastructure]]", "[[ai-factory]]", "[[tasks-vs-jobs]]", "[[value-per-gigawatt]]", "[[amin-vahdat]]", "[[intelligence-as-utility]]", "[[sam-altman]]"]
---

# Token 工厂经济学（AI 作为营收引擎）

[[jensen-huang|Jensen Huang]] 论证 [[nvidia|NVIDIA]] 增长「inevitable」、乃至可达 **$3T 营收 / $10T 市值**的经济学框架。核心是把「计算机」从「存东西的仓库」重新定义为「产 token 的工厂」。

> "I think that NVIDIA's growth is extremely likely, and in my mind, inevitable."

## ⚠️ 术语澄清：两种「AI factory」

本页的「AI factory」是 **Jensen 意义上的**——**数据中心即营收工厂**（factory-as-revenue-engine）。这与本库既有的 [[ai-factory]]（[[anjney-midha]] 意义上的 **AI 模型生产管线**：pre-training / mid-training / post-training / deployment + RL）是「AI factory」一词的**两种不同含义**：

| | 本页（Jensen） | [[ai-factory]]（Midha/CS153） |
|---|---|---|
| 指代 | 数据中心作为产 token 的营收工厂 | 训一个前沿模型的制造管线 |
| 产出 | token（可售商品） | 模型（含 trainers/tutors/labelers 的人力层） |
| 视角 | 商业/宏观经济 | 工程/研究流程 |

两者不冲突，可视为「工厂造出的模型」在「工厂化数据中心」里产出 token——请勿混用。

## 两大根本转变

### (1) Retrieval-based → Generative computing

> "We went from a retrieval-based computing system to a generative-based computing system."

- **旧世界**：人类**预录**内容（写好、录好、画好，放进文件/网页），再用 recommender / smart filter「检索」给你。计算机本质是文件检索系统——**需要大量存储**。
- **新世界**：AI 计算机 **contextually aware**，必须**实时处理并生成 token**，grounded on new insight。**需要多得多的计算**。
- 唯一会让它「倒退」的情形，是这种生成式计算被证明「not effective」——但 Jensen 说过去五年给他的信心超过之前十年，所以不会倒退。

### (2) Warehouse → Factory

> "Computers were largely a warehouse. We're now building factories. Warehouses don't make much money. Factories directly correlate with the company's revenues."

计算机不仅**做事的方式变了**，它在世界上的**用途也变了**——从存储单元变成**营收/利润生成单元**（product generation unit）。

## Token 作为产品

- **像 iPhone 一样分层**：free tokens、premium tokens、以及中间若干档。
- **智能是可标价、可扩展的产品**：高智能 token 用于专门用途，有人愿付高价——「somebody's willing to pay **$1,000 per million tokens** is just around the corner. It's not if, it's only when.」
- **核心指标 = tokens/sec/watt**：NVIDIA 的整机价格在涨，但 token 生成效率涨得更快，所以 **token 成本每年降一个数量级**（能效直接决定工厂营收——见 [[extreme-co-design]]）。
- **世界 GDP 中用于计算的比例将 100×**：因为计算机从 storage unit 变成 product generation unit，叠加 AI 带来的生产力跃升、新药/新产品/新服务，Jensen「absolutely certain the world's GDP is going to accelerate」。

## $10T / $3T revenue 论证

- NVIDIA 是史上最大的计算机公司，这本身就该引出「why?」——答案就是上述两大转变。
- $3T 营收「not limited by any physical limits」；供应链负担由 **200 家公司**分摊，剩下的问题只是「能量够不够」（「surely we will have the energy」）。
- **最反直觉的一点**——NVIDIA **不在抢市场份额**：

> "NVIDIA is not in the market share business. Almost everything that I just talked about doesn't exist... there's nobody I could take share from. The challenge for the world is the imagination of the future."

- 若是 $10B 公司抢 10% 份额，股东容易想象；但 NVIDIA 的天花板难以想象，因为它要开创的市场**还不存在**——难的是 **imagination**，不是执行。
- 反面案例都违反 first-principles：曾有 CEO 断言「fabless 半导体公司理论上不可能超过 $1B」，又有人说「你永远超不过 $25B」——「those aren't first-principled thinking.」

## agents = "the iPhone of tokens"

Token 工厂需要「杀手级应用」来引爆需求，而 Jensen 认为它已经到来：

> "The iPhone of tokens arrived. It is the fastest-growing application in history. It went straight up."

这个「iPhone」不是某个具体产品，而是 **agents**（OpenClaw 是其代表）。agents 会 spawn 大量 sub-agents（对应 [[scaling-laws]] 的 agentic scaling law），从需求侧指数级放大 token 消耗 → 需要指数级更多 token 工厂。安全侧的 two-of-three rights 见 [[nvidia]]。

## CS153 补充：MFU 批判（度量的艺术）

[[jensen-huang|Jensen]] 在 [[cs153-jensen-huang-compute|CS153]] 给出一个反直觉的度量观（MFU = model flops utilization）：

> "I'd like to be at low MFU all the time."

- 缘由：想「聪明到 overprovisioned」以避开 **Amdahl's law**——数据中心里 flops / memory bandwidth / memory capacity / network 总有一个是瞬时瓶颈，要按 **peak 而非 base** 过量供给。
- **「flops are cheap」**——H100 涨价不是因为 flops，而是 bandwidth / architecture /「everything else」。正确度量是 **tokens per watt > flops**；对 decode，产 token/watt 的最大单一因素是 **NVLink-72 的 aggregate bandwidth**，此时可 **disaggregate prefill/decode**，用「极低 MFU 交付极高 tokens/watt」。
- **「not all tokens are born equal」**（coding token 更值钱）→ 需要严肃的 eval、构建「an index of different intelligences」，而非优化 flops（「flops is too contrived… necessary, not sufficient」）。

## 与就业的联系

Token 工厂经济学的另一面是「谁来消费这些 token、谁的工作被改变」。Jensen 的立场——**purpose ≠ tasks**、程序员从 3000 万增至 10 亿、放射科医生不减反增——是对 [[tasks-vs-jobs]] 中 [[dario-amodei|Dario]] 观点的直接对位。详见 [[jensen-huang]] 与 [[jensen-huang-lex-fridman]]。

## CS153 补充：value per dollar 与 tokens-as-utility

[[amin-vahdat]]（[[value-per-gigawatt]]）把度量进一步收紧到 **value per dollar**（而非 FLOPs 或 gigawatts）——这与本页的 **MFU 批判**、以及 **system balance**（按 peak 过量供给、别让瓶颈资源空转）直接同源：闲置的产能「is a bug」。需求侧则由 [[sam-altman]] 的 **tokens-as-utility** 框架补齐——消费者直接以 **token** 计量思考、底层硬件被彻底抽象掉，智能像水电一样按量取用（见 [[intelligence-as-utility]]）。两者一供一需，都指向「token/价值」而非「flops」才是正确的经济单位。

## 相关页面

- [[nvidia]]
- [[compute-infrastructure]]
- [[ai-factory]]
- [[tasks-vs-jobs]]
- [[extreme-co-design]]
- [[scaling-laws]]

## References

- [[jensen-huang-lex-fridman]] — Lex Fridman Podcast #494（2026-03-24）
