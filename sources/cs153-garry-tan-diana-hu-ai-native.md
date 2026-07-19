---
title: "Stanford CS153 | Garry Tan & Diana Hu on The AI Native Company"
author: "Garry Tan, Diana Hu"
date_ingested: 2026-07-19
date_published: 2026-06
tags: [ai-native, startups, y-combinator, agents, coding-agents, evals]
url: "https://www.youtube.com/watch?v=Lri2LNYtERM"
---

# Stanford CS153 | Garry Tan & Diana Hu on The AI Native Company

Stanford **CS153 Frontier Systems**（2026 春）系列讲座（playlist #5），嘉宾为 [[garry-tan|Garry Tan]]（[[y-combinator|Y Combinator]] 总裁 / CEO）与 [[diana-hu|Diana Hu]]（YC General Partner），主持人为课程讲师 [[anjney-midha|Anjney Midha]]。属于 [[cs153-frontier-systems]] 系列，落在 [[frontier-systems]] 框架的 **Capital** 层——但真正的主题是：**当"生产单元（unit of production）"被 AI 改写，一个人如何成为 1000x engineer，一家公司如何变成 AI-native。**

主标题里的 "1000x engineer" 不是修辞：Garry 引用 Steve Yegge 的说法——用 coding agent 的工程师比在 Cursor 里聊天的人 10–100x 高效，而在 [[anthropic|Anthropic]] 内部约是 2005 年 Googler 的 **1000x**。整场讲座分两半：Garry 讲 **code 层**的 agentic 工程原语（[[agentic-engineering-primitives]]），Diana 讲 **org 层**的 AI-native 组织（[[ai-native-company]]）。

## 主持人开场：从 The SAFE 到"未来算力协议"

[[anjney-midha|Anjney]] 把本讲和第 1 讲（compute 瓶颈）连成一条线：**capital 和 compute、energy 一样是前沿进步的瓶颈**，而瓶颈往往靠"标准化"解开。

- 工业革命里，电力成为可开发的基础设施，靠的是 **AC/DC 标准** + 电力公司（utility）这类**执行标准的机构**建电网协调供需。
- 2011 年 Garry 初到硅谷时，VC 还处在**前标准化时代**——一团乱麻。[[paul-graham|Paul Graham]] 与 Jessica Livingston 拿出 **The SAFE**（Simple Agreement for Future Equity）——"一份两页的法律文书"，标准化了种子轮融资，YC 由此成为**制定并执行标准的机构**。"没有那一份文档，硅谷的走向会完全不同。"（见 [[venture-capital-systems]]、对照 [[ben-horowitz]] 那一讲的 VC 系统再设计。）
- Anjney 透露 AMP 未来可能开源 **"a standard agreement for future compute"**（未来算力协议），把 [[compute-infrastructure|compute]] 也标准化。
- Garry 接棒："The SAFE 是**法律工具**；今天我们要讲的是 **code**——而且 **Markdown 也是 code**。你们这一代要为整个社会建造的，是 **the cognitive layer（认知层）**。"

## 核心论点

### 生产单元正在被改写

- **Posterous 重建实验**：Garry 2008 年做的博客平台 Posterous，当年用了 **10 人 + $4M + 2 年**，3 年后以 **$20M** 卖给 Twitter。而现在他一个人靠 **$200/月的 [[claude-code|Claude Code]] Max plan**，**约 5 天**就重建了同样的软件。"这屋里任何人都能做到。"
- **新的经济密度**：2026 年一个 **6 人团队可做到 $10M 收入**；YC portfolio 里的公司**一年内 0 → 数千万美元收入**（过去这需要 4–5 年、上亿美元资本才到 Series B）。**一个员工 = $1–2M 收入**——对比 Salesforce 员工人均收入不到六位数，**至少 10x**（详见 [[ai-native-company]]、[[agentic-micro-company]]）。

### GStack：一座"软件工厂"，不是 AI slop

- Garry 从"不写代码"（去年 12 月）起步，如今 **GStack 87,000+ GitHub stars、GBrain 13,000 stars**，合计 10 万+ stars、约 **15,000 人每日使用**、数十万次 skill 调用。
- **驳"AI slop"**：LLM 确实啰嗦、爱写 boilerplate、会 hallucinate——但这正是**软件工厂要对抗的默认状态**，不是终点。靠 **plan-review skill**（每天用约 **20 次**）把 **test coverage 拉到 80–90%** → 进 production，不是 slop。
- **LOC 是垃圾指标**：真正的指标是"它对客户管不管用、有没有人付钱"。"harness / model / GStack 里没有任何东西叫模型多写代码——如果有，方向是反的：写得越密越简越好。"
- **Boil the ocean（把海煮沸）**：一个人坐在 terminal 前 ≈ **500–1000 人**的产出；模型自己给的工期估计（"要 3 周"）**错了 1000x**——按下 approve，**一小时就完成**。模型权重还没跟上这个新现实。
- **从 latent space 里拉出 persona**：**office hours skill** 蒸馏了 YC 3–4 个月、数千场 office hour 的 transcript，再**压缩 90%**开源；**plan-ceo-review** 问的是"**10x 版本 / platonic ideal（柏拉图式理想版）**是什么"。

