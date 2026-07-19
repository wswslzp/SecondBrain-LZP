---
title: "CS153 '26: Energy Bottlenecks — Scott Nolan, General Matter"
author: "Stanford CS153（讲者 Scott Nolan / General Matter）"
date_ingested: 2026-07-19
date_published: 2026-05
tags: [ai, energy, nuclear, uranium-enrichment, haleu, smr, compute, infrastructure, cs153]
url: "https://www.youtube.com/watch?v=wisccQYTRQc&list=PLoROMvodv4rN447WKQ5oz_YdYbS74M5IA&index=7"
type: lecture-transcript
---

# CS153 '26: Energy Bottlenecks — Scott Nolan（General Matter）

Stanford CS 153（2026）第 7 讲。主讲人 [[scott-nolan]]，[[general-matter]] 创始人兼 CEO、前 Founders Fund 合伙人、SpaceX 早期工程师。对谈者是课程主理人 [[anjney-midha]]（a16z），Mike Abrash 在场。这一讲把镜头从 AI labs「拉远」（zoom out），进入 [[ai-factory|AI 工厂]] 里最上游、也最被忽视的一层：**energy / electricity**。

## 核心论点

Scott 用一串「five whys / 五个为什么」把 AI 的瓶颈一路往上游追：**compute → power → 电网扩张 → baseload → 核能 → 核燃料 → 浓缩铀（enrichment）**。结论是一句反直觉的话——**「enrichment is the bottleneck all the way through to AI on a five-year time frame.」** 铀浓缩这一步（美国今天全球市占 <0.1%）在五年尺度上是 AI scaling 的真正卡点，而 General Matter 正是在把这一步「带回美国、规模化、在成本上完胜」。完整框架见 [[ai-energy-bottleneck]]。

## 权威背书：能源才是瓶颈

Scott 开场引用三位「站在数据中心/模型最前沿」的人，全都指向能源：

- **Sam Altman（OpenAI）** 参议院作证：「everything is going to converge to the cost of energy, to the cost of electricity. Chips are going to get cheaper, models are going to get cheaper, but energy is fundamentally what you consume when you're running these models.」
- **[[jensen-huang|Jensen Huang]]（[[nvidia]]）**——「他的激励本该是说芯片才是瓶颈」，但他在 Joe Rogan 播客上也承认 **energy is actually the bottleneck**。
- **Elon Musk**——众多瓶颈里他要突出的也是 energy（对应 SpaceX 的在轨发电计划）。
- 还有一位（讲者念不清姓名的）前 Stanford 教授主张：所有货币/成本都应以 **joules（焦耳）** 计价——与上面收敛到能源成本是同一件事（见 [[token-economics]]）。
- 连 Financial Times 都意识到：数据中心与 compute 的上游是 **power**。

## 关键要点

### 供应链的滞后与两次 crunch
- 「It takes two years to tape out chips and stand up data centers.」芯片流片 + 数据中心建站要两年。
- ChatGPT（2022 年底）= 第一个 **consumer killer app** → 2023 初出现巨大 **compute crunch**，短暂还叠加 **energy crunch**。
- Claude 4.6（2025 年 12 月）= **enterprise killer app** 的「Groundhog Day 时刻」：寒假回来的成年人把 Claude 用进工作，企业需求爆发。

### 需求侧：super-linear，电网却近乎停滞
- 电力需求「way super linear」，一个十年内奔向 **1 terawatt**。
- 但美国过去 20 年电网扩张几乎「没干什么」——需要从「almost a complete standstill 到 nearly vertical」，要走 **China-like slope**，甚至比中国更陡（图中黄色部分）。

### 供给侧的逐层筛选
1. **Stranded energy（搁浅电力）**：五年前够用——偏远水电、孤立地热、West Texas 的 stranded wind 等「有供给没需求」的电。最早的 builds 是 **Bitcoin 矿场**（不需要多少 fiber，iridium 卫星连接即可）。**Crusoe** 从比特币起步、如今在 West Texas 做 **Stargate**（接风电 + 天然气）。但优质 stranded 资源已被抢光，且体量也不够了。
2. **Uptime 需求** 让数据中心难以直接吃 solar/wind（要巨量电池，成本太高）。近两年主力是 **天然气涡轮机（turbines）**，但涡轮机紧缺、交期数年、产能不跟涨。
3. 想要 **baseload + 低碳 + 安全** → 指向 **核能**：核电碳排最低、安全性与风电基本并列最好，所以 hyperscalers 都在看核能。但核能是 **5–10 年** 才真正上量，不是一夜建成。
4. 于是：核能是电力的长期扩张限制器，电力是 AI 的瓶颈 → **核能是 AI scaling 的瓶颈（在陆地上）**。
5. 核能的瓶颈？反应堆要 **燃料**（每 1–2 年换料，先进堆 5–10 年），燃料走五步供应链，卡在中间的 **enrichment（浓缩）**——美国 <0.1% 市占。且 enrichment 往往是先进核燃料里**最大的成本项**。

