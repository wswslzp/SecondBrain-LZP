---
title: "AI Compute 基础设施经济"
tags: [ai, compute, infrastructure, gpu, markets]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[frontier-systems]]", "[[anjney-midha]]", "[[context-feedback-loops]]"]
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

## 来源
- [[cs153-frontier-systems]]