## Agentic 工程原语

（完整概念页见 [[agentic-engineering-primitives]]。这些是 Garry 通过 **OpenClaw / [[hermes-agent|Hermes agent]] 一周一周学到**的 code 层原语。）

- **Skill = 会调用 code 的 runbook**：一个 markdown 文件，像"办活动的手册"，任何人/agent 读完 1–2–3 步就知道怎么做。**大转变**是——现在能用 markdown + LLM 做**真实工作**。关键纪律：**分开 deterministic work（该是 code）与 latent work（该交给 LLM）**——每个崩掉的 agentic 系统都是把两者混淆了。例子：**8 人晚宴排座** latent space 能搞定，**800 人 / Startup School 6000 人**就 hallucinate → 必须用 code（如 `context-now.mjs`，防止 OpenClaw 老以为你在英国 Greenwich）。
- **Resolver = 治 bloated CLAUDE.md 的解药**：与其把所有指令塞进 context（触发 "40,000 tokens" 警告），不如做一个 **master directory**，**按需 lazily load** 指令（"写 changelog 时才加载 changelog.md"）。类比：**resolver ≈ org chart（组织架构图）**——谁负责什么。
- **Skillify = 升一层抽象**：先手动把一件事做对一次（如"保存这篇文章"），然后说 **"skillify"** → agent 自动产出 **skill + code + unit tests + LLM evals + integration test + resolver trigger（agents.md）+ trigger eval（LLM-as-judge）+ check-resolvable（DRY 去重）+ smoke test + schema/memory 存放位置**。**~10 步里只有 2 步是写 skill/code**，其余全是"像人类系统一样"的 compliance/audit 脏活。
- **GBrain = 三层记忆系统，长在 Karpathy 的 Knowledge Wiki 之上**：起点就是 [[andrej-karpathy|Karpathy]] 的 **[[llm-wiki-pattern|LLM Wiki]]**（只有 grep）→ "fell over" → 加了 **vector search、RRF fusion、backlinks、graph database（typed knowledge graph）**，再加 **epistemology layer**（区分 hunch / 某人的 belief / world knowledge，并追踪"某人的 contrarian hunch 后来被证明对了"）。下一步：**dynamic ontology**（每个用户一套 schema——researcher / journalist / politician）。（见 [[company-brain]]、[[ai-agent-memory]]。）
- **组织同构（the org isomorphism）**：Garry 发现这些原语**一一映射到公司**——skill ↔ 有某项能力的**员工**；resolver ↔ **org chart**；filing rules / memory ↔ **内部流程**；check-resolvable ↔ **audit & compliance**；trigger eval ↔ **绩效评估（performance reviews）**。"人类系统很乱——我 45 岁、建了大量 agentic 系统后，才终于理解企业为什么要花那么多人做审计合规。"

## AI-native 组织

（完整概念页见 [[ai-native-company]]。这半场由 [[diana-hu|Diana Hu]] 主讲。）

