---
title: "网络效应（Network Effects）"
tags: [network-effects, moats, platforms, venture-capital, systems]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[ben-horowitz]]", "[[venture-capital-systems]]", "[[cs153-ben-horowitz]]", "[[marc-andreessen]]", "[[sam-altman]]", "[[y-combinator]]"]
---

# 网络效应

本页忠实转录 [[ben-horowitz|Ben Horowitz]] 在 [[cs153-ben-horowitz|Stanford CS153]] 中给出的框架——他既把网络效应当作**最强的 moat**，又把 **a16z 这家 firm 本身**设计成一个网络效应生意。

## 为什么是最强的 moat：N² 价值

网络的价值随节点数**近似 N² 增长**——每加一个节点，价值约增加 N²（Metcalfe 式直觉）：

> "It's basically like an N squared value, so every node you add kind of increases the value by N squared. So if you have five people on the network, that's 25. But if you have 6, that's... 36."

| 节点数 N | 近似价值 (N²) |
|---|---|
| 5 | 25 |
| 6 | 36 |
| … | … |
| internet 规模 | "invincible" |

一旦做到互联网规模，价值就**无敌（invincible）**：

> "Nobody's going to ever build a rival to the internet, or very unlikely."

因此在 AI 时代 **code 不是 moat、UI 不是 moat**（详见 [[venture-capital-systems]]）之后，网络效应（及其近亲——供应链关系、渠道）反而成为少数还站得住的护城河。

## 历史：网络效应为何一度"不可见"

- 大规模网络的时代始于**互联网**，但互联网很怪——**没有人拥有它**，是"第一个真正去中心化的网络"。人们从建在互联网上的东西获益，却不知道该怎么理解"网络"这种资产。
- 结果是早期投资人**看不懂**这些网络有多强：Facebook 早期融资时没多少人给钱——"That's why **Peter Thiel** was able to do it at a really good price." Twitter 同理。
- 直到这些网络"长到有力量"，人们才发现它们**多么不可战胜**。a16z 因深度参与互联网、Twitter、Facebook，对此有第一手理解。

## 最难的部分：bootstrap（冷启动）

Ben 强调网络效应真正难的不是"网络大了以后有多值钱"，而是**从 0 到有**：

> "The bootstrapping of any network is always the most difficult thing... how did **Alexander Graham Bell** sell the first telephone when there was nobody to talk to? That part is actually really hard."

一个 10 亿人的网络当然值钱，但没人在上面时，第一个用户为什么留下？这是 chicken-and-egg 问题，也是网络型创业的核心难点。

## 案例：把 a16z 自己 bootstrap 成网络

a16z 从第一天起就"把 firm 当作一个网络"来经营——**关系越多，网络效应越强**：

> "The more relationships that we have, the stronger our network effect."

于是做别的 firm 不做的事：去和**硅谷每一个工程师、每一个高管、每一家买技术的大公司**建立关系，让创业者"一接入就立刻变强"（tap into that network and become extremely powerful right off the rip）。

**从落后位置 bootstrap 的具体手法：**
1. **不给自己发工资**——别的 VC 拿管理费给自己开高薪；a16z 把钱**全砸在建网络上**（雇人去把大公司引进来）。
2. **HP enterprise briefing center 的 hack**——因为把前公司卖给了 HP，认识其 briefing center 的人；于是每周打电话问"这周谁来 briefing center、能给我们号码吗"，把这些来访大公司请到 a16z 自己的 briefing center 看 startups（还备好 donuts）。结果："we knew more big companies than VCs who had been around 50 years."
3. 面对既有系统的**免疫反应（antibodies）**——别的 VC 起外号 "a-ho"、天天说坏话；但**因为太恨 a16z，反而不愿抄它**在做的（有效的）事，这本身成了护城河。CMO 说这只是"marketing"，Ben 的回应是 "yeah, that's your job. This is working."

> 系统性含义：网络效应不仅是产品属性，也是**组织与 go-to-market 的设计选择**。谁先付出高昂的 bootstrap 成本、把不对称资产（HP 关系、不发工资的现金）投进去，谁就先点燃飞轮。

## 网络效应也会"腐化"文化

Ben 顺带指出网络效应生意的**副作用**：

- **它能掩盖平庸**。Zuck 20 岁时"其实不太行"——"if he didn't have a network effect business, that wouldn't have worked at all"；正是网络效应带来的 **vertical takeoff** 给了他成长为如今这样的空间。
- **它会养出松弛的文化**。他把某个阶段称作 "the fat, happy network effect era"——那时"人人都想给公司价值观投票"，CEO 妥协，结果对谁都不好。他认为**这套已经过去，硬派文化又回来了**（详见 [[ben-horowitz]] 的"文化=行为"）。

## 与 VC / 平台的关系

- a16z 作为"平台/agency 型 VC"的更大系统设计（集中控制、拆成可对话的小组、founder-first 等）见 [[venture-capital-systems]]。
- AI 时代对 moat 的重估（code/UI 失效、供应链与渠道成为新护城河，Navan 案例）同样见 [[venture-capital-systems]]。

## 规模下的涌现：YC batch 的网络效应（CS153）

[[sam-altman]] 在 CS153 把 **YC batch 的网络效应**举为一个典范级的**规模涌现属性（emergent property at scale）**——这种「魔力」只有当你以旧 batch 规模的 100× 去投创业公司时才会出现；当年不少聪明人反而劝 [[y-combinator]] 缩小规模，事后看是错的。这与本页「网络长到有力量才显出多么不可战胜」的主线一脉相承，也呼应 [[intelligence-as-utility]] 的规模涌现主题。

## 相关

- [[ben-horowitz]] · [[venture-capital-systems]] · [[marc-andreessen]]
- [[frontier-systems]] · [[cs153-frontier-systems]]

## 来源

- [[cs153-ben-horowitz]]
