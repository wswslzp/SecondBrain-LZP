---
title: "Sovereign AI"
tags: [ai, geopolitics, cloud, infrastructure]
date_created: 2026-04-18
date_modified: 2026-07-21
related: ["[[context-feedback-loops]]", "[[frontier-systems]]", "[[nvidia]]", "[[jensen-huang]]", "[[ai-energy-bottleneck]]", "[[frontier-ecosystem]]", "[[satya-nadella]]", "[[microsoft]]", "[[ai-capex-beneficiaries]]", "[[project-glasswing]]", "[[deepseek]]", "[[china-us-compute-gap]]"]
---

# Sovereign AI

主权 AI：国家/政府/机构需要本地控制的 AI 基础设施，不依赖海外云。

## 起源

[[anjney-midha]] 在 CS 153 中讨论的 Mistral 案例：
- Arthur Mensch（Chinchilla 论文作者）+ Guillaume Lamp（llama 共同创建者）在欧洲创立 Mistral
- 核心论点：关键敏感 context 不能送到海外云

## 驱动因素：Cloud Act

美国政策规定：**如果 workload 运行在美国公司的服务器上（无论地理位置），美国政府可以访问数据**。

这对以下工作负载不可接受：
- 国家记录
- 国防
- 主权数据
- 关键基础设施

## 打破 15 年的云集中

过去：
- Amazon/Google 因消费者业务产生巨量服务器需求 → 转售 AWS/GCP
- 规模经济 + 边际成本递减 → 寡头垄断持续 15 年

现在：**AI workload 从"聊天"升级为关键基础设施**（因为 RL 达到生产精度），引发全球重新洗牌。

## 标志事件

Macron + Jensen Huang + 一位 33 岁从未运营过企业的科学家（Mensch）在巴黎宣布 Mistral 是"欧洲未来"。

> "It's because of context. There are governments and mission-critical workloads that are just too sensitive to be run on cloud infrastructure overseas."

## 机会

对学生/创业者而言：
> "One clue about where to spend your time is where there's a unique context that hasn't been available to you because you're not at scale, but that you can do something unique and get ahead of."

## Jensen Huang 的国家视角

[[jensen-huang|Jensen]]（[[nvidia]]）本人正是巴黎 Mistral 发布的站台者之一。在 Lex Fridman 访谈里，他把 NVIDIA 的成功直接系于**美国国家利益**：巨额税收、技术领导力=国家安全（"all aspects"）、以及 AI factory 带来的**再工业化**与就业回流。同时他盛赞中国是「fastest-innovating country / builder nation」（50% 的 AI 研究者是华人；省市竞争 + open source 文化），其领导层多为工程师而非律师。主权 AI 的博弈因此不只是「数据放哪」，也是美 / 中两个 builder 体系在人才、开源与再工业化上的竞争。

## 企业级第二义：repatriation 与 on-prem（Citrini）

[[citrini-research|Citrini]] 在《[[citrini-all-along-the-ai-watchtower|All Along the AI Watchtower]]》里给「sovereign」加了**第二种解读**——不只是国家主权，也是**企业**为保住竞争优势（"business alpha"，Palantir 语）而**拥有自己整条 AI 栈**：从算力（on-prem/私有云/托管机房）、到数据、到持续定制更新的模型本身。

- **[[satya-nadella|Nadella]] 的「付两次费」**：「你为智能付两次——一次是钱，另一次是让智能有用所必须透露的专有知识。」结合 Microsoft **因成本停用内部 [[claude-code|Claude Code]]** 的背景，隐忧不在表面 token 账，而在把大量软件开发路由进竞争对手「套数据饥渴」的系统。
- **Palantir（PLTR）× [[nvidia|Nvidia]]「The Future of AI is on-prem」**（2026-06-29）：联合发布 **Sovereign AI OS Reference Architecture**，整合 Nvidia 开源 Nemotron 模型 + GPU + Dell PowerEdge R670 + Palantir 软件栈，造一个自给自足、数据不出门的 AI 平台。实施成本 $5-6M（最小 32 GPU）到 $50-70M（最大），另加软件许可/硬件刷新/电力托管。
- **工作负载回流本地**是并行的市场动态：Dropbox「魔法口袋」（2018，90% 用户数据迁出 AWS，毛利大增）、GEICO、37signals（转 OpenStack，砍 $3M AWS 账单）；Barclays 调查 **88% 企业 CIO 计划把至少部分公有云负载迁回私有/本地**。
- **硬件受益链**：Dell（DELL）、HPE、联想（992 HK）、富士通（6702 JP）、存储 NetApp（NTAP）/Everpure（P）、应用交付与安全 F5（FFIV）、平滑迁移的 Nutanix（NTNX）；主权买家还含欧盟 €2000 亿 InvestAI、沙特 Humain、阿联酋 Stargate、日本 METI 补贴算力。详见 [[ai-capex-beneficiaries]] 主题 3。

## 中国视角：国产替代 = 主权算力（[[liang-wenfeng|梁文锋]]）

[[liang-wenfeng|梁文锋]]/[[deepseek|DeepSeek]]（[[liang-wenfeng-investor-meeting]]）给主权 AI 加了**供给侧的算力自主**一层——不是「数据放哪」，而是「**卡从哪来、生态谁建**」：

- **被迫即机遇**：买不到英伟达卡 → 所有人被迫做国产 → 国产卡适配「没有任何障碍」，一年内可扭转「国产生态不好」的认知，剩下只是产能。华为 950 超节点可**平替** GB200/GB300（代价 4 张顶 1 张 + 落后 2 年）。详见 [[china-us-compute-gap]]。
- **中国是「三体之一」**：常理上中国**产能最大、电力最多**，AI 最终大概率扮演**产量最大 / 最便宜**的角色；「中国产的 AI 会系统性地更便宜，就跟其他行业一样」——与 [[restraint-as-strategy|克制定价]] 互为因果。
- 这为本页 [[jensen-huang|Jensen]]「中国是 builder nation」的判断补上了**中方自己的战略叙事**：不追求在最大模型上与美国正面竞争，而在「能训得起、用得起」的规模上先赢**成本与时间**。

## 企业级映射：Nadella 的 frontier-ecosystem

[[satya-nadella|Satya Nadella]]/[[microsoft]]（[[cs153-satya-nadella-frontier-ecosystem]]）的 [[frontier-ecosystem]] 与主权 AI 是同一命题的两个尺度：都关乎**不把敏感 context / IP 泄漏**给外部——主权 AI 在**国家层面**（数据不出境、不落海外云），frontier-ecosystem 在**企业层面**（拥有自己的「token capital」、在私有 RLE 上 hill-climb，而非把语料喂给基础模型的所有者）。

## 来源
- [[cs153-frontier-systems]]
