---
title: "Stanford CS153 | Joe Sullivan on The Road Ahead: Resilience Required"
author: "Joe Sullivan"
date_ingested: 2026-07-19
date_published: 2026-05
tags: [cybersecurity, resilience, transparency, ai-security, leadership]
url: "https://www.youtube.com/watch?v=g50FHC-PzK8"
---

# Stanford CS153 | Joe Sullivan on The Road Ahead: Resilience Required

Stanford **CS153 Frontier Systems**（2026 春）playlist 第 3 讲，嘉宾为 [[joe-sullivan|Joe Sullivan]]——Uber 首任安全负责人、Facebook / Cloudflare 前 CSO/CISO、前联邦检察官，如今是安全顾问、Costanoa Ventures venture partner，兼一家帮助乌克兰儿童的 nonprofit（Ukraine Friends）CEO。属于 [[cs153-frontier-systems]] 系列，对应 [[frontier-systems]] 全栈框架里最顶层的 **治理 / 安全 / 信任** 一层。

这一讲的两条主线：一是 Sullivan 横跨 **政府 ↔ 科技** 交界处的职业弧线，以及那桩让他成为"史上第一个因公司安全事件被刑事起诉的高管"的 Uber 案；二是面向未来的 **AI 时代安全** 与贯穿全场的 title 主题——**resilience（韧性）**。核心概念沉淀在 [[cybersecurity-resilience]]。

> 讲座录制时间为约 2026 年 5 月：Sullivan 提到自己 2023 年 5 月 4 日的宣判"是三年零一周前"，且"一周前刚结束缓刑"。clipper 未捕获确切发布日期，date_published 为估算。

## 核心故事：Uber 案与转身

**职业弧线（government ↔ tech 交界处）**——1995 年从法学院毕业来北加州，在 **DOJ（司法部）** 做联邦检察官八年，是那个"死缠烂打要求把 internet 直连到自己办公桌"的人，因此成了办公室里唯一能上网的"守门人"。之后：2002 年 eBay/PayPal（信任与安全，eBay 早期业务模式是"把现金装进信封寄给卖家，然后祈祷发货"）→ 2008 年 Facebook（当时比 Myspace 还小；后来成为 NSA/[[snowden|Snowden]] 事件里代表 Facebook 与 NSA 打交道的人）→ 2015 年 Uber 首任安全负责人 → 2018 年 Cloudflare CISO。一个反复出现的模式：**"接手三个工程师，建成一个大团队"**，在 Facebook、Uber、Cloudflare 各来了一次。

**Uber 数据泄露（2016 秋）**——两名黑客（佛州 19 岁、多伦多 20 岁，在游戏社区认识）发现 Uber 的 **AWS 配置错误**，拿到了 **5700 万人** 的数据。Uber 按 **bug bounty** 流程处理：付了 **$10 万**、legal 签字、CEO 批准、全程用中心化 tracker 记录，并派了一位受过专业训练的 **前 CIA 审讯官** 去核实数据已被删除（还做了一份约六页的心理画像）。legal 判断无需对外披露。

**刑事案（2020 起诉 → 2022 定罪 → 2023 宣判）**——2020 年 Sullivan 因公司未披露此事被 **个人起诉**，罪名为 obstruction of justice（妨碍司法）+ misprision of a felony（隐瞒重罪）。感恩节休假期间，Bloomberg 记者 Eric Newcomer 的标题**"I paid hackers to delete stolen data on 57M people"** 引爆全球；危机正中，他自己团队因公司决定解雇他而 **远程 brick 了他的 Uber 手机与电脑**。2022 年 10 月败诉，卡在一个 **全新的法律问题**：公司能否在访问发生后 **追认授权**（类比"事后把闯入者请进门"）？在 **18 USC 1030**（计算机入侵法）下，法官指示陪审团 **"Uber 无权给予许可"**，等于抽掉了整个辩护。2023 年 5 月 4 日宣判，法官说了那句最重要的话 **"it wasn't a cover-up"**，并当庭训斥检方（"要起诉公司，为什么不起诉 CEO？CEO 全程在 loop 里"、"Joe 没有任何经济动机"），最终判 **三年缓刑**（政府先求三年监禁、后改 18 个月）。安全社区寄给法官 **200 多封求情信**（一封 60 人联署、一封 50 人、一封 40 人），Sullivan 自嘲这是"我自己的 Irish wake（爱尔兰守灵）"——活着听到大家说自己的好话。

**转身**——败诉后没人敢用他，唯一愿意合作的是乌克兰人（"他们无所可失"）。他做了 Ukraine Friends CEO，发起 **Digital Wings**，把科技公司 help desk 后面成堆的旧笔记本运给失去父母的乌克兰儿童（至今已运数千台，还成了锂电池空运安全专家）。后来在 DEFCON / Black Hat CISO Summit 第一次公开讲自己的案子，获得同行 standing ovation，重建声誉，开了自己的安全咨询公司。

> 详细的法律经过与责任披露史见人物页 [[joe-sullivan]]。

