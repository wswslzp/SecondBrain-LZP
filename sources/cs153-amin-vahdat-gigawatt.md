---
title: "Stanford CS153 | Amin Vahdat on The Discipline of Delivering Value per Gigawatt"
author: "Amin Vahdat"
date_ingested: 2026-07-19
date_published: 2026-05
tags: [ai-infrastructure, google, tpu, datacenter, energy, systems]
url: "https://www.youtube.com/watch?v=VeTqsCpcDgg"
---

# Stanford CS153 | Amin Vahdat on The Discipline of Delivering Value per Gigawatt

[[amin-vahdat]]（[[google|Google]] VP，掌管内部 ML/systems 基础设施——[[value-per-gigawatt|TPU]]、networking、data center）做客 [[frontier-systems|Stanford CS153]]（playlist #4），主持人 [[anjney-midha]]。主持人开场就把他框成 **「the opposite of Jensen」**：如果说 [[jensen-huang|Jensen Huang]] 是「rapid fire, high-throughput LLM」的 showman，Amin 就是「被训练在 infrastructure discipline 上的三个 frontier model 的蒸馏」——近 **30 年**从业、把每个 token 都压得极实的 systems 老兵。这一讲是 [[cs153-jensen-huang-compute|Jensen 那场]] 的**严谨系统工程对位面**：同样承认「compute/energy 是瓶颈」，但落点不在需求侧的宏大叙事，而在**如何把每一瓦、每一个 node 榨出价值**。

## 核心论点：value per gigawatt

- **1 GW ≈ $40–50B 基础设施**（Amin 报 $40B，别处听到 $50B，且数字一直往上走）。Google 内部纪律极高：**node allocation < 96% 就算 major outage**；对照传闻中 Colossus 的 **~11% MFU**。
- 关键 reframe：**错的度量是「你有几个 GW / 每 GW 花多少钱」，对的度量是「每一美元交付多少价值」**——最终 roll up 到 **happy daily active users / paying enterprise customers / developers getting work done**。
- > "If capacity sits idle, that's a bug."
- > "It's not how much money you spend per gigawatt, it's how much value you deliver per dollar."
- 若能用一半的钱、一半的容量交付同样能力，很好；**若能从一个 GW 交付 2x 价值，就少建几个 GW**——在 energy 是硬约束时，这是唯一可持续的打法。Google 已在做 **intelligence-per-dollar** 的 benchmark 并对外发表。
- **agent 时代是整体编排问题**：不是「TPU 多就行」；若昂贵的 TPU 空转、等一个 agent 在 CPU 上跑 simulation、又要从另一个 region 的 storage 取数据，那就是浪费。要 orchestrate TPU + CPU + storage + data-center network 的整体。
- 完整框架见 flagship 概念页 [[value-per-gigawatt]]。

## 系统平衡与可靠性

- **System balance（Amdahl's Law）**：引 Amdahl（1967）——每 1M instructions/sec 需 ~1 MB/s I/O，「compute without data is useless」。今天 I/O 基本是 **networked I/O**。Scaling FLOPs 很容易；难的是在 **10k–100k TPU** 上建一台 **balanced coordinated supercomputer**（FLOPs : HBM bandwidth : network bandwidth : SRAM 的正确比例）。over-fixate FLOPs 就是浪费钱。
- **为什么 MFU 低**：转向 **Mixture-of-Experts / sparse computation** 后，今天所有硬件都没建在正确的 balance point——**需要相对 compute 多得多的 memory bandwidth**，于是大量 FLOPs 在空转。
- **100% MFU 不可能**：单核 7-stage → 现在 127-stage pipeline；跨 100k node，只要某个 TPU/GPU 的 cache hit rate 有微小 variation 就产生 pipeline bubble，等另一个 node 的数据 → MFU 掉，且**沿 100k node 复合、相乘（compound & multiply）**。
- **Reliability & goodput**：99% availability = 一年 down **3.65 天**（可能 unacceptable）；99.9% = 0.365 天；**five nines = 一年 30 秒**，但要 **2N（1+1）冗余供电**，意味着**一半电力容量随时闲置**。
- **同步 data-parallel 的脆弱**：serving 一个 frontier model 是数百至数千颗加速器，training 是数万颗以上，计算是**同步**的（all-reduce / all-gather）——**一个 node down，全盘 down**。每个 node 都「special」（承载特定 expert / layer），不像 web search 那样任何 rack 消失都没人注意（有备份数据 + fungible 备用算力）。
- > "Everything we developed over the past 20, 25 years that said loose coupling, don't worry about individual failures — all that's gone out the window."
- **access-over-reliability 的新拐点**：历史上企业级服务要 five nines；现在 frontier labs 说 **「给我 2x 容量，一年 3.65 天不可用我认」**——training 关心的是 throughput 不是 uptime。「We will take access over reliability.」（internal 为主，also some external，Amin 称之为 recent/fascinating new phenomenon。）

