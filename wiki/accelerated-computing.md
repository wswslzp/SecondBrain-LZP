---
title: "Accelerated Computing（加速计算 / 后通用计算时代）"
tags: [nvidia, accelerated-computing, compute, moores-law, codesign, concept]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[extreme-co-design]]", "[[nvidia]]", "[[cuda]]", "[[scaling-laws]]", "[[compute-infrastructure]]", "[[amin-vahdat]]", "[[value-per-gigawatt]]"]
---

# Accelerated Computing（加速计算 / 后通用计算时代）

[[nvidia|NVIDIA]] 的立身之本。如果说 [[extreme-co-design]] 回答的是「**怎么**跨整条 stack 协同优化」，那么 accelerated computing 回答的是更上游的问题：「**为什么**要加速、**为什么通用计算走到了尽头**、**该加速哪些问题**。」这一页整理 [[jensen-huang|Jensen Huang]] 在 [[frontier-systems|CS153]] 对 Stanford 学生给出的这套「premise 级」论证（见 [[cs153-jensen-huang-compute]]）。

## 计算 60 多年来首次被重新发明

> "Computing is being reinvented for the first time... in about 60-plus years."

- 自 **IBM System/360（64 年）** 以来，计算的 mental model、架构、写程序/跑程序/上市的方式基本没变（Jensen 学架构的第一本书就是 System/360 手册）。PC→互联网→移动→云都没改变**计算模型**本身。
- 这次真正变了两条轴：
  - **prerecorded → generated**：旧计算是「检索预录内容」（图像/视频/软件都是事先录好的）；新计算**实时生成**，因而 contextually relevant、能响应 intention。
  - **on-demand → continuously running**：「on-demand」是这代人为分时/云计算发明的词；[[scaling-laws|agentic]] 系统则**持续运行**——「what happens in a world where the computers are continuously running?」
- 一个干净的定义：**「thinking is generating tokens you consume internally；tool use is generating tokens you consume externally.」**

## Codesign 的 Stanford 血统（RISC / Hennessy）

加速计算的方法论根，来自 Stanford 自己的遗产——**RISC**：

- 旧世界把计算分层抽象：做微处理器的、做编译器的、做语言的，各干各的。
- **John Hennessy 的 RISC 之美**：让编译器与微处理器架构「harmoniously codesign」。若把微处理器单独优化到极致，往往**难以编译**；换一个更简单、对编译器暴露 simplicity 的指令集，编译器能生成更好的代码。

> "A simpler machine, codesigned with a compiler, creates better performance than two systems that were optimized individually. That's very Stanford."

- 但 first principles 不变：**Mead & Conway** 的方法论今天仍然扎实；只是 constant current/power density 那套 iso-scaling 已被耗尽——「none of that is iso anything anymore.」（协同设计如何延展到芯片以外的 power/cooling/rack/pod/data center，见 [[extreme-co-design]]。）

## 通用计算的尽头（Moore's Law / Dennard scaling）

> "Why is it that every problem in computer science would be solvable by a general purpose instrument?"

- **Moore's Law** 好日子：2×/18 个月 = 10×/5 年 = **100×/10 年**，其底层是 **Dennard scaling**——但 Dennard 约**十年前就没了**，此后一直靠「squeezing」。
- 关键 nuance：若只吃通用微处理器的自然 scaling、不动软件，理论上限 100×，但**因为 Dennard 已死，实际大概只有 ~10×/10 年**。
- 而 NVIDIA 靠 codesign 拿到 **1,000,000×/10 年**——「somewhere between 100,000x and 1 million x，数字大到已经无所谓。」（相对 Moore 的 ~10,000× 额外杠杆、以及它如何压低 token 成本，见 [[extreme-co-design]] 与 [[token-economics]]。）
- 为什么这如此重要，用类比说：能以光速旅行则「住哪都无所谓」；NY→CA 十分钟则「社会一切都变」；**compute 快一百万倍，「everything about computing changed」**——于是 AI 研究者才敢说「why don't we just take all of the internet」，不再纠结 curate 什么数据。

## 该加速哪些问题（specialized 机制、general-purpose 触达）

- 通用机器不该去解一切**极端计算密集**问题：computer graphics、molecular dynamics、quantum chemistry、fluid dynamics、mesoscale/multiscale multiphysics、deep learning。对这些，就该**同时**优化算法 + 系统 + 编译器 + 框架 + 芯片架构。
- 但加速计算在**触达面上仍是通用的**：Jensen 反复强调「**NVIDIA is a general purpose computing company**」——GPU 用于 video games、送酱油、medical imaging（「every single medical imaging system in the world」）。机制上专用、触达上通用，这正是 [[cuda|CUDA]] 刻意维持的 **specialization ⇄ generalization** 张力（专用到能真正加速、又通用到能随每 6 个月一变的算法演进）。

## 硬件随 workload 共同演化（四代 roadmap）

加速计算不是一颗更快的芯片，而是**硬件形态随计算 pattern 逐代重塑**。方法论：「你要先对 computing pattern 有 mental model，再造能跑它的系统。」

| 代际 | 目标 workload | 关键设计决定 |
|---|---|---|
| **Hopper** | pre-training | 当年最贵超算 $350M，NVIDIA 押注 multibillion-$ 系统——为一个「precisely zero」的市场造，纯 first-principles |
| **Grace Blackwell / NVLink-72** | inference（decode） | decode 需要的 memory bandwidth 远超单芯片 → 「gang up 72」→ **世界第一台 rack-scale computer**；两年 **50×**（Moore 同期 2×） |
| **Vera Rubin** | agents | long-term memory 进 storage、storage 直连 fabric/GPU（不走网络拷贝）；tool 跑 CPU 且整台 GPU 超算在等它 → **Vera** CPU 主打极低延迟、single-threaded 性能 |
| **Feynman** | swarms of agents | agents → subagents → subagents 的 swarm，「what kind of computer does that manifest」 |

（Vera Rubin **pod** 的具体规模——7 种芯片 / 5 种机架 / 40 机架 / 1.2 quadrillion 晶体管 / 60 exaflops 等——见 [[extreme-co-design]]。）

## 与 [[extreme-co-design]] 的分工

| | accelerated computing（本页） | [[extreme-co-design]] |
|---|---|---|
| 回答 | **为什么** / premise | **怎么** / 方法 |
| 内容 | 通用计算终结（Moore/Dennard）、RISC 血统、该加速哪些问题、硬件随 workload 共演化 | 跨整条 stack + 超越 CPU/GPU（含 power/cooling/rack/pod）、anticipate hardware、pod-scale 数字 |

两页互为上下游：先有「通用已死、必须加速」的前提，才谈得上「如何极致协同设计」。

## CS153 补充：Google 的专用化理由（Amin Vahdat）

[[amin-vahdat]]（[[value-per-gigawatt]]）从**需求侧**给出与本页一致的专用化理由：通用 CPU 的性能/能效增长已停滞了**十余年**，所以必须挑那些体量足够大的 workload（inference / training）去做专用硅——一颗 TPU 在这些任务上可比 CPU **高约 100×** 的效率，代价是它「can't do anything（else）」。这条来自 Google 自研 silicon 的路径，为本页「通用计算走到尽头、机制上专用」的后通用计算命题再添一个独立佐证。

## 相关页面

- [[extreme-co-design]]
- [[nvidia]]
- [[cuda]]
- [[scaling-laws]]
- [[compute-infrastructure]]
- [[token-economics]]
- [[jensen-huang]]

## References

- [[cs153-jensen-huang-compute]] — Stanford CS153（讲者 Jensen Huang / NVIDIA），2026