## AI 时代的安全

Sullivan 认为 cybersecurity 自 2016 年以来已彻底改变——从只关心"data 有没有离开大楼"（data exfiltration），扩展到 **operational resilience（运营韧性）** 与 **AI 带来的全新攻防**。这些论点系统整理在 [[cybersecurity-resilience]]。

- **代码量爆炸（vibe-coding velocity）**——他合作的一家小银行两个月内从每月 25 万行代码涨到 **125 万行**。见 [[vibe-coding]]。
- **非工程师上生产**——一位市场部员工把一个漏洞 merge 到 production，却看不懂修复方案；传统 AppSec"安全提方案、工程师应用"的模式就此失效。非技术员工用 [[claude-code|Claude Code]] 这类工具会更激进地对外连接（甚至自建外部服务器、自造 API key）。
- **Agents as toddlers（智能体像学步的幼儿）**——你无法按用途给 agent 划 guardrail（"能写邮件用于目的 A，但不能用于目的 B"做不到）；需要的是 **runtime anomaly detection（运行时异常检测）**——"公司里的 agent 就像屋里的幼儿，你得贴身跟着跑"。关键不是它 **有** 什么权限，而是它 **拿权限去做了什么**。呼应 [[agent-comfort-zone]]。
- **Anthropic 的 "Mythos" / Cyber 模型**——[[anthropic|Anthropic]] 把一款强大的 cyber 能力模型交给约 **8 家具名公司**（外加若干未公开的）。Sullivan 有合作方 day-one 拿到访问权，评价"amazing and scary"；这类能力约 **6 个月后就会公开可得（哪怕来自 open-source）**，所以 cybersecurity 必须"step up"。他称赞 Anthropic 在品牌/沟通上的处理（刚打完与 Department of War 的仗，转身以"高尚地帮世界做安全"亮相），也提到社区的 backlash（"我没访问权、这是 hype"）。用这些模型需要围绕它搭 **harness**——用现有公开模型配好 harness 也能挖出很多同样的东西。见 [[openai|OpenAI]] 与 Anthropic 都在做的 cyber 模型。
- **Ransomware（勒索软件）的演变**——最早是 **国家支持的破坏性攻击**（Saudi Aramco、Sands Casino ← 伊朗；Sony ← 朝鲜，归因正是 Sullivan 在 Facebook 的团队做的）→ 如今已成一个 **产业**（很多公司把 ransomware negotiator 常年 on retainer）。**Colonial Pipeline** 是第一起真正冲击普通美国人的攻击。**Jaguar Land Rover**（2025 年，停产三个月、英国政府 **10 亿英镑+** 纾困、供应链多家小公司倒闭）说明安全已是 operational resilience，而非仅数据外泄。
- **Regulation（监管）**——支持 *smart* regulation："在规模之上需要监管来保护人，纯为赚钱而存在的公司不会主动保护每个用户。" 举例 Facebook 上非洲异见者以公司从未设想、且没有商业激励去保护的高风险方式使用产品。政府正把私营部门的人拉进来（点名 Emil Michael 代表 Department of War 与 Anthropic 谈判）。
- **物理 / 内部威胁**——IP theft 是创业公司第一忧虑；员工因国内家人被胁迫；高管遭绑架、加密货币私钥的 "wrench attack"（乃至断指取指纹解锁金库）；提到近期 [[sam-altman|Sam Altman]] 的安全惊魂。
- **Quantum risk（量子风险）**——**"harvest now, decrypt later"**：各国机构正大量吸走加密数据，等量子（约 2030）到来再破解；大多数主干基础设施届时会 quantum-resistant，风险主要落在 Google/AWS 等大厂身上。

## 金句

> "It wasn't a cover-up." —— 宣判日法官的话，Sullivan 说这是他"这辈子能听到的最好的话"。

> "Who's writing the blog post?" —— Cloudflare CEO Matthew Prince 对安全事件的第一反应（CTO 加入应急房间只为记录、保证透明）。

> "You're going to get punched in the face sometimes... a boxer still has a plan."

> "Agents inside companies are like toddlers inside a house. You run next to them. It's not that they have access, it's what they do with it."

> "Run towards those stressful situations, because the more you go through them, the better you'll handle them... If you try to steer your career to never go through bad things, you'll never get the wisdom."

> "That type of model being held close right now is going to be publicly available in six months, even if it comes from the open-source guys. Cybersecurity needs to step up."

## 关联页面

- [[joe-sullivan]] —— 人物页（职业弧线 + Uber 案完整经过）
- [[cybersecurity-resilience]] —— 概念页（透明、责任披露/赏金、韧性与危机沟通、agents-as-toddlers、运营韧性、AI cyber 模型）
- [[frontier-systems]] · [[cs153-frontier-systems]] —— 课程框架
- [[anthropic]] · [[claude-code]] · [[openai]] · [[vibe-coding]] · [[agent-comfort-zone]] —— AI 安全交叉引用
- [[sam-altman]] —— 高管人身安全（"wrench attack"语境）