## 光路交换与 torus

- **rack 内**：64 颗 TPU 之间是 **copper**、point-to-point 直连（「that is the right technology」）。**rack 之间**：**Optical Circuit Switch (OCS)** 组成一个 **3D torus**。
- **OCS 是什么**：一块方形芯片，约 **136 面 MEMS 镜**，每面可在三维旋转（软件控制的 tiny mirror + tiny motor）。光从 fiber 射入 → 打到镜面 → 按旋转角反射到指定 output port → 得到一个**可编程 topology**。
- **用途一（reliability）**：某 rack 坏了，OCS 可把它**虚拟移除**、把一个 spare rack 插进**完全相同的位置**，让 torus 重新完整——**秒级、无需人手拔插光纤**，实现**instantaneous failure recovery**（只要有几个 spare rack「lying around」，spare 平时还能跑小计算）。这正是 **TPU 的真正差异化**：更高的 availability。
- **用途二（agent/storage 就近）**：更上一层还有一个 OCS layer，可把镜面**指向某个 5 小时任务需要的 storage/cluster**；Borg 在调度任务时顺带调度 topology（point the mirrors over there for the next five hours），**short-circuit 掉多层 electrical packet switch**、省下 miles of fiber，等于按需 direct-connect。不是 per-packet、不是 fully fungible，但对「已知会跑 5 小时、已知要哪块 storage」的场景刚好够用。
- **为什么是 torus**：ML training 头号 collective 是 **all-reduce**（向所有人分发参数、每步带极小计算），torus 是 all-reduce 的最优 topology；若做 **all-to-all**，则 **switched topology（标准 Clos）** 更优——但 **model designers 会很聪明地绕开 topology**。OCS 是 **augment 不是 magic bullet**：仍有大量 electrical packet switch，**on-chip 不用、大部分 WAN 也不用**。

## 供应链与规划

- **memory 造不出来**：世界产不出足够 memory（还有「某 frontier lab 用 call options 垄断 memory、业界反弹」的传闻，3–4 个月前的事）。
- **lead time = 2–3 年**：net-new GW 有 2–3 年交期，钱到位也没用——land、grading、permitting（~6 个月且 indeterminate）、power 都是物理过程。
- **20 年 take-or-pay**：现在去 utility 要一个 GW，对方要你签 **20 年、24/7 全额付款**的合同，因为**电网已无 slack**；过去要 10 MW 无需合同、随取随到。
- **stranded capacity**：hyperscaler 只要**可扩展**的站点，于是 **<100 MW 的并网点被 stranded**。但 100 MW 级加总也不是需求主体；随着 **serving（更 fungible、更小）** 超过 **training（需大块连续容量）**，部分 stranded 会被自然吸收，但仍需把大电力集中交付到少数地点。
- **planning under uncertainty**：2–3 年前 commit 容量 → 要么 under-predict（把机会留在地上）、要么 over-predict（浪费钱），「predicting perfectly never happens」。**watts + data-center space 跨代 fungible**（Gen X / X+1 / X−1 都能装），所以**先 provision watt envelope**；但 chip order 也是长 lead time，得早下单。新产品/新客户随时进来 → **daily replan**。
- **depreciation 6 年**（少数 5 年）：老芯片不会 obsolete——H100/H200/B200/GB200 即便 Rubin 已发布仍**需求旺盛**。

## 金句