### 铀燃料五步供应链
1. **Mining（采矿）**——得到矿产（U3O8）。
2. **Conversion（转化）**——U3O8 → **UF6** 气体。
3. **Enrichment（浓缩）**——分离 UF6，提高裂变同位素 **U-235** 浓度。← General Matter 做的那一步、美国缺失的一步。
4. **Reconversion（再转化）**——气体经化学过程变回固体。
5. **Fabrication（制芯/制棒）**——压成燃料 pellet / fuel rod。

其余四步美国都有选项，唯独第 3 步 enrichment 几乎为零。General Matter 只做分离——**厂内无核反应**（材料铺开、避免 critical mass）、**无化学反应**，纯 separation。产品可覆盖 5% LEU（供占美国电网 20%、零碳排的现有反应堆）与 **HALEU**（先进堆 / SMR / microreactor）。

### 美国 enrichment 兴衰史
- 1980s：美国占全球 enrichment **约 86%**，在几处 DOE 站点（前 Manhattan Project / 冷战设施、政府运营）。冷战期达峰，自给全部民用核电燃料。
- 柏林墙倒 → 与俄自由贸易 → **Megatons to Megawatts** 计划（拆解俄核弹头 down-blend 后进美国反应堆）。
- 美国当时技术相对昂贵、不经济，干脆走自由贸易，从俄/欧进口 → 国内 enrichment 关停，**最后一座 2013 年**（Paducah, Kentucky）。
- AI 让需求提前到来——「back to the future」，美国正把这一步重启。

### General Matter 的执行
- 2024 年 1 月成为公司；此前 fall '23 组队、Dec '22 起 Scott 已在琢磨；用 2023 一整年做 five whys。
- 团队近 **100 人**，抽调自 national labs、其他核能公司、**Tesla、SpaceX**（复用打入资本密集、被在位者主导、停滞行业的 playbook）。头几个月 100-hour weeks。
- 2026 年 1 月拿下 DOE **$900M** 合同（原合同期到 2034，但公司目标是 **十年内先上线**、随后快速扩产）。跨 Biden→现政府一致支持（先 HALEU 后 LEU），国会两党 + DOGE 助推。
- 选址：**Paducah, Kentucky**——上一座美国商业 enrichment 所在城市，DOE 站点南端一块从未开发的 **100 英亩**；8 月奠基。HQ 在 LA。
- 就业：LA 未来几年约 500，Kentucky 相当或更多，合计约 **1000** 个新岗位——被 [[anjney-midha]] 当作「AI 净创造新岗位」的活证据。

### 长期使命与地缘
- 长期还想为「不做 enrichment 的盟国」低成本供货——用极低成本让别人「懒得自己搞」，从而带来 **nonproliferation（防扩散）** 的下游收益。呼应 [[sovereign-ai]] 里的能源/供应链主权与国家安全。
- Kazakhstan、Canada、Australia 有顶级铀矿（哈萨克约占全球 **40%** 矿产），各国应聚焦各自最擅长的一步；理想上化学处理等步骤应 colocate。

### 核能认知与对照
- 安全记录：Three Mile Island **无可测直接死亡**；Fukushima 或许 1 例，但海啸致数千死。
- 反面教材：**德国** 关停正常运行的反应堆，实际未用可再生替代，而是回到煤/天然气 → 空气质量对比法国（高核电占比）「德国红、法国蓝」。
- 公众舆论近几年已从「反核为主」翻转到「支持为主」。产业下一步要解决的是**前期造价太贵**（Elementl、Oppenheimer Energy、各家 SMR 工厂化量产）。

## 与既有页面的联动

- [[compute-infrastructure]]：Midha 说 compute 今天「不是大宗商品」；有意思的对照是该页指出 **电力是可互换的（1 MW = 1 MW）**——但 Scott 说明的是「即便电可互换，你也先得有电」，他补的是 compute **下面** 的那一层。
- [[nvidia]] / [[jensen-huang]]：Jensen 在 Joe Rogan 上承认 energy 才是 blocker；NVIDIA 侧的解法是先吃电网**闲置容量**这块 low-hanging fruit，并用 [[extreme-co-design]] 把 **tokens/sec/watt** 每年拉高一个数量级。
- [[frontier-systems]]：本讲正对应 AI 全栈里的 **土地 / 电力 / 外壳** 那一层，也是 4 Cs 之外常被忽视的实体约束。

## 相关页面
- [[scott-nolan]]
- [[general-matter]]
- [[ai-energy-bottleneck]]
- [[compute-infrastructure]]
- [[nvidia]]
- [[jensen-huang]]
- [[frontier-systems]]
- [[cs153-frontier-systems]]
- [[token-economics]]
- [[sovereign-ai]]
