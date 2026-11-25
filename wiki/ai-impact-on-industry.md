---
title: "AI 对产业的影响"
tags: [ai, semiconductor, programming, career, industry, marketing]
date_created: 2026-04-11
date_modified: 2026-11-23
related: ["[[compute-infrastructure]]", "[[vibe-coding]]", "[[neuromarketing]]", "[[llm-wiki-pattern]]", "[[tasks-vs-jobs]]", "[[anthropic]]", "[[product-management-ai-era]]", "[[career-as-chapters]]", "[[yu-su]]", "[[yu-su-xiaojun-agent-history]]", "[[haozhe-wang]]", "[[harry-wang-beyond-silicon-chips]]", "[[liang-qiwei]]", "[[liang-qiwei-phantom-blade-zero-xiaojun]]"]
---

# AI 对产业的影响

AI 正在系统性地重写软件/硬件全栈、职业结构、营销和知识管理。

## 硬件层：存储芯片超级周期

AI 大模型从训练到推理阶段的转变，引发了存储芯片前所未有的需求。

- HBM（高带宽内存）涨幅超 1800%
- 全球存储芯片经历近年来最严重的供需失衡
- 云巨头抢占订单，手机/PC/汽车厂商承压
- 扩产面临三座大山：洁净室紧缺、设备商保守、制程摩擦

**风险**: 压缩算法迭代可能颠覆当前需求假设。

来源: [[ai-storage-chip-super-cycle]]

## Compute 基础设施：从商品到稀缺

[[compute-infrastructure]] 详述：
- Big Tech 2026 年 CapEx 达 $1.2T
- H100 价格**持续上涨**（2 年前芯片）
- Compute **不可互换**（H100 ≠ GB200 ≠ B300）
- 进入"标准化之前"时代

> "It's a good time to be a drug dealer." — Amp 的客户描述 compute crunch

来源: [[cs153-frontier-systems]]

## 软件层：程序员职业影响

### 立党（[[lidang]]）的观察
- **被替代的**: 低端重复性编程工作
- **不被替代的**: 定义问题的能力、理解大型项目复杂性的能力
- **核心观点**: 程序员的价值在于"定义问题"，而非"写代码"

> "换一个人都没有办法理解这个项目的所有细节" — 立党

延伸：[[lidang]] 在 [[lidang-ai-agent-tutorial]] 中进一步给出「不会编程者如何用 [[headless-agent-pattern|headless Claude Code]] 端到端办事」与「AI agent 的 [[agent-comfort-zone|封闭可验证舒适区]]」。

来源: [[ai-destroying-programmer-jobs]]、[[lidang-ai-agent-tutorial]]

### Dario 的观察：tasks vs jobs
[[dario-amodei|Dario Amodei]] 的框架（详见 [[tasks-vs-jobs]]）：AI 先自动化 tasks 而非整份 job；自动化 90% 时人在剩下 10% 上 10× leveraged，但逼近 100% 后必须为人找到新去处。他警告可能出现「高 GDP 增长 + 高失业 + 高不平等」的组合，并预测 1–5 年内或消灭 50% entry-level 白领岗位。

### Naval 的观察
- [[vibe-coding]] 让非程序员也能构建应用
- 传统软件工程师仍有不可替代的优势：用代码思考 + 能堵抽象泄漏
- **英语是新的编程语言**
- 程序员获得 5-10× 杠杆
- "No entrepreneur is worried about an AI taking their job" — 企业家只有极端能动性

来源: [[a-motorcycle-for-the-mind]]

### 市场结构
- **没有对平庸的需求** — 最好的应用赢得 ~100% 市场
- 头部：超级聚合者
- 长尾：填补任何细分
- **中型公司被摧毁**（5-20 人软件公司）

### SaaSpocalypse
[[anthropic|Anthropic]] 发布 Claude Cowork 后，软件板块**一夜蒸发 $285B 市值**（交易员称之为 SaaSpocalypse / 白领 wipeout，部分软件股连跌九日）。Dario 的解读：AI 让「pie 变大」，软件产业整体不缩小，但看不清趋势、认不清护城河的公司会成为「big losers」。详见 [[anthropic]]。

## 产品与组织层：从 information mover 到 builder

[[nikhyl-singhal]]（Skip，前 Meta/Google/Credit Karma）在 CS153 给出组织内部的重构画像（详见 [[product-management-ai-era]]、[[career-as-chapters]]）：
- 产品/管理岗中「**搬信息**」的部分交给 agent → 组织**变平又变宽**，价值转向 **judgment / building**。
- 大厂今年 **30–70% 裁员**却又**薪资飙升、大规模招聘**并存——被裁的是 ZIRP 超招的「information mover」，稀缺的是「有 judgment 的 product builder」（top 1% 产品人薪资 18 个月翻倍）。
- 最受冲击的是 **8–15 年、只会搬信息的中层经理**；学生与 hands-on builder 反而最占位。这与 [[tasks-vs-jobs]] 的 Dario/Jensen 之争是同一分布的两端。

## 营销层：神经营销崛起

Meta 开源 Tribe V2 改变一切。
- 720 人 × 数千小时 MRI 训练的脑反应模型
- 任何人现在可以在广告上线前看到大脑反应
- 学术神经营销研究通常 30-50 人（成本数百万美元）→ Meta 免费发布 720 人数据