- **Closed-loop vs open-loop company（控制系统视角）**：旧公司是 **open loop**——信息散落在人脑、Slack DM、没写下来的会议记录、"vibes" 里，**误差累积 → 脱轨**。AI 把公司变成 **closed loop**（类比 PID controller）：一个 agent（Hermes / OpenClaw）**对公司产出的每一个 artifact 有 read access** → 主动建议下一步、bug fix、self-heal。**YC 自己的工程团队：sprint 时间砍半、产出 10x。**
- **三种角色**：① **人人都是会 ship 的 IC**（连非技术岗也是——销售自己搭 pipeline）；② **DRI（Directly Responsible Individual，源自 Apple）** 编排 IC 达成一个 outcome（常是 founder，如"本周把收入做到 3x"）；③ 全新的 **AI founder**——活在未来的边缘、试遍每一个新工具、把创新带回公司（[[garry-tan|Garry]] 即化身）。呼应 **Jack Dorsey 的"agentic organization"** 与更扁平、**更少中层管理**（"lossy information routing"）——与 [[nikhyl-singhal|Nikhyl Singhal]] 的中层被挤压论一致（见 [[tasks-vs-jobs]]、[[product-management-ai-era]]）。
- **Taste 与 evals 不可外包**："**shipping code 的成本归零，taste 不会归零**。"通用 benchmark（MMLU）不告诉你产品好不好用——需要 **human-in-the-loop、亲自读 traces、标注失败、转成 evals、replay 回去 self-heal**。Garry 预告 **cross-modal eval**：**Opus + GPT-5.5 + DeepSeek V4** 互评彼此的 I/O 再反馈迭代。YC 创始人金句："Claude Code 是我的 ADHD CEO，Codex 是我近乎不说话的 200-IQ CTO——两个都要，做 cross-modal analysis，**ships zero bugs**。"
- **Go-to-market wedge**：选一个**痛的 workflow**，作为 **forward-deployed engineer** 扎进客户里，"go undercover"——**去把那份工作干一遍**学会 domain。案例（全部一年内 0 → 八位数收入）：**Salient**（贷款服务的 voice agent，拿下美国顶级银行）、**HappyRobot**（货运 freight，去年拿 Series B、收入 10x）、**Reducto**（文档处理）。引用 **Anthropic economic-index 图**：软件 / CS 已 ~50% 渗透，但 back-office / finance / data / 学术 / cybersecurity / 客服是巨大 whitespace → "**hundreds of AI unicorns waiting**"。
- **增长统计**：过去只有 top 1% 公司做到 PG 定的 "10% week-over-week"（Airbnb 那种）；YC 上一批**平均公司 3 个月 3x**——史无前例。"现在是历史上创业的最佳时机，我们在这场革命的第一局第一个投球。"

## 自指彩蛋

Garry 的 **GBrain 字面上扩展了 Karpathy 的 [[llm-wiki-pattern|LLM Wiki]]**——也就是**本 vault 正在运行的同一套模式**（raw / wiki / schema 三层 + ingest / query / lint）。区别在于 GBrain 在其上加了 vector search / graph DB / epistemology；本 vault 目前仍是 grep + wikilinks 的轻量版。这是一个恰好落回自身的 delightful 链接。

## 金句

> "The SAFE was a legal instrument. What we're going to talk about today is actually code. And not just code — Markdown is code."

> "Your generation is going to create the cognitive layer for all of society."

> "I created all that software with 10 people over two years — me with the $200/month Claude Code Max plan did it in about five days."

> "Let's boil the ocean. You sitting in front of one of these terminals can do the work of about 500 to 1,000 people."

> "There's nothing in Claude Code or the model or the harness that tells the model to write as many lines of code as possible. If anything, the reverse is true."

> "Writing the skill and writing the code is only 2 out of the 10 steps."

> "A skill is a squishy human being who's an employee with a capability. A resolver is the org chart. Check-resolvable is audit and compliance. A trigger eval is a performance review."

> "Shipping code is going to zero. The taste to build something good is not going to zero."

> "Claude Code is my ADHD CEO, and Codex is my nearly non-verbal 200-IQ CTO — I need both for cross-modal analysis, and it ships with zero bugs."

> "We're at the first pitch of the first inning of the revolution, and you guys are the shock troops."

> "This whole lecture was about how that one-person frontier lab can become a one-person company — and that could be you."

## 关联页面

- [[garry-tan]] — 人物页（YC 总裁 / CEO）
- [[diana-hu]] — 人物页（YC General Partner）
- [[y-combinator]] — 机构页
- [[agentic-engineering-primitives]] — **本讲新建**：code 层原语（skill / resolver / skillify / GBrain、latent-vs-deterministic、org 同构）
- [[ai-native-company]] — **本讲新建**：org 层（closed-loop、DRI/IC/AI-founder、taste & evals、GTM wedge、增长统计）
- 系列同源：[[frontier-systems]] · [[cs153-frontier-systems]] · [[anjney-midha]]
- 相关：[[claude-code]] · [[llm-wiki-pattern]] · [[andrej-karpathy]] · [[hermes-agent]] · [[company-brain]] · [[agentic-micro-company]] · [[venture-capital-systems]] · [[ben-horowitz]] · [[nikhyl-singhal]] · [[tasks-vs-jobs]] · [[compute-infrastructure]] · [[anthropic]] · [[sam-altman]]

## References

- Stanford Online / CS153 Frontier Systems, YouTube: https://www.youtube.com/watch?v=Lri2LNYtERM
- Raw transcript: `raw/Stanford CS153 Frontier Systems  The AI Native Company How One Founder Becomes a 1000x Engineer.md`