- > "It's not how many gigawatts you have, it's how much capability and value you're delivering to your users." 
- > "If capacity sits idle, that's a bug."
- > "We will take access over reliability."
- > "Scaling FLOPs is easy. Building a coordinated supercomputer that scales to 10,000, 100,000 TPUs with the right balance point — super hard."
- > "100% MFU is not possible."
- > "The best thing about Google is how often I get to learn something [new]." —— 讲 TPU v2（2015）网络之争：他凭 45 年 Ethernet 传统坚信用 Ethernet，结果 **[[value-per-gigawatt#TPU 专用化与 GPU 的非零和|Norm Jouppi]]** 一派的 distributed-shared-memory / point-to-point 赢了，「I got it wrong. I learned something new.」
- > "There's no such thing as winners and losers in the real world. They're just people who get shit done and who don't."
- > "I view what we're doing at Google as participating in an ecosystem to lift the entire industry... It's not going to happen on the back of any one company."

## 其他要点

- **TPU 8i / 8t**：第八代首次拆线——**8i（inference）/ 8t（training）**，一年发两颗芯片、首次专用化。以前一颗 fungible chip 是对的（各只好 ~5%）；如今需求发散到**专用化带来 major uplift**，差异就在 **memory : compute : networking 比例**。通用 CPU 性能/能效增速已放缓十年+ → 必须挑大 workload 专用化；TPU 对其领域比 CPU **~100x 更高效**，但「can't do anything」。
- **TPU vs GPU 不是目标、非零和**：市场在膨胀，「no winning and losing」；Google 大量买/卖/用 GPU，「all the respect in the world for Jensen」，会打电话向他请教，只是打不同 domain/客户。
- **anti-zero-sum coda**：vendor 不想要 concentration risk（一个客户买断三年产能对 vendor 反而坏；SEC filing 也惩罚 1–2 客户集中度）；mission-critical 供应链要冗余（earthquakes、geopolitics）。Google 参与生态是**抬升整个行业和所有用户**。
- **Colossus → Anthropic / Cursor**：SpaceX/xAI 的 Colossus 富余算力租给 [[anthropic|Anthropic]] 和 Cursor——**inference 需求爆炸**；coding agents「4–5 个月前才 explode，没人预测到这个量级」，没人有 lead time 备货。
- **robotics**：最好的现实例子是 **Waymo**；safety 是首要、latency 关键 → 倾向 locality 与「single-threaded」本地计算，**规模远小于 datacenter**（别指望 1000 miles 外的 20k TPU）。
- **energy 是他最没把握的瓶颈**：引 Rich Sutton《The Bitter Lesson》；transformers 比 LSTM ~5x 高效，但即便再来个「transformers-prime」再 5x，compute 仍会被用满——未来 5–10 年（他倾向更久）compute 都是瓶颈。US 应多押 wind/solar/battery，space/floating DC 是 5–10 年的 portfolio 选项。
- **社区责任**：PUE、water-vs-power 的 10% trade-off（缺水社区选不耗水但低 10% 能效的设计）、**gigawatt 级 demand response**（电网最紧张那一两天还回 100 MW）——data center 要做「community/grid asset」，目标是 **optimal scaling** 而非 capacity at any cost。
- **origin**：6 岁在伊朗看到杂志封面上的电脑就决定当程序员（当时没碰过电脑）；教授 12–13 年（Duke）后 2010 年加入 Google——当时他与 CEO Eric Schmidt 之间 **7 个人全有 CS PhD**。

## 关联页面

- [[amin-vahdat]] — 人物
- [[google]] — 公司（infra / TPU / Gemini / DeepMind）
- [[value-per-gigawatt]] — **本讲旗舰概念页**
- [[jensen-huang]] / [[nvidia]] — 被 Amin 反复对照的「对位面」与非零和伙伴
- [[compute-infrastructure]] / [[ai-energy-bottleneck]] — 需求/电网/能源瓶颈的共同线索
- [[extreme-co-design]] / [[accelerated-computing]] / [[token-economics]] / [[cuda]] / [[scaling-laws]]
- [[anthropic]] / [[sam-altman]] / [[openai]] — 生态中的 frontier labs
- 系列同源：[[cs153-frontier-systems]] / [[frontier-systems]]（[[anjney-midha]] 主讲）、[[cs153-jensen-huang-compute]]、[[cs153-scott-nolan-energy]]

## References

- Stanford Online / CS153 Frontier Systems, YouTube: https://www.youtube.com/watch?v=VeTqsCpcDgg
- Raw transcript: `raw/Stanford CS153 Frontier Systems  The Discipline of Delivering Value per Gigawatt.md`
</content>
</invoke>