详见 [[neuromarketing]]、[[attention-economy]]。

来源: [[neuromarketing-tribe-v2]]

## 生产力层：知识管理革命

LLM 改变了个人知识管理方式：

- [[llm-wiki-pattern]] 让"第二大脑"维护成本趋近于零
- 人类负责策展和提问，LLM 负责所有 bookkeeping
- 打破了个人知识库"建了又废"的死循环
- AI 作为最有耐心的导师（[[ai-for-learning]]）

来源: [[claude-obsidian-second-brain]], [[a-motorcycle-for-the-mind]]

## Context 与 Sovereign AI

进展最快的领域 = 可验证的领域（[[context-feedback-loops]]）。

主权 AI 打破 15 年的云集中（[[sovereign-ai]]）。

## 苏煜视角：软件末日论只对了一半

[[yu-su|苏煜]]（2026-05）承认软件利润率在被压缩，估值逻辑变了。他不相信 agent 会重写或替代所有软件。变化在卖的东西：软件从前卖工具，买家现在要结果、劳动力、AI employee。软件公司若想活，是从 tool 转成在自己平台上交付结果的 labor market。AI-native、模型公司和老软件公司谁赢，他说 2026 年才刚开始，说不准。

就业上，他不把近期风险写成奇点。缺的是原生目标和生存压力。真正担心的是知识工作被替换的速度快过新岗位和再分配，而收益集中在少数公司和资本。研究者能做的一份是把专家级 agent 的门槛降到个人能用自己的洞察变现。数字和判断均为口述。见 [[yu-su-xiaojun-agent-history]]。

## 嘉宾视角：AI 进入半导体制造链本身（2026-10-27）

本页的硬件层讨论的是芯片需求侧（存储超级周期）；[[haozhe-wang|Harry Wang]]（硅谷101 Alignment 2026）补上**供给侧**的变革：AI 正从三步进入制造链——看（[[atomic-microscopy|ATOMIC]] 表征材料，99.7% 准确率）、做（Co-Scientist 接实验设备生成配方）、造（在良率 65.6% 的缺陷材料上造芯、良率 +30pct）。叠加材料代际切换（[[2d-semiconductor]]），半导体的生产函数本身正在被 AI 改写。

## 嘉宾视角：游戏产业的“古法手工溢价”——越是 AI 时代，人类心血越像爱马仕贴牌（梁其伟，2026-11-13）

[[s-game-phantom-blade-zero|灵游坊]]创始人[[liang-qiwei|梁其伟]]在《影之刃零》发售前夕，对生成式 AI 如何重塑文化娱乐与买断制游戏产业给出了“工程拥抱、艺术死守手工”的鲜明判断：
- **工程环节提效 vs. 艺术环节零 AI**：灵游坊在代码逻辑、QA 测试、性能优化中积极使用 AI；但在《影之刃零》的美术与核心艺术创作中坚持 100% 纯手工、零 AI 生成。原因不在于 AI 画得不好，而在于消费者对 AI 生成物的心理定价截然不同——一旦玩家发现买断制游戏或抽卡立绘是 AI“大风刮来的”，价值体系会瞬间崩塌。
- **买断制游戏卖的是一半体验 + 一半“人类工作量溢价”**：不同于只看实用功能的喝水杯子，买断制单机玩家花数百元购买的不仅是游玩体验，更是背后数百名人类创作者耗费数年光阴、烧掉数亿资金的“心血证明”，以及对工作室未来续作的“品牌养成投票”。正如工业流水线没有消灭爱马仕手工缝制铭牌的十倍溢价，数码时代没有消灭诺兰《奥德赛》坚持 IMAX 胶片或 R 星耗资 10 亿美元人工打磨《GTA6》的定价权，**越到 AI 海量低成本生产时代，“古法手工打造”反而越会成为金字塔尖最稀缺的品牌护城河**。
- **一人 AI 游戏团队的品牌化前提**：对于 AI 取代初级岗位导致新人断层的担忧，他认为未来会出现“一人 AI 游戏团队”或知名度堪比张艺谋的“AI 短剧/游戏导演”——只有当大众明确将体验归功于背后那个人的独特审美与灵魂（如个人 IP 结合虚拟形象日常直播），AI 原生作品才会真正建立起商业品牌溢价。见 [[wuxia-punk-and-craft-premium]]。

## 相关页面
- [[compute-infrastructure]]
- [[vibe-coding]]
- [[neuromarketing]]
- [[attention-economy]]
- [[context-feedback-loops]]
- [[sovereign-ai]]
- [[llm-wiki-pattern]]
- [[ai-for-learning]]
- [[yu-su-xiaojun-agent-history]] — 张小珺 #139 苏煜（2026-05-01，本地 ASR，未校对）
- [[harry-wang-beyond-silicon-chips]] — 硅谷101 Alignment 2026 Keynote：Harry Wang 谈超越硅的下一代芯片与自生成智能（2026-10-27）
- [[liang-qiwei-phantom-blade-zero-xiaojun]] — 《张小珺商业访谈录》#156 对话《影之刃零》制作人梁其伟（2026-11-13）
