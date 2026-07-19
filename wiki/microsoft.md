---
title: "Microsoft"
tags: [microsoft, ai, company, silicon, quantum, agents]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[satya-nadella]]", "[[frontier-ecosystem]]", "[[openai]]", "[[extreme-co-design]]", "[[open-weights-strategy]]", "[[compute-infrastructure]]"]
---

# Microsoft

50 年老公司，[[satya-nadella|Satya Nadella]] 治下的核心 DNA 始终是「**developer tools platform + knowledge worker tools company**」，但每逢新平台就把这一使命**重新诠释**一次。本页汇总其在 [[frontier-systems|Stanford CS153]] / **Build** 大会一线披露的 AI 战略与硬件/量子布局。

## 与 OpenAI 的关系

- 2019 年 **$1B 下注 [[openai|OpenAI]]** 的来处见 [[satya-nadella]]（prepared mind + Gates-Grove DNA）；真正的大决定是 **compute concentration** 而非资本。
- 当年「we were one happy family」，[[sam-altman|Sam]] 的 scaling-laws 野心正合 Microsoft 对 natural language 的长期执念。Maia 200 如今与 **OpenAI 的模型 codesign**（「we have that IP」）。

## Frontier Intelligence Ecosystem（Build 发布主线）

- **七个 MAI 模型**：以「thinking」与「coding」为主，数据 lineage 极干净（Mustafa 强调不掺 synth data、不碰版权），使 reasoning 能真实 emerge；配一份被 Satya 盛赞「近期同规模模型里最透明」的 technical report。
- **licensed weights，非 fully open**：weights **licensed** 而非完全开源，可在 Base10 / Fireworks / Together 上取用并 fine-tune；理由是 inspection / safety + 一个真实的 economic model。另发布两个 open-weight 本地模型 **Ion Instruct / Ion Plan**（Phi Silica 血统，跑在 Windows 上做 local agent loop）。详见 [[open-weights-strategy]]。
- **hill-climbing machine**（生态核心）：把 MAI 当「easy button」交出，任何公司搭 **RLE（gym）**、带 private evals、请任意模型进来 hill-climb、**retain IP**。**M365 可 bootstrap RLE**——把 multi-tenant SaaS 变成 multi-tenant hill-climbing service，甚至从观察到的工作流（HR onboarding）自动生成 evals。完整论证见 [[frontier-ecosystem]]。

## Copilot 三形态 + agent containment

- **chat →（delegate 任务的）Cowork → Scout = autopilot**。Scout 是 long-running agent：持续运行、monitoring、有 **heartbeat**、会「dreaming」（对标 Claw）。用 **Entra ID** 作 delegated identity = 用户的 **digital twin**；可 mint 更多 autopilot，各带自己的 identity 与 sandbox。可视作「enterprise OpenClaw + 融入 Copilot 的 UI」。
- **containment**：与 OpenClaw Foundation 合作，在 Windows 上 out-of-the-box 把 OpenClaw 装进新容器 **MXC**（sandbox）。可设 process / session / VM 隔离边界（甚至整个 Windows 365 云实例）。名句：「we're going to learn to isolate the environments for these agents, just like how back in the day we thought about **processes**.」见 [[multi-agent-patterns]]。

## Unmetered intelligence + edge silicon

- **动机**：token 短缺时，把负载卸到庞大的 **dGPU install base**（边缘算力），让 Scout / Claw 在本地 **24×7 运行且不被计费**（unmetered）。见 [[value-per-gigawatt]]、[[token-economics]]。
- **硬件**：与 [[nvidia|NVIDIA]] 合作的 **RTX SoC**（Surface Laptop 秋季出货，OEM 跟进）；一台 **dev box**——1 petaflop AI 算力、20 CPU cores、**128GB unified memory**，本地跑 **trillion-parameter 模型**；以及让 Windows 跑在 **GB300** 上的 **DGX workstation**，Satya 称之为「**data center desktop**」。

## Project Solara：agent 时代的新 form factor

- 两个 reference design：一个 **badge**（含 fingerprint reader + camera + **MediaTek** 处理器，能唤醒 Copilot、口述编码任务→云端执行→回推通知），一个 **desk companion**。定位是 long-running agent 的**端点**（wake / notify），指向「ambient intelligence + ubiquitous computing」（如护士 station-to-station badge in 数据）。
- **新平台规则**：延续 Windows「唯一 open platform」的 ethos——「you can install anything on Windows」，不把上一代 App Store 规则 carry over 到 agent 平台。

## Custom silicon（三大新负载：training / inference / long-running agent）

- **Maia 200**：与 Microsoft + OpenAI 自家模型 **codesign**，已在多个数据中心跑 **GPT-5.5** 为 Copilot 供能，拿到 **TCO 优势**。
- **Cobalt**（ARM CPU）：用 **GitHub Copilot traces** 调优，专攻 agent loop 所需的强 single-thread core。
- **heterogeneous fleet + smart workload placement**：仍大量用通用 GPU；连**旧 GPU** 都拿去加速 **Fabric** 数据仓库（**7x+** 性能）。设计点远不止 AI accelerator——还有 CPU、network accelerator、storage accelerator、AI WAN（multi-data-center hops）。
- Satya：「**a great time to be in computer architecture**」——像当年 Patterson 书出、RISC vs CISC 之争，如今可从数据中心 physical design 一路重想到「把 electron 高效送到 CPU」以让 token 更省。方法论见 [[extreme-co-design]]、[[compute-infrastructure]]。

## Quantum

- 干了 20 多年（Satya 是第三任接力的 CEO）。**Majorana 1**（一年前首个 QPU，验证 topological qubit 物理突破）→ **Majorana 2**（industrial scale），并已 perfect 了 digital control。
- **quantum = the new accelerator**：不替代 classical（不擅存储/内存），擅 computation，须与 classical 联姻。近期路线：用 ion-trap / photonics / natural-atom 机器（含丹麦 QuNorth × Atom Computing 合作，一年内上线）生成高保真 **traces** 训练 **material-science / chemistry** 模型；「100 logical qubits + good error correction」即可产 synth data。目标：**by the end of the decade** 解真实问题。

## 相关页面

- [[satya-nadella]] — CEO 与其世界观
- [[frontier-ecosystem]] — 公司当前战略的核心论点
- [[openai]] / [[sam-altman]] — 深度合作方
- [[nvidia]] / [[jensen-huang]] — RTX SoC / DGX workstation / unmetered intelligence
- [[extreme-co-design]] / [[compute-infrastructure]] / [[token-economics]] — silicon 与经济
- [[open-weights-strategy]] — MAI = licensed 的取舍

## References

- [[cs153-satya-nadella-frontier-ecosystem]] — Stanford CS153 源摘要
