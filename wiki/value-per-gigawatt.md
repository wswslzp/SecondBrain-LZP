---
title: "Value per Gigawatt（每吉瓦的价值）"
tags: [ai-infrastructure, tpu, mfu, system-balance, reliability, energy, datacenter, google]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[amin-vahdat]]", "[[google]]", "[[jensen-huang]]", "[[compute-infrastructure]]", "[[ai-energy-bottleneck]]"]
---

# Value per Gigawatt

[[amin-vahdat]]（[[google|Google]]）在 [[cs153-amin-vahdat-gigawatt|CS153]] 提出的中心纪律。主持人 [[anjney-midha]] 把 Amin 框成 **[[jensen-huang|Jensen Huang]] 的对位面**（「the opposite of Jensen」）：Jensen 是需求侧的 showman，Amin 是**供给侧的严谨系统工程师**——不问「你有几个 gigawatt」，只问 **「你从每一美元榨出了多少价值」**。这一页是该纪律的 flagship，串起 value-per-dollar、MFU/system-balance/Amdahl、reliability/goodput/2N、access-over-reliability，以及作为使能机制的 **OCS/torus**。

## value per dollar：把度量搬对地方

- **1 GW ≈ $40–50B**（Amin 报 $40B，别处 $50B，且数字一直往上）。但 Amin 说这些度量「actually broken」：
- > "It's not how much money you spend per gigawatt, it's how much value you deliver per dollar."
- **两个 GW 不等价**：reliability 不同、balance 不同，交付的价值天差地别。花 $40B 建一个 GW，如果不保证每个 node 都可靠、坏了能秒级定位修复，utilization 和 **goodput** 就远达不到应有水平——**「you just wasted a lot of money」**。
- 价值最终 roll up 到 **happy daily active users / paying enterprise customers / developers getting work done**。低层度量（FLOPs、HBM bandwidth、ICI/NVLink bandwidth）都重要，但只是手段。
- > **"If capacity sits idle, that's a bug."**
- **纪律的量化**：Google 内部 **node allocation < 96% 就是 major outage**；对照传闻中 Colossus 的 **~11% MFU**。
- **杠杆是乘性的**：能用一半的钱/容量交付同样能力，很好；**能从一个 GW 交付 2x 价值，就少建几个 GW**——在 energy 是硬约束时这是唯一出路（Google 已在做 **intelligence-per-dollar** benchmark）。
- **agent 时代 = 整体编排**：不是「TPU 越多越好」；若昂贵 TPU 空转、等 agent 在 CPU 上跑 simulation、又要从另一 region 的 storage 取数，就是浪费。要 orchestrate TPU + CPU + storage + data-center network 的整体。

## MFU、system balance 与 Amdahl's Law

- **system balance 才是第一位**：over-fixate FLOPs、却 HBM bandwidth / SRAM / network bandwidth 不够，FLOPs 再多也白搭。**Scaling FLOPs 很容易**（无限 FLOPs 接细管子谁都会）；难的是建一台**跨 10k–100k TPU、比例正确的 balanced coordinated supercomputer**（FLOPs : HBM BW : network BW : SRAM）。
- **Amdahl's Law（1967）**：每 1M instructions/sec 需 ~1 MB/s I/O——**「compute without data is useless」**。近 60 年后，规模从「小」变成 10k–100k node、甚至跨 WAN，I/O 基本成了 **networked I/O**；不按这个 ratio 建，就有「huge amount of FLOPs that aren't doing anything」。
- **为什么今天 MFU 低**：转向 **Mixture-of-Experts / sparse computation** 后，**所有硬件都没建在正确的 balance point**——需要相对 compute 多得多的 **memory bandwidth**，于是大量 FLOPs 空转。
- **100% MFU 不可能**：单核从 7-stage pipeline 到今天 127-stage；跨 100k node，只要某颗 TPU/GPU 的 **cache hit rate 有微小 variation** 就产生 pipeline bubble（在等另一 node 的数据），MFU 掉，且**沿 100k node compound & multiply**。所以「花 $55B 把 GW 建得 balanced/reliable 也值」。

## 可靠性、goodput 与 2N

- **99% 听起来不错，其实一年 down 3.65 天**（可能 unacceptable）；99.9% = 0.365 天；**five nines = 一年 30 秒**——但要 **2N（1+1）冗余供电**，一路 down 立刻切换，代价是**一半电力容量随时闲置**。这也是「data center region 边缘 provision 的电，远多于 compute 实际用掉的电」的原因之一。
- **同步 data-parallel 的脆弱**：serving frontier model 是数百至数千颗加速器，training 是数万颗以上，计算**同步**（all-reduce / all-gather）——**一个 node down，全盘 down**。每个 node 都「special」，承载特定 **expert / layer**，它一走 propagation/serving 就停。
- **对照 web search 的 loose coupling**：web search 设计成任何 rack 随时消失都没人注意（别处有备份数据 + fungible 备用算力）。而 training/serving：
- > "Everything we developed over the past 20, 25 years that said loose coupling, don't worry about individual failures — all that's gone out the window."

## access over reliability（新拐点）

- 历史上企业级服务要 **five nines**、不能 down。**今天 frontier labs 的选择反过来**：
- > "Would you rather have twice the capacity but 3.65 days a year of downtime, or half the capacity at five nines?" —— 「Sign me up, give me more capacity. I'll take the downtime.」
- 因为 **training 关心 throughput 不是 uptime**：一年 down 一两三天无所谓，其余 362 天在训就行。Amin 称之为 **recent / fascinating new phenomenon**（internal 为主，also some external）：**「We will take access over reliability.」** 这直接改变了整套供电与冗余的经济学。

## 光路交换与 torus

