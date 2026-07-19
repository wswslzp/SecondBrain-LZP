---
title: "风险投资作为系统（Venture Capital as a System）"
tags: [venture-capital, systems, a16z, moats, startups, ai]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[ben-horowitz]]", "[[network-effects]]", "[[cs153-ben-horowitz]]", "[[marc-andreessen]]", "[[frontier-systems]]"]
---

# 风险投资作为系统

[[ben-horowitz|Ben Horowitz]] 在 [[cs153-ben-horowitz|Stanford CS153]] 中把 **VC 当作一个可以设计、可以规模化的系统**来讲——a16z 被称为"venture capital 系统设计上最重要的创新之一"。本页转录他的核心框架。对应 [[frontier-systems]] 4 Cs 里的 **Capital**（与 **Culture**）。

## 起点：两个"过时"的假设（2009）

a16z 成立时，Ben 认为业界有两个陈旧前提：

1. **VC 只是一个投资产品**——对 LP（投资人）的产品很好（高回报），但**对创业者的产品很差**："they didn't do much for you other than give you money." → a16z 要给创业者做一个**更好的产品**。
2. **每年只有约 15 家公司能过 \$100M 收入**——历史数据确实支持，于是整个行业只是在抢投这 15 家，限制了整个盘子的大小。a16z 反过来赌 **software was going to eat the world**，未来每年能过线的会是 **~200 家**。

这两个赌注要成立，就必须解决一个 VC 历来不做的事：**规模化**。

## 规模化 VC 的系统设计

VC 历来不 scale（"不需要"）。Dave Swensen（最著名的 LP）说过：

> "A good venture capital firm is like the size of a basketball team, five guys and then a six man."

但要"给创业者做好产品 + 投更多公司"，五六个人远远不够。a16z 的几个"听起来很简单却很重要"的系统想法：

### 1. 不共享控制权，只共享经济利益
传统 VC 是 partnership，合伙人**同时**共享经济利益与控制权。问题：控制权共享 → 组织无法改变，因为凡事都要所有人同意；而任何 reorg 都是权力再分配，总有人恨它（不一定是能力差的人，只是没人喜欢失去权力）。

> "We'll share economics, but we'll centralize control."

集中控制让 a16z 能不断重组、扩张进新品类——**American Dynamism、crypto、bio** 等。

### 2. 保持"能真正对话"的小组
投资本质是**一场追求真相的高保真对话**；房间里的人不能多到无法对话：

> "You never want more people in the room than can have a conversation... you can't have a conversation with 30 people. That's a presentation."

有很好的化学反应/默契时，上限约 **7 人**；否则更少。因此 a16z 的做法是**不断把 firm 拆成越来越小的组**，每组盯市场的一部分。

### 3. 用一次"疯狂"的下注建立信誉：Skype
第一支基金约 **\$300M**，a16z 把其中 **1/4** 投进 Skype 收购——所有人都觉得疯了，但他们知道别人不知道的事：
- Skype 从 eBay spin out 时，**eBay 买了公司却没买 IP**（"never buy the company without buying the IP"）；IP 是**控制通信协议的底层 library**（很难替代），握在创始人 Janus 与 Niklas 手里，理论上能起诉并关停服务，所以外界视之为"unbuyable asset"。
- 但 a16z 认识创始人，知道 **Skype 是定义他们人生的东西**，绝不会关掉它——问题只是"要多少钱、要不要董事席位"。
- 赌成之后，别人开始觉得"也许你没完全疯"。**系统含义**：一次高信念、信息不对称的下注，能为一个从零起步的 firm 建立信誉。

### 4. 把 firm 建成网络效应
"we always thought of the firm as a network"——完整框架（N² 价值、bootstrap 之难、HP briefing center 的 hack、免疫反应）见 [[network-effects]]。

## AI 如何改变 VC 的底层假设

Ben 认为 AI 带来了他整个职业生涯里最根本的变化：

### 1. "现在可以砸钱解决问题了"
过去技术公司的铁律是**不能靠砸钱追赶**——"nine women can't have a baby in a month"，通信开销会吃掉一切（"what's a [mythical man-month]? It's like 700 IBMers before lunch"）。

AI 反转了这条：**"if you have enough GPUs and enough data, you can basically solve most problems right now."** → **资本竞赛**第一次变成真的。

### 2. moat 的重估
> "Code is not really a moat the way it was in the past. And user interface isn't really a moat."

