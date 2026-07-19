---
title: "Google"
tags: [google, tpu, gemini, deepmind, ai-infrastructure, datacenter, company]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[amin-vahdat]]", "[[value-per-gigawatt]]", "[[nvidia]]", "[[compute-infrastructure]]", "[[frontier-systems]]"]
---

# Google

从 [[cs153-amin-vahdat-gigawatt|Amin Vahdat 的 CS153 讲座]]看到的 Google，是一家**把自研 silicon、data-center networking、能源与规划垂直整合**、以支撑 [[value-per-gigawatt|Gemini]] 等前沿 AI 的公司。本页聚焦其 infra / TPU / Gemini / DeepMind 一面。掌管内部 ML/systems 基础设施的是 [[amin-vahdat]]。

## Compute 规模

- 自称拥有「**among the largest computing infrastructures on the whole planet**」，未来四年**瞄向 tens of gigawatts** 且会「well north of」。
- **1 GW ≈ $40–50B** 基础设施——所以 Google 的 infra org 被主持人称为「literally one of the most efficient on the planet」。
- **利用率纪律极高**：**node allocation < 96% 就算 major outage**；对照传闻中 Colossus 的 **~11% MFU**。核心不是「有几个 GW」，而是**每美元交付多少价值**（完整框架见 [[value-per-gigawatt]]）。
- **depreciation 6 年**；老芯片（含 GPU）不会 obsolete，需求持续。

## TPU

- Google 自研的 AI 加速器，是 Gemini 得以 scale 的地基。**rack 内 64 颗 TPU 用 copper point-to-point 直连**，**rack 之间用 [[value-per-gigawatt#光路交换与 torus|Optical Circuit Switch (OCS)]] 组成 3D torus**——torus 是 **all-reduce**（ML 头号 collective）的最优 topology，OCS 则能秒级虚拟换掉坏 rack，实现 **instantaneous failure recovery**。
- **TPU v2（2015）**：初代 256 node，如今单个 pod 超 **9,000 node**。当年网络之争由 **Norm Jouppi** 一派的 distributed-shared-memory / point-to-point 胜出（[[amin-vahdat]] 曾押错 Ethernet）。
- **第八代首次拆线：8i（inference）/ 8t（training）**——一年发两颗、首次专用化。以前一颗 fungible chip 是对的（各只好 ~5%）；如今需求发散到专用化带来 **major uplift**，差异在 **memory : compute : networking 比例**。TPU 对其领域比 CPU **~100x 更高效**，但「can't do anything」。
- **与 [[nvidia|NVIDIA]] 非零和**：Google **大量买、卖、用 GPU**；「TPU 打败 GPU」不是目标（「not even a goal」），市场在膨胀、no winning and losing，只是打不同 domain / 客户。

## DeepMind 与 Gemini

- **ChatGPT code red（2022 年 11 月）** 后 Sundar 的大 reorg：**Brain + DeepMind 合并**（Amin 称「fantastic move」），同时把多支 infra 团队合到 [[amin-vahdat]] 麾下，以「more speed and unification」推进。Demis Hassabis、Jeff Dean、Sundar Pichai 记大功。
- Amin 称公司文化经历了一次「reinvention」，如今已「through it」。**Gemini app 的成功度量 = happy daily active users**，不是「背后有几个 GW」。

## 供应链与能源

- **team 常驻 Taiwan / South Korea / Thailand** 深度参与供应链（TSMC 等）；Amin「not worried」能拿到 fair share，关键仍是**高效使用**。
- **memory 是全球性短缺**；net-new GW 的 lead time 是 **2–3 年**；utility 现在要 **20 年 take-or-pay** 合同（电网无 slack）。详见 [[value-per-gigawatt#供应链与规划|供应链与规划]] 与 [[ai-energy-bottleneck]]。
- **社区/电网 asset**：缺水社区选「不耗水但低 10% 能效」的 DC 设计；已开发 **gigawatt 级 demand response**（电网最紧张那一两天还回 100 MW）。目标是 **optimal scaling**，而非 capacity at any cost。
- **Colossus 富余算力**（SpaceX/xAI）被租给 [[anthropic|Anthropic]] 与 Cursor，反映 inference 需求爆炸——虽非 Google 自有，但被 Amin 用作「serving 需求超过 training」的例证。

## 相关页面

- [[amin-vahdat]]
- [[value-per-gigawatt]]
- [[nvidia]]
- [[jensen-huang]]
- [[compute-infrastructure]]
- [[ai-energy-bottleneck]]
- [[anthropic]]
- [[frontier-systems]]

## References

- [[cs153-amin-vahdat-gigawatt]] — Stanford CS153 Frontier Systems（讲者 Amin Vahdat / Google）
</content>
