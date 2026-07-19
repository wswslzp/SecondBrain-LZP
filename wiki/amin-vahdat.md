---
title: "Amin Vahdat"
tags: [amin-vahdat, google, tpu, systems, networking, infrastructure, person]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[google]]", "[[value-per-gigawatt]]", "[[jensen-huang]]", "[[compute-infrastructure]]", "[[frontier-systems]]"]
---

# Amin Vahdat

[[google|Google]] VP / GM，掌管公司**内部 ML 与 systems 基础设施**——[[value-per-gigawatt|TPU]]、data-center networking、data center、能效与规划。主持人 [[anjney-midha]] 在 [[cs153-amin-vahdat-gigawatt|CS153]] 上说：**「让 Gemini 成为可能的那些 TPU，若没有 Amin，绝不会做到今天的 scale。」** 从业近 **30 年**。

## 定位：the opposite of Jensen

主持人把他框成 [[jensen-huang|Jensen Huang]] 的对位面——Jensen 是「rapid-fire, high-throughput LLM」式的 showman，Amin 则是「被训练在 30 年 infrastructure discipline 上的三个 frontier model 的蒸馏」，每个 token 都压得极实。他代表的是 [[frontier-systems]] 光谱里**最严谨的系统工程一端**：不谈需求侧宏大叙事，只谈**如何把每一瓦、每一个 node 榨出价值**（见 [[value-per-gigawatt]]）。但两人共享「compute/energy 是瓶颈」的底层判断，且 Amin 强调二者**非零和**——「all the respect in the world for Jensen」，会打电话向他请教。

## 他反复强调的几件事

- **value per dollar > gigawatts**：正确度量不是「有几个 GW」，而是**每一美元交付多少价值**，最终 roll up 到 happy DAU / paying customers / developers。「If capacity sits idle, that's a bug.」
- **system balance（Amdahl's Law）**：scaling FLOPs 容易，建一台跨 10k–100k TPU、比例正确（FLOPs : HBM BW : network BW : SRAM）的 balanced supercomputer 才难。
- **reliability & goodput**：同步 data-parallel training 里一个 node down = 全盘 down；five nines 要 2N 冗余供电（半数容量闲置）。他观察到 frontier labs 正**用 reliability 换 access**。
- **OCS + 3D torus**：用 optical circuit switch 做可编程 topology，秒级虚拟换掉坏 rack、保持 torus 完整——TPU 的真正差异化就是这种 availability。
- **anti-zero-sum**：「There's no such thing as winners and losers — just people who get shit done and who don't.」Google 参与生态是**抬升整个行业和所有用户**。

## 履历

- **6 岁在伊朗**看到杂志封面上的一台电脑，就决定要当 computer programmer（当时没碰过电脑）——自称 defining characteristic 是「very stubborn, I never change my mind」。全家在他 6 岁移居美国。
- 出于对 material 的纯粹热爱读了 PhD，**做了 12–13 年教授（Duke）**；对「去工业界」曾极其 haughty。
- **2010 年加入 Google**（本是一年 sabbatical）——当时他与 CEO **Eric Schmidt** 之间只有 7 个人，且 **7 人全有 CS PhD**，「organ rejection」没有发生，从此留下。
- 研究老本行是 **networking**。**TPU v2（2015）** 网络之争中他坚信该用 Ethernet（凭 45 年 Ethernet 传统），结果 **Norm Jouppi**（Stanford PhD）一派主张的 **distributed-shared-memory / read-write / point-to-point / not switched** 赢了，并「stood the test of time for a decade」。他把这当作最爱的 Google 故事：「**The best thing about Google is how often I get to learn I'm wrong.**」
- **ChatGPT code red / 2022 年 11 月**：Sundar 的大 reorg 把 **Brain + DeepMind** 合并（[[google#DeepMind 与 Gemini|见 Google 页]]），并把多支 infra 团队合到 **Amin 麾下**；他 now reports to Sundar，常「fondly」提起那个月。给 Demis Hassabis、Jeff Dean 记功。

## 相关页面

- [[google]]
- [[value-per-gigawatt]]
- [[jensen-huang]]
- [[nvidia]]
- [[compute-infrastructure]]
- [[ai-energy-bottleneck]]
- [[frontier-systems]]
- [[anjney-midha]]

## References

- [[cs153-amin-vahdat-gigawatt]] — Stanford CS153 Frontier Systems（讲者 Amin Vahdat / Google）
</content>