新问题变成：你的 **barrier to entry** 是什么？在 code/UI 失效后，护城河转向**网络效应、供应链关系、渠道、政策/合规**等。

### 3. 需求几乎无上限
产品好用到不可思议，所以采用极快——"companies go from \$9 to \$30 billion in run rate in six weeks"。对比旧世界：Siebel 软件部署要两年、至少 \$1M，这本身就限制了需求。**技术足够好时需求没有上限。**

### 4. 好点子的形状
> "Anything that needs to exist that doesn't otherwise exist is a good idea."

世界并不需要"又一家 VC"，但需要"一种不同的 VC"——这正是 a16z 存在的理由；OpenAI 同理（世界需要一个 Google 之外的 AI 替代品）。反面是 **SaaSpocalypse**：重建一个便宜版 Salesforce 是"世界上最无聊的事"。

## 投资判断：投人 + founder-market fit

- **"We invest in founders"**——要 original thinkers、有 breakthrough thinking（marketing 也算，Cluely 为例）。判断可以极快：听 Scott Shenker 说 Matei Zaharia 是"十年来学界最好的分布式系统的人"，Ben 当场就决定投 Databricks，哪怕 pitch 烂得难忘。这是一种 [[judgment|判断力]]。
- **founder-market fit / "size it to you"**——别问"我要做多大的事"，问"我能解决什么问题"；从小问题长出大公司（Meta、Dropbox、Elon 的黄页→PayPal→Tesla→SpaceX）。"Trying to swallow the Earth from the beginning... is good for your pitch deck, but it's not good for your company."
- **唯一不可饶恕的罪：没钱了**——"there's only one unforgivable sin in business, and that's running out of money."（Slack 起死回生为例。）只要创始人特别、且没烧光钱，就不出局。

## VC 行业里正在变化的假设

- **瓶颈迁移**：从软件工程师 → **电力/能源**（呼应 [[frontier-systems]] 全栈里"土地/电力/外壳"层）。
- **公司变得极大**：到 **\$1B 收入**就需要 multi-country / multi-channel / multi-product 能力，多数 VC 从没有过，现在必须有。
- **私募市场缺公开市场的功能**，需要被补上。
- **投资人不能替公司做决策**："the investor can't run the company"——LP 只有过去的知识和对你在做什么的浅层了解，没有实时的完整 context（Yale/Swensen 至今仍是 a16z 的 LP）。

## 主动施加瓶颈：对 AI-LBO 说不

被提了 18 次的诱惑：像 spreadsheet 催生 PE 那样，用 AI 去改造老公司提效。Ben 拒绝，两个理由：

1. **文化上与 VC 相反**——VC 投"有新想法、要快速成长的创业者"；LBO 关心 entry price、提效、裁员，"I don't really want to grow it. I just want to make more money out of what it is." 不想把文化劈成两半。
2. **不想用人生做这个**——"you build a company to do something larger than yourself and make the world a better place. And then if you do that, you will make money."（呼应 [[wealth-creation]]。）

> 系统含义：**你不必因为哪里有钱就进哪个业务**；主动给自己的增长设瓶颈，以守住文化与使命。

## Wall Street vs Silicon Valley（估值 = narrative）

- **"Anytime Wall Street thinks one thing and Silicon Valley thinks another thing, that arbitrage is worth a lot of money and Wall Street's always wrong."**
- SaaSpocalypse 下"人人入狱，不论是否有罪"——"when the paddy wagon backs up to the house of ill repute, everybody goes to jail."
- Warren Buffett："in the short term, it's a voting machine. In the long term, it's a weighing machine." Wall Street **买 narrative，不买 facts**；等到季报（weighing machine）出来，"为什么一个据说被 [[anthropic|Anthropic]] one-shot 的公司还这么赚钱"，narrative 才会翻转。
- 真实 moat 的反例 **Navan**（企业差旅软件）：护城河是与全球每一家航司/酒店的**供应链关系**（爬网站会被 cease-and-desist 起诉出局）+ 卖给"travel manager"这种脏活——"there's gold bricks everywhere. They're not going to pick up a silver brick."

## 相关

- [[ben-horowitz]] · [[network-effects]] · [[marc-andreessen]]
- [[frontier-systems]] · [[cs153-frontier-systems]] · [[wealth-creation]] · [[judgment]]

## 来源

- [[cs153-ben-horowitz]]
