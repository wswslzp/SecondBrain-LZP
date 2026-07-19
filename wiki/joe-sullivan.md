---
title: "Joe Sullivan"
type: entity
tags: [person, cybersecurity, ciso, leadership, resilience]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[cybersecurity-resilience]]", "[[cs153-joe-sullivan-resilience]]", "[[anthropic]]", "[[cloudflare]]", "[[frontier-systems]]"]
---

# Joe Sullivan

安全领域最出名、也最具争议的高管之一：Uber 首任安全负责人、Facebook 与 Cloudflare 前 CSO/CISO、前联邦检察官——**史上第一位因公司安全事件被个人刑事起诉的高管**。如今是独立安全顾问、[[costanoa-ventures|Costanoa Ventures]] venture partner，兼 nonprofit **Ukraine Friends** CEO。他在 [[cs153-frontier-systems|Stanford CS153]] 的一讲（[[cs153-joe-sullivan-resilience]]）把自己的 Uber 案讲成一堂关于 [[cybersecurity-resilience|韧性]] 的公开课。

## 职业弧线（government ↔ tech 交界处）

贯穿一生的主题：**始终站在政府与科技公司相遇的交界处**。

- **DOJ 联邦检察官（1995–2002）** —— 法学院毕业来北加州，做了八年联邦检察官。那个"死缠烂打要求把 internet 直连到 DOJ 办公桌"的人，因此成了办公室唯一能上网的守门人。会挨家跑硅谷公司问"讲讲你们的 cybercrime，我想起诉"——早期公司毫无披露激励，靠建立信任才慢慢换来真话。
- **eBay / PayPal（2002–2008）** —— 建 legal 与 safety/security 两条线。eBay 早期业务模式是"把现金装进信封寄给卖家，然后祈祷发货"；PayPal 与数字支付解决的正是"信任"这个头号问题。为 eBay 跑了 50 州里的 46 个、并在十多个国家培训执法。**2007 年在 PayPal 发布史上第一份 responsible disclosure policy**。
- **Facebook（2008–2015）** —— 加入时 Facebook 比 Myspace 还小。**接手三个工程师，建成大团队**（此模式后在 Uber、Cloudflare 各重演一次）。是 [[snowden|Snowden]] 事件中代表 Facebook 与 NSA 打交道的人。约 2010–2011 年 **发布史上第三个 bug bounty 计划**。也是他团队做出"Sony 被朝鲜攻击"的归因并分享给 FBI。
- **Uber（2015–2017）** —— 首任安全负责人，约 40 名旧团队成员随他从 Meta 转投（触发 Meta 总法律顾问的警告信）。见下文案子。
- **Cloudflare CISO（2018–）** —— 被 Uber 解雇、遭 doxing 之后加入。CEO [[matthew-prince|Matthew Prince]] 做了尽职调查、"愿意赌一把"。在这里他把 **transparency** 内化为核心价值观。
- **今天** —— 自营安全咨询公司（服务同时期 3–4 家 startup），做安全公司顾问，Costanoa venture partner，Ukraine Friends CEO。因"大公司不能公开与 felon 合作"，更多拥抱 startup（"startup 不在乎，只想要最好的安全"）。

## Uber 案（这一讲的脊梁）

- **泄露（2016 秋）** —— 两名黑客（佛州 19 岁、多伦多 20 岁，游戏社区相识）发现 Uber 的 **AWS 配置错误**，触及一批已废弃旧数据库，暴露 **5700 万人** 数据。Sullivan 收到邮件后按惯例转给管 bug bounty 的 product security 团队（Rob Fletcher 主导对接）。
- **按 bug bounty 处理** —— 付 **$10 万**、CEO 签字批准、两三名 lawyer 与 communications 团队全程在 loop、中心化 tracker 记录一切；legal 判定无需披露。Sullivan 追加要求：查出对方身份、派 **前 CIA 审讯官** 上门核实数据已删（做了约六页心理画像）。同期 FBI 也在追这两人却没找到，Uber 团队先找到了。
- **刑事起诉（2020）** —— 罪名 obstruction of justice + misprision of a felony，让他 **个人** 为公司未向正在调查的政府机构披露而担责。**Bloomberg 标题"I paid hackers to delete stolen data on 57M people"** 在他感恩节休假时引爆全球；危机正中，自己团队因公司决定解雇他而 **远程 brick 了他的 Uber 手机与电脑**。此后两个月"蛰伏、留胡子、不想露面"。
- **败诉（2022 年 10 月）** —— 卡在一个 **全新法律问题**：在 **18 USC 1030** 下，公司能否在访问 **之后** 追认授权（律师一贯类比 trespass——"你可以事后把闯进前院的人请进来，就不算侵入"）。陪审团发问后，法官不确定，采纳政府主张，指示 **"Uber cannot give permission"**，抽掉整个辩护——即便他获得 legal 批准、不认为做错，仍可被判妨碍司法。
- **宣判（2023 年 5 月 4 日）** —— 法官当庭说 **"it wasn't a cover-up"**（Sullivan："这辈子能听到的最好的话"），并训斥检方：**"要起诉公司，为什么不起诉 CEO？"**（CEO 全程在 loop、支持每个决定）、"Joe 没有任何经济动机"，"我这辈子没见过这样的案子"。最终 **三年缓刑** + 小额罚款（政府先求三年监禁、后改 18 个月；probation office 直接建议只给缓刑）。安全社区寄给法官 **200+ 封求情信**（60/50/40 人联署各一封），他自嘲这是"我自己的 Irish wake"。缓刑于讲座前约一周结束。

> 反思：技术操作层面"everything we did, I would do the same"，唯一想改的是 **更多文档**。因此他现在投资/顾问 [[breachrx|BreachRX]]——一个逼 legal 与 communications 在事件中更早、更直接与 security 协作的平台。

## 核心信念

- **Transparency > cover-up** —— 见 [[cybersecurity-resilience]]。Cloudflare 模式（"who's writing the blog post?"）为其范本；不透明（Uber 2016）会积成"boiling negativity"。
- **Responsible disclosure & bug bounty** —— 他亲手推动了这段演进：从"起诉黑客"→"承诺不告不诉"（PayPal 2007）→"付钱给他们"（Facebook 第三个 bug bounty，约 2011）。第一次收到"付钱换漏洞"邮件时作为前检察官"double mad"，被团队一句"Joe, shut up, we should be paying these people"点醒。
- **安全 leader 的真正 team 是其他高管** —— 一个 trick question："tell me about your team"（答案不是 detection/AppSec 小组，而是公司其他 executives）。Facebook 的 exec coach 让他花 50% 时间在其他高管身上，他认为安全 leader 应更高。
- **Resilience** —— "你会挨拳，要有挨拳的计划";"run toward stressful situations——智慧来自扛过糟糕的事"。

## Sources

- [[cs153-joe-sullivan-resilience]]

## 相关

- [[cybersecurity-resilience]] · [[frontier-systems]] · [[cs153-frontier-systems]] · [[anthropic]] · [[sam-altman]]
