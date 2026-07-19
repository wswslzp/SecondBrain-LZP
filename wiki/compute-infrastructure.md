---
title: "AI Compute 基础设施经济"
tags: [ai, compute, infrastructure, gpu, markets]
date_created: 2026-04-18
date_modified: 2026-07-19
related: ["[[frontier-systems]]", "[[anjney-midha]]", "[[context-feedback-loops]]", "[[nvidia]]", "[[token-economics]]", "[[jensen-huang]]", "[[amin-vahdat]]", "[[value-per-gigawatt]]", "[[sam-altman]]", "[[satya-nadella]]"]
---

# Compute 基础设施

[[anjney-midha]] 在 CS 153 中的核心论点：**Compute 今天不是大宗商品**。与普遍观点相反。

## 资本支出规模

Big Tech 过去 3 年：
- 2024 年：~$300B CapEx
- 2025 年：~$600B
- 2026 年：**$1.2T（已宣布）**

> "Over the last 3 years, the five largest tech companies have decided to spend more on infrastructure than they have in the preceding 30 years combined."

## 价格反直觉

H100（2 年前发布的旧芯片）：
- 2 年前：$1.73/hr
- 2024 年 8 月：停止下跌
- 之后：**持续上涨**

> "It's a good time to be a drug dealer." — 一位独角兽创始人在 compute crunch 中的消息

## 为什么不是商品

### 1. 不可互换（not fungible）
- 不同厂商（AMD vs Nvidia）不互换
- 同厂商不同代（H100 ≠ GB200 ≠ B300）不互换
- 电力是可互换的（1 MW = 1 MW），compute 不是

### 2. 难预测
- 训练：尖峰式（hero runs）
- 推理：昼夜循环
- 研究方向变化快

### 3. 集中囤积
大玩家抢购 land + power + shell + chips——"Not sure which breakthrough will do it, might as well buy it all up."

## 基础设施周期历史

Midha 请 Claude 整理的案例：
- **钢铁 1867-1895**：上涨 → 1873 恐慌 → 崩溃 → 标准化
- **光纤**：Cisco、Lucent、Nortel、WorldCom
- **DRAM**：暴涨暴跌
- **航运**（Baltic Dry）
- **铀 1970s**：政府干预稳定

**平均周期长度**：
- 数字基础设施：2.8 年
- 物理基础设施：6.3 年
- **AI**：是两者的结合——物理资源产出数字收入 → 新领域

## 从独占到可用：需要两件事

历史规律显示，将稀缺资源转为可用大宗商品需要：

### 1. 标准
- ACDC（电力）、TCP/IP（网络）
- 大家同意的格式

### 2. 机构
- 强制执行标准
- 协调人类采纳
- 有时是行业自律，有时需政府

**今天 AI compute 处于标准化之前的时期。**

## 合成商品的定义（经济学）

- 共同单位
- 标准交付接口
- 互联互通与集中池化
- 计量、控制、结算
- 买家可以替换卖家的单位

**今天的 AI compute 全部都不满足。**

## 给学生的作业

1. 未来几年如何实现 compute 的和平过渡？
2. 你在其中的角色？（博客、推文、写作、参与标准化）

## Jensen Huang：compute 是智能的唯一约束

[[jensen-huang|Jensen]]（[[nvidia]]）从需求侧给出同一判断的另一面：四条 scaling law 最终都收敛到「intelligence is gonna scale by one thing, and that's compute」（见 [[scaling-laws]]）。他进一步论证计算的「用途」也变了——从 retrieval-based 的仓库变成 generative 的**工厂**，因此世界 GDP 中用于计算的比例会是过去的 **100×**（见 [[token-economics]]）。这解释了本页描述的 CapEx 狂潮与 H100 涨价并非泡沫式反常，而是需求侧结构性变化的映射。NVIDIA 用 [[extreme-co-design]] 把 tokens/sec/watt 每年拉高一个数量级，正是在缓解本页所说的「不可互换 + 集中囤积」压力。

## CS153 补充：大学 compute crunch + 能源总量

来自 [[jensen-huang|Jensen]] 的 [[cs153-jensen-huang-compute|CS153 讲座]]：
- **不是缺芯片，是体制问题**：「There's plenty of chips. If the president of Stanford places an order, I'll deliver it.」真问题是各系各自拉 grant、没人合并，单笔不够买校级共享算力，世界又搬去了人手一台笔记本。解法：聚合建**校级共享超算**、「$40B endowment 切 $1B 做成给每个学生/研究者的 AI cloud」——这为本页「compute 不是商品、需要机构协调」提供了一个具体的机构失灵案例。
- **能源总量**：未来计算所需能源「likely **1,000× more** than we currently have」；能效是可控杠杆（tokens/watt 已 +50× 且复利）。能源作为 compute 之上的**实体地基**详见 [[ai-energy-bottleneck]]（[[scott-nolan]] / [[general-matter]]）——即便「电力可互换（1 MW=1 MW）」，你也得**先有电**。

## CS153 补充：供给/交期的物理现实（Vahdat / Altman / Nadella）

[[amin-vahdat]]（[[value-per-gigawatt]]）在 CS153 给出数据中心运营者视角的**供给与交期现实**：1 GW 产能约合 **$40–50B**；净新增 GW 的 lead time 要 **2–3 年**；电力公司如今要求 **20 年 take-or-pay** 长约（电网已无 slack）；小于 **100MW** 的孤立站点会被 stranded；而 **watts 与 space 在不同芯片世代间是可互换的**，因此要先把**电力信封（watt envelope）**圈下来、再逐代填芯片，并且**每天重新规划（replan daily）**。需求侧上，[[sam-altman]] 称这是一场「gigantic compute shortage… shortage forever」（需求无上限），[[satya-nadella]] 则把负载归为三类主导 workload——**训练 / 推理 / 长时运行的 agent**。这些都为本页「compute 不是商品、需要机构协调」的论点补上了电力与交期这层硬约束。

## 来源
- [[cs153-frontier-systems]]
