---
title: "Usage-Based Pricing（席位→用量/结果的定价转变）"
tags: [business-model, saas, pricing, agentic, enterprise-software]
date_created: 2026-07-21
date_modified: 2026-07-21
related: ["[[token-economics]]", "[[ai-capex-beneficiaries]]", "[[intelligence-as-utility]]", "[[tasks-vs-jobs]]"]
---

# Usage-Based Pricing

智能体时代逼出的**定价范式转变**:企业软件从「按席位/按月订阅」转向**按用量 / 按 token / 按结果**计费。因为**驱动工作量的不再是「人（席位）」而是「智能体」**,座位数与价值创造脱钩。

> "This reality demands a new model: usage-based pricing for everything […] The natural unit of payment for software is the request, the token, or the outcome, not the seat or the month."

## 为什么发生
- 单个智能体任务会跨会话状态/应用数据/工具结果/权限/事件产生**大量重复读写**,工作集持续变化,检索成为执行循环本身的一部分——按席位收费无法捕获这种「持续消耗」。
- 与 [[intelligence-as-utility]]（智能作为公用事业,按用量计价）、[[token-economics]]（token 工厂经济学:retrieval→generative)同源;是 [[tasks-vs-jobs]] 在**商业模式层**的映射。

## 案例（均来自 [[ai-capex-beneficiaries]] 主题 2）
- **GitLab（GTLB）**——**GitLab Flex** 作为商业桥梁:付费客户单次年度承诺,可在席位与积分功能间月度灵活调配,无需新合同。**Orbit** 平台的外部智能体通过 MCP/REST 查询会消耗 **GitLab Credits**,让 Claude Code/Codex/Cursor 等对 GitLab 图谱的调用可计量(自有 Duo Agent 查询目前零费率)。
- **MongoDB（MDB）**——**Atlas 消费级定价**:list price 自 2020 未变,却把「新增热容量计量器」(专用搜索节点、向量搜索、流处理)接到同一基准曲线上,workload→revenue 的传导**自动**发生(无重新谈判、无打包决策、无销售周期)。
- **Elastic（ESTC）**——大客户在消费前就**标准化采用搜索平台**,合约延展是「表面现象」;定价为 ex-growth,搜索平面被包装成廉价可选权。
- 三者是同一转变的三种传导方式:GitLab 把席位转成计量器(定价转型进行中)、MongoDB 已计量工作集(今天就有效)、Elastic 售卖「一切内容的可查询副本」(企业标准化选项)。

## References
- [[citrini-all-along-the-ai-watchtower]]
