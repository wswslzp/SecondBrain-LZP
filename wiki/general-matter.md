---
title: "General Matter"
tags: [company, energy, nuclear, uranium-enrichment, haleu, leu, supply-chain, cs153]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[scott-nolan]]", "[[ai-energy-bottleneck]]", "[[nvidia]]", "[[sovereign-ai]]", "[[frontier-systems]]"]
---

# General Matter

美国的**铀浓缩（uranium enrichment）公司**，由 [[scott-nolan]] 于 **2024 年 1 月**创办并任 CEO。使命是把美国几乎已消失的 enrichment 能力**带回本土、规模化，并在成本上完胜**——因为在 [[ai-energy-bottleneck|AI 能源瓶颈]] 的「five whys」推演里，enrichment 是「五年尺度上一路通到 AI 的瓶颈」。内容以 [[cs153-frontier-systems|CS 153]] 讲座为准。

## 在做什么

- **只做浓缩这一步（separation / refining）**：把 **UF6** 气体按同位素分离，提高裂变同位素 **U-235** 的浓度到反应堆可用水平。
- **厂内既无核反应也无化学反应**：靠把材料铺开、避免形成 **critical mass** 来确保不发生核反应；本质是纯物理 **separation process**。所以 General Matter 不是反应堆、也不是化工厂。
- **产品覆盖多种等级**：能做 5% 的 **LEU**（供占美国电网约 **20%**、零碳排的现有反应堆）和 **HALEU**（先进反应堆 / SMR / microreactor 需要的更高浓度燃料）。「if you can enrich, you can make fuel.」

## 为什么是这一步：美国缺失的中间环节

核燃料走**五步供应链**（详见 [[ai-energy-bottleneck]]）：mining → conversion（U3O8→UF6）→ **enrichment** → reconversion（回固体）→ fabrication（制芯/制棒）。其余四步美国都有选项，唯独中间的 enrichment：

- 美国今天全球市占 **<0.1%**——「unable to produce its own nuclear fuel at any scale whatsoever」，完全依赖欧洲厂商，甚至至今仍从**俄罗斯**进口（有制裁仍进口，因为确实需要）。
- 历史上却曾是霸主：1980s 占全球约 **86%**（DOE 站点、政府运营、前 Manhattan Project / 冷战设施）。柏林墙倒后走自由贸易 + **Megatons to Megawatts**（俄核弹头 down-blend），本土 enrichment 因不经济而关停，**最后一座 2013 年**在 Paducah。
- enrichment 还常是先进核燃料里**最大的成本项**——所以既是 scaling 瓶颈也是 cost 瓶颈。

## 执行与里程碑

- **DOE $900M 合同**（2026 年 1 月，公司成立满 24 个月时拿下）。原合同期到 **2034**，但公司目标是**十年内先上线**、随后快速扩产，以赶上 SMR 的部署节奏（demos 明年、真正 scaling '28–'29、hockey stick 在 2030s 初到 2035）。
- **跨政府一致支持**：始于 Biden 政府（先推 HALEU / 先进堆燃料），延续到现政府（转向 LEU / 电网燃料）；国会两党支持，DOGE 成员帮助推进。DOE 内部是「一群把整个职业生涯押在核能上」的人。
- **团队**：近 **100 人**，抽调自 national labs、其他核能公司、以及 **Tesla / SpaceX**——刻意复用「打入资本密集、被在位者主导、停滞行业」的 SpaceX/Tesla playbook。头几个月 100-hour weeks。
- **选址 Paducah, Kentucky**：上一座美国商业 enrichment 所在城市；DOE 站点南端一块从未开发的 **100 英亩**，8 月奠基。HQ 在 LA。
- **就业**：LA 未来几年约 500，Kentucky 相当或更多，合计约 **1000** 个新岗位；到处招不满，「we can't find enough good people」。

## 长期使命：成本 + 防扩散

长期目标类比 SpaceX：把这项技术带回美国、用极低成本扩大整个行业。除了先解决美国自身，还想为**不做 enrichment 的盟国**低成本供货——用低到「让别人懒得自己搞」的成本，带来 **nonproliferation（核不扩散）** 的下游收益（越少国家需要自建 enrichment，地缘政治风险越低）。这与 [[sovereign-ai]] 里的能源/供应链主权、国家安全同频。

## 与 AI 的联动

General Matter 本质是在解 [[ai-energy-bottleneck|AI 的能源瓶颈]] 的最上游：AI 需要 compute（见 [[compute-infrastructure]]）→ compute 需要 power → power 的 baseload 长期靠 nuclear → nuclear 需要 fuel → fuel 卡在 enrichment。[[nvidia]] 的 [[jensen-huang|Jensen]] 也在 Joe Rogan 上承认 energy 才是 blocker——两边从需求侧与供给侧指向同一约束。

## 相关页面
- [[scott-nolan]]
- [[ai-energy-bottleneck]]
- [[nvidia]]
- [[jensen-huang]]
- [[sovereign-ai]]
- [[frontier-systems]]
- [[cs153-frontier-systems]]

## References
- [[cs153-scott-nolan-energy]] — Stanford CS153（讲者 Scott Nolan / General Matter），Energy Bottlenecks
