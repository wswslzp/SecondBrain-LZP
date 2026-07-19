---
title: "Stanford CS153 Frontier Systems | Jensen Huang from NVIDIA on the Compute Behind Intelligence"
author: "Stanford CS153（讲者 Jensen Huang / NVIDIA）"
date_ingested: 2026-07-19
date_published: 2026-05
tags: [nvidia, jensen-huang, accelerated-computing, compute, codesign, moores-law, mfu, energy, open-source, export-controls, cs153]
url: "https://www.youtube.com/watch?v=tsQB0n0YV3k"
---

# Stanford CS153 | Jensen Huang on the Compute Behind Intelligence

[[jensen-huang|Jensen Huang]]（[[nvidia|NVIDIA]]）回到 [[frontier-systems|Stanford CS153]] 的 guest 对谈（现场戏称「AI Coachella」，主持人为课程讲师 [[anjney-midha]] 一侧）。与 [[jensen-huang-lex-fridman|Lex Fridman #494]] 的「技术+商业+人生」全景长谈相比，这一场是**对着 Stanford 计算机系学生**讲的，因此在三个方向上更「上游」、更具体：

1. **面向学生的角度**：codesign 的 **RISC / John Hennessy 血统**、教育应如何用 AI 重写、职业与「suffering」、大学的 compute crunch 与「$40B endowment 该怎么花」。
2. **对 accelerated computing / AI factory 的具体讲法**：为什么通用计算走到尽头、Hopper→Blackwell→Vera Rubin→Feynman 四代硬件如何随 workload 共演化。
3. **新数据 / 新比喻 / 新立场**：MFU 批判与「unit of intelligence per watt」、能耗「1,000×」、芯片出口管制与「everybody should have AI, nobody should have nuclear bombs」。

> 本页只标注**相对已有页面新增或更强调**的内容；与 Lex #494 重合的部分（moat=CUDA install base、四条 scaling laws 的完整版、太空数据中心、领导力哲学、$3T/$10T 论证）见 [[jensen-huang-lex-fridman]] 与对应 wiki 页，不再重复。

## 本讲要点

### 1. 计算 60 多年来首次被重新发明（学生视角的开场）
- 「computing is being reinvented for the first time... in about 60-plus years」——自 **IBM System/360（64 年）** 以来计算模型基本未变；Jensen 学架构的第一本书就是 System/360 手册。
- **prerecorded → generated**：旧计算是预录内容的检索；新计算实时生成、contextually relevant、能响应 intention。
- **on-demand → continuously running**：「on-demand」一词是这代人为分时/云计算发明的；agentic 系统则是**持续运行**的计算机——「what happens in a world where computers are continuously running?」
- 一句很干净的定义：**「thinking is generating tokens that you consume internally；tool use is generating tokens that you consume externally.」** GPT 出现后「thinking is just around the corner」是可预测的。
- 详见新概念页 [[accelerated-computing]]（本讲最集中的新内容落点）。

### 2. Codesign 的 Stanford 血统（新增，vs [[extreme-co-design]]）
- 旧世界把计算分层抽象：做微处理器的做微处理器、做编译器的做编译器、做语言的做语言。
- **RISC 的美 = John Hennessy 的遗产**：让编译器与微处理器架构「harmoniously codesign」——「a simpler machine, codesigned with a compiler, creates better performance than two systems that were optimized individually.」「That's very Stanford.」
- 由此推到「**post general-purpose computing**」：为什么每个问题都要用通用机器解？对 graphics / molecular dynamics / quantum chemistry / fluid dynamics / mesoscale multiphysics / deep learning 这类极端计算密集问题，就该同时优化算法+系统+编译器+框架+芯片架构。
- **量级上的新 nuance**：若只吃通用微处理器的自然 scaling，Moore's Law 好日子是 100×/10yr；但 Dennard scaling 约十年前就没了，所以**通用路线实际大概只有 ~10×**；NVIDIA 靠 codesign 拿到 **1,000,000×/10yr**（「somewhere between 100,000x and 1 million x，数字这么大已经无所谓」）。
- 比喻：能以光速旅行则「住哪都无所谓」；NY→CA 十分钟则「社会一切都变」；**compute 快一百万倍，则「everything about computing changed」**——于是 AI 研究者说「why don't we just take all of the internet」。

### 3. 教育应如何用 AI 重写（新增，Stanford 特有）
- AI 不只是课程内容，更该是**学习工具**：预录教科书追不上 AI 实时生成的知识。
- Jensen 的用法：「I can't learn anymore without AI」——读完一篇 paper 让 AI 去读它引用的一堆相关 paper → 变成「super researcher」→ 像对待专属研究员一样与这篇 paper 交互。「summarize 的过程中 AI 学到了很多」。
- 但 **first principles 不变**：Mead & Conway 仍然扎实；他在 Stanford 时已在 AMD 设计微处理器，「实践 + 第一性原理同时学」收获最大。

### 4. Open models 的具体动机与新数据（补充 [[nvidia]]）
- **NVIDIA 用 Anthropic + OpenAI 的 token 比几乎任何人都多**；**100% 工程师已 agentically supported**。强烈建议学生用 frontier 模型——「Claude is a product, and **Claude Code is a whole harness** around it；不太可能去 GitHub 下个开源的就能一样好。」（→ [[claude-code]]）
- 为什么还大力做 open models：语言模型是「the codification of our intelligence」；AI 的本质是**学习信息的 representation / meaning / structure**——学会 representation 就能 manipulate、generate、put to use，因此要对化学、蛋白、基因、物理、机器人做同样的事（但结构与维度不同、训练策略也不同）。
- **五大自研 foundation 域**：Nemotron（语言）、**BioNemo**（生物）、Alpamayo（自动驾驶）、**Groot**（人形机器人 articulation）、**climate science（mesoscale multiphysics）**——因为这些领域的科学家没有 scale 与技术去自建 foundation model，NVIDIA 先造「第一件 artifact」以激活整条下游产业。
- 小语言动机：Swedish 及另外 ~230 种语言不会成为别人的高优先级——「human intelligence, no matter the size of your population, somebody should care.」
- **Alpamayo = language model fused with a world model + human priors**：能像人一样带 human priors 推理，所需训练数据大减——「only experienced a few million miles, not billions」，却是世界最有效的自动驾驶系统之一。
- **Open = safety**：「you can't defend against a black box, and you can't secure a black box.」透明系统才能被 researcher interrogate。cybersecurity 打法不是「7.0 对 8.0 对 9.0」的军备竞赛，而是用 **Nemotron Nano** 训出「swarms of cheap AIs」组成「a giant dome」把威胁团团围住。

### 5. MFU 批判与「unit of intelligence per watt」（新增，最技术的一段）
- 缘起：xAI Memphis 集群传出 **11% MFU**（model flops utilization）。学生问怎么提高利用率。
- Jensen 反直觉：「**I would like to be at low MFU all the time.**」原因——想「so smart that I'm overprovisioned」以避开 **Amdahl's law**；数据中心里 flops / memory bandwidth / memory capacity / network capacity 在任意时刻总有一个是瓶颈；要按 **peak 而非 base** 过量供给，否则短暂的 100% MFU 窗口会被拉长成长时间。
- 「**flops are cheap**」；H100 涨价不是因为 flops，而是 bandwidth / architecture / 「everything else」。
- 正确的度量不是 horsepower 式的 flops，而是 **performance / tokens per watt**——「tokens per watt is more than flops」。对 decode，产 token/watt 的**单一最重要因素是 NVLink-72 的 aggregate bandwidth**；此时 MFU「incredibly low」因为主要是 decode、prefill 很少，而且可以 **disaggregate prefill/decode**——「我用极低 MFU 交付了极高 tokens/watt」。
- 但「**not all tokens are born equal**」（coding token 比别的更值钱），所以必须设计**真正严肃的 eval**、去构建「an index of different intelligences」——「flops is too contrived... 如果那么容易我就不用坐在这了」。overfit 单一问题会因市场太小养不起 R&D，good-at-everything 又退化成通用机——「writing that balance is artistry. That's what I do for a living.」

### 6. 四代硬件随 workload 共演化（补强 [[extreme-co-design]] 的 roadmap）
- **Hopper = pretraining**：当年最贵超算 $350M，NVIDIA 却决定造 multibillion-$ 系统——「你在为一个 precisely zero 的市场造东西」，纯 first-principles 押注，结果对了。
- **NVLink72 / Grace Blackwell = inference（decode）**：decode 需要的 memory bandwidth 远超单芯片 → 「gang up 72」→ **世界第一台 rack-scale computer**；两年内比上一代快 **50×**（Moore's Law 同期只有 2×）。
- **Vera Rubin = agents**：agent 要 load 大量 memory（long-term memory 进 storage，storage 直连 fabric、直入 GPU，不走网络拷贝）；tool 跑在 CPU 上，而 multibillion-$ 的 GPU 超算在等这一颗 CPU → 需要极低延迟 → 造了 **Vera**（multi-core single-threaded 性能之王）。
- **Feynman = swarms of agents**：未来是 agents → subagents → subagents 的 swarm，「what kind of computer does that manifest」正是 Feynman 要回答的。
- 方法论：「你要对 computing pattern 有 mental model，再造能跑它的系统。」

### 7. 能源（补充 [[compute-infrastructure]] / [[token-economics]]）
- 可控的一环 = **energy efficiency**：tokens/watt 已提升 **50×** 且会持续复利。
- **总量新数据**：未来计算所需能源「likely probably 1,000 times more than we currently have」，且「off by a couple of orders of magnitude 我也不惊讶」——因为计算将永远是 generated + continuous。
- 立场：现在是**史上最好的可再生能源投资窗口**——过去需政府补贴建太阳能/核电，如今「market forces are so strong, we'll pay you to do it」，正好借机升级 archaic grid。

### 8. 芯片出口管制 / 对手国家（新增政策立场）
- GPU 用于 video games、送酱油、**medical imaging**（「NVIDIA is in every single medical imaging system in the world」）——「a billion people have NVIDIA GPUs；I advocate them to my family。**I don't advocate atomic bombs to anybody.** 所以拿 GPU 类比原子弹是 stupid，从这起步就 finish 不了一个 thought。」
- 「why compete in foreign countries, you'll lose anyway」的逻辑站不住——「你都这么想那早上何必起床」；竞争 serves markets、enhances your company。
- 剥夺某些国家的**通用计算**（NVIDIA 已是 general purpose computing company），只为一两家公司获益，毫无道理。**电信业前车之鉴**：美国当年用同样论证把电信基础技术「policied out of our country」，如今已无本土电信核心技术。
- 反 AI 末日论：把 singularity/科幻恐惧当公开事实宣讲是 irresponsible——「It is not true that we have no idea how these systems work... It is not true.（反复强调）」总结句：**「Everybody should have AI. Nobody should have nuclear bombs.」**

### 9. 大学的 compute crunch（新增，Stanford 特有的犀利交锋）
- 学生逼问：美国 compute-constrained，独立团队/初创/大学都拿不到 compute，是否该本土优先。Jensen：「Absolutely.（该）」「Absolutely not.（没发生）」——「There's plenty of chips. If the president of Stanford places an order, I promise you, I'll deliver it.」
- 真问题不是缺芯片，而是**体制不再为大学交付大规模 compute**：各系各自拉 grant、没人合并，单笔 grant 不够买「用时要很猛」的共享算力；世界从中心化计算搬去了人手一台笔记本。
- 用他标志性的「赋能式归因」：「**It's absolutely your (Stanford's) fault**」——因为「当谁有错，你就赋能了谁去解决它」。建议：改预算方式、聚合建**校级共享超算**（「build yourself a linear accelerator, just like Stanford has done in the past」）；「$40B endowment 我会立刻切 $1B 做成 cloud service，让每个学生每个研究者都有 AI 超算」；但要提前 plan（「买 $1B 的番茄不能空手走进杂货店」）。

### 10. 职业 / suffering / 预测方法（补充 [[jensen-huang]]）
- **别只追热爱**：「choose what you love」门槛太高，大多数人不知道自己爱什么。「my job used to be cleaning toilets and bussing tables」——无论给我什么工作我都做到最好。
- **90% 的工作是苦的**：「there's not one CEO... zippity doo dah from morning to night；我真正喜欢的只有 10%，其余 90% 我 literally suffer through it。」但主动求些 pain/suffering → 练出 resilience 这块肌肉，关键时刻才顶得住。「Don't wake up with a loser mindset.」
- **预测/forecasting 方法**：`what am I observing?` → 回到 first principles → `so what? is this a big deal?`（AlexNet：Alex/Ilya/Hinton 一个神经网络一举碾压几十年的 CV → big deal）→ `how far can you take it? what else can you solve?` → 建 mental model of future → 定位公司 → work backwards。把结果分成「will likely happen / will absolutely happen / may happen」。**「the opportunity cost of pursuing a strategy is the real cost」**——要提升 optionality、「get the journey to pay for itself」。
- **最大的错误**：第一代产品架构「completely wrong」（curved surfaces 而非 triangles、无 z-buffer、forward texture mapping、无 floating point）——但逼出了 strategic genius。真正的战略错误是**进军 mobile**：做到 $1B 又在 3G→4G 被 Qualcomm 的 modem 完全锁死、归零；但把那身**极致低功耗**本事转去了当年还不存在的 robotics——「**Thor 是那颗 mobile 芯片的 great-great-great-great grandson**」。

## 与 Lex #494 的异同（速查）

| 主题            | Lex #494（已入库）                                                     | CS153（本讲新增/更强调）                                                                                                             |
| ------------- | ----------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Codesign      | 跨 stack + 超越 CPU/GPU + anticipate hardware（[[extreme-co-design]]） | **RISC/Hennessy 血统**、post-general-purpose、通用路线实际只 ~10×                                                                      |
| Moore/Dennard | 1M× vs 100×                                                       | 补「Dennard 死后通用只剩 ~10×」的 nuance                                                                                              |
| 硬件 roadmap    | Grace Blackwell → Vera Rubin + Rock                               | **完整四代**（Hopper/pretraining → NVLink72/inference → Vera Rubin/agents → **Feynman/swarms**）+ $350M「marketplace of zero」      |
| 度量            | tokens/sec/watt（[[token-economics]]）                              | **MFU 批判**、「low MFU on purpose」、disaggregate、「index of intelligences」                                                       |
| 能源            | 消化电网闲置容量                                                          | **「1,000× more energy」**、可再生能源投资窗口                                                                                          |
| Open source   | Nemotron 三动机（[[nvidia]]）                                          | **NVIDIA 用最多 Anthropic/OpenAI token、100% 工程师 agentic**、五大 foundation 域、Alpamayo world-model fusion、Nemotron Nano cyber-dome |
| 政策            | China/主权 AI                                                       | **出口管制**、电信前车之鉴、「everybody should have AI」、反末日论                                                                             |
| 教育/大学         | —（几乎没有）                                                           | **AI 重写课程**、大学 compute crunch、endowment→$1B compute                                                                         |
| 就业/人生         | purpose≠tasks、放射科医生、intelligence is a commodity                   | suffering→resilience、别只追热爱、forecasting 三档、mobile→robotics 复盘                                                                |

## 关键实体 / 概念页
- [[jensen-huang]] — 人物与领导力哲学
- [[nvidia]] — 公司、moat、开源、供应链
- [[accelerated-computing]] — **本讲新建**：加速计算 / 后通用计算时代
- [[extreme-co-design]] — 协同设计方法（本讲补 RISC 血统与四代 roadmap）
- [[cuda]]、[[token-economics]]、[[scaling-laws]]、[[compute-infrastructure]]、[[frontier-systems]]
- 系列同源：[[cs153-frontier-systems]]（[[anjney-midha]] 主讲）、[[jensen-huang-lex-fridman]]

## References
- Stanford Online / CS153 Frontier Systems, YouTube: https://www.youtube.com/watch?v=tsQB0n0YV3k
- Raw transcript: `raw/Stanford CS153 Frontier Systems  Jensen Huang from NVIDIA on the Compute Behind Intelligence.md`