作为**使能机制**，Optical Circuit Switch (OCS) 让上面的 reliability 变得可负担：

- **拓扑**：rack 内 64 颗 TPU 用 **copper** point-to-point 直连；rack 之间用 **OCS** 组成 **3D torus**。
- **OCS 是什么**：一块方形芯片，约 **136 面 MEMS 镜**，每面可三维旋转（软件控制的 tiny mirror + tiny motor）。光从 fiber 射入 → 打到镜面 → 按角度反射到**可编程的 output port** → 得到**可编程 topology**，等于「无需人手就能拔插光纤」。
- **用途一（reliability）**：坏了一颗 TPU 会毁掉整个 lattice；OCS 可把该 rack **虚拟移除**、把 spare rack 插进**完全相同位置**，让 torus 重新完整——**秒级、instantaneous failure recovery**（只要有几个 spare rack，平时还能跑小计算）。**这就是 TPU 的真正差异化：更高的 availability。**
- **用途二（storage 就近）**：更上层还有一个 OCS layer，可把镜面**指向某 5 小时任务需要的 storage/cluster**；**Borg 调度任务时顺带调度 topology**（point the mirrors there for the next five hours），**short-circuit 掉多层 electrical packet switch**、省 miles of fiber、按需 direct-connect。
- **为什么是 torus**：ML 头号 collective 是 **all-reduce**（向所有人分发参数、每步带极小计算），torus 是其最优 topology；若做 **all-to-all**，**switched topology（标准 Clos）** 更优——但 model designers 会很聪明地**绕开 topology**。
- **OCS 是 augment 不是 magic bullet**：仍有大量 electrical packet switch，非 per-packet、非 fully fungible；**on-chip 不用、大部分 WAN 也不用**。

## 供应链与规划

- **memory 造不出来**：世界产不出足够 memory（另有「某 frontier lab 用 call options 垄断 memory、业界反弹」的传闻）。
- **lead time = 2–3 年**：net-new GW 钱到位也没用——land、grading、permitting（~6 个月且 indeterminate）、power 全是物理过程。
- **20 年 take-or-pay**：utility 现在要你签 20 年、24/7 全额付款才给一个 GW，因为**电网已无 slack**（过去要 10 MW 随取随到、无需合同）。
- **stranded capacity**：hyperscaler 只要**可扩展**站点 → **<100 MW 并网点被 stranded**；随 **serving（fungible、更小）** 超过 **training（需大块连续容量）**，部分会被自然吸收，但仍需把大电力集中交付到少数地点。
- **planning under uncertainty**：2–3 年前 commit → under-predict（机会留地上）或 over-predict（浪费钱），「predicting perfectly never happens」。**watts + DC space 跨代 fungible**（Gen X / X+1 / X−1 都能装）→ **先 provision watt envelope**；但 chip order 也长 lead，需早下单；新产品/客户随时进来 → **daily replan**。

## TPU 专用化与 GPU 的非零和

- **8i / 8t**：第八代首次拆线——**8i（inference）/ 8t（training）**，一年发两颗、首次专用化。以前一颗 fungible chip 是对的（各只好 ~5%）；如今需求发散到专用化带来 **major uplift**，差异就在 **memory : compute : networking 比例**。通用 CPU 性能/能效增速放缓十年+ → 必须挑大 workload 专用化；TPU 对其领域比 CPU **~100x 高效**，但「can't do anything」。
- **非零和**：Google 大量买/卖/用 **[[nvidia|GPU]]**，「TPU 打败 GPU」不是目标；市场在膨胀，「no winning and losing」，「all the respect in the world for Jensen」。
- **history 注脚**：**TPU v2（2015）** 网络之争由 **Norm Jouppi**（Stanford PhD）一派的 **distributed-shared-memory / point-to-point / not switched** 胜出——[[amin-vahdat]] 凭 45 年 Ethernet 传统押错，「the best thing about Google is how often I get to learn I'm wrong.」

## 与 Jensen / 能源瓶颈的共同线索

- Amin 与 [[jensen-huang|Jensen]] 共享「**compute/energy 是瓶颈**」的判断，但角度互补：Jensen 从**需求侧**讲「1,000× more energy」「tokens/watt」「MFU 可以故意低」（见 [[cs153-jensen-huang-compute]]、[[token-economics]]），Amin 从**供给侧**讲「把每一瓦榨出价值、96% allocation 纪律、OCS/torus/2N」。二者都指向 [[ai-energy-bottleneck]]——[[scott-nolan]]/[[general-matter]] 讲的 **enrichment → nuclear → power → compute** 是同一根链条的更上游。Amin 自认 **energy 是他最没把握的瓶颈**（引 Rich Sutton《The Bitter Lesson》：即便再来个「transformers-prime」5x 高效，compute 仍会被用满，未来 5–10 年+ 都是瓶颈）。
- **anti-zero-sum coda**：vendor 不想要 concentration risk（一客户买断三年产能对 vendor 反而坏；SEC filing 惩罚 1–2 客户集中度），mission-critical 供应链要冗余（earthquakes、geopolitics）。**「There's no such thing as winners and losers — just people who get shit done and who don't.」** Google 参与生态是抬升整个行业和所有用户，「won't happen on the back of any one company」。

## 相关页面

- [[amin-vahdat]]
- [[google]]
- [[jensen-huang]]
- [[nvidia]]
- [[compute-infrastructure]]
- [[ai-energy-bottleneck]]
- [[extreme-co-design]]
- [[accelerated-computing]]
- [[token-economics]]
- [[scaling-laws]]
- [[frontier-systems]]

## References

- [[cs153-amin-vahdat-gigawatt]] — Stanford CS153 Frontier Systems（讲者 Amin Vahdat / Google）
</content>
