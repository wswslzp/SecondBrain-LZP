---
title: "Extreme Co-Design（极致协同设计）"
tags: [nvidia, engineering, systems, compute, extreme-co-design, concept]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[nvidia]]", "[[compute-infrastructure]]", "[[optical-interconnect-roadmap]]", "[[scaling-laws]]"]
---

# Extreme Co-Design（极致协同设计）

[[nvidia|NVIDIA]] 的招牌工程范式，也是 [[jensen-huang|Jensen Huang]] 眼中「the miracle of this company」。它有两个维度的「跨越」：

1. **跨整条软件/硬件 stack** 联合优化：架构 → 芯片 → 系统 → 系统软件 → 算法 → 应用。
2. **超越 CPU/GPU/网络芯片/scale-up switch/scale-out switch**，把 **power、cooling、rack、pod、data center** 一并纳入协同优化。

> "We're optimizing across the entire stack of software from architectures to chips, to systems, to system software, to the algorithms, to the applications... and it goes beyond CPUs and GPUs and networking chips."

## 为什么必要（why）

> "The reason why extreme co-design is necessary is because the problem no longer fits inside one computer to be accelerated by one GPU."

- 当今问题已装不进一台电脑。你想让 10,000 台电脑跑出「a million times faster」，就必须拆算法、shard pipeline / data / model，把问题**分布**出去。
- 一旦分布，**Amdahl's Law** 就成主宰：若计算只占总负载 50%，哪怕把计算加速一百万倍，整体也只快 2×。于是 CPU、GPU、网络、交换、负载分配**样样都成瓶颈**——「everything gets in the way」。
- 而 **Moore's Law 已放缓**（因 Dennard scaling 放缓）。若不做 extreme co-design，就只能线性 scale 或吃 Moore 的残羹。

### 量级证据

> "In the last 10 years, Moore's Law would have progressed computing about 100 times. We progressed and scaled up computing by a million times in the last 10 years."

即 extreme co-design 相对 Moore's Law 带来了约 **10,000× 的额外杠杆**（1,000,000× vs 100×）；直接体现为 **tokens/sec/watt 每年提升一个数量级**，进而压低 token 成本（见 [[token-economics]]）。

## Speed of light 思维

extreme co-design 的方法论内核是 Jensen 的 **speed of light**——一切对照物理极限衡量，而非搞 continuous improvement。系统设计准则：

> "As complex as necessary, but as simple as possible."

先质疑「所有这些复杂性是否都必要」，必要之上的复杂都是 gratuitous。（speed of light 的完整展开见 [[jensen-huang]]。）

## Anticipate hardware（提前 2–3 年押注）

这是 extreme co-design 最难、最「scary」的部分：硬件**无法在一周内 pivot**，必须预判 AI 的走向。

> "AI model architectures are being invented about once every six months. And system architectures and hardware architectures kind of every three years. So you need to anticipate what likely is going to happen two, three years from now."

预判的三条来源：**内部基础/应用研究**（自己造模型 → 第一手经验）；**倾听全行业**（NVIDIA 是唯一与几乎每一家 AI 公司合作的 AI 公司，能听到「the whispers across the industry」）；**保持架构弹性**（CUDA 兼具 specialization 与 generalization，能随算法演进——见 [[cuda]]）。

### 实例

- **MoE / sparsity**：正因预判到 mixture-of-experts，才上 **NVLink-72 而非 NVLink-8**——把整个 4T~10T 参数模型放进「一个 computing domain，as if running on one GPU」。
- **Grace Blackwell → Vera Rubin + Rock**：Grace Blackwell rack 专为跑 MoE LLM inference 设计；仅一年后的 **Vera Rubin** rack 完全不同——新增 storage accelerators、新 CPU「Vera」、以及额外的 **Rock** rack，从「跑 LLM」转向「跑 **agents**（agents bang on tools）」。这套系统的设计**早于** Claude Code / Codex / OpenClaw 问世——纯靠 first-principles 推理（「a digital worker 必须 access ground truth = file system、do research、use my tools」）预判出来。

## Vera Rubin pod 的规模（一个具体锚点）

一个 Vera Rubin **pod**：

| 维度 | 数值 |
|---|---|
| 芯片类型 | 7 种 |
| 专用机架类型 | 5 种 |
| 机架数 | 40 |
| 晶体管 | ~1.2 quadrillion（1.2×10¹⁵） |
| NVIDIA dies | 近 20,000 |
| Rubin GPU | 超过 1,100 |
| 算力 | 60 exaflops |
| scale 带宽 | 10 PB/s |

而单个 **NVL72 rack** 就有 130 万个组件、1300 颗芯片。Jensen 说「we're probably gonna have to crank out about **200 of these pods a week**」——「the most complex computer the world has ever made」。

## 与 Elon 的对照

Jensen 认为 co-design 是「the ultimate systems engineering problem」，与 Elon 在 Colossus 上的方法论同源：凡事三问——**是否必要 / 是否必须这样做 / 是否必须这么久**，把一切削到「不能再删、但必要能力仍在」的最小集，且亲临 point of action。

## 相关页面

- [[nvidia]]
- [[compute-infrastructure]]
- [[optical-interconnect-roadmap]]
- [[scaling-laws]]
- [[token-economics]]
- [[jensen-huang]]

## References

- [[jensen-huang-lex-fridman]] — Lex Fridman Podcast #494（2026-03-24）
