---
title: "Anthropic"
tags: [anthropic, ai, ai-safety, frontier-lab, company, enterprise]
date_created: 2026-07-19
date_modified: 2026-10-29
related: ["[[dario-amodei]]", "[[daniela-amodei]]", "[[claude-code]]", "[[claude-constitution]]", "[[scaling-laws]]", "[[tasks-vs-jobs]]", "[[ai-impact-on-industry]]", "[[dhh]]", "[[dhh-lex-fridman]]", "[[addy-osmani]]", "[[agentic-code-review]]", "[[claude-code-team-code-review]]", "[[vitalik-buterin]]", "[[effective-altruism]]", "[[d-acc]]", "[[silicon-valley-101-vitalik-ea-ai-safety]]", "[[gpt-6-astra]]", "[[huazhe-xu]]", "[[zheqing-zhu]]", "[[sheng-wang]]", "[[wet-lab-verification-loop]]", "[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]"]
---

# Anthropic

估值近 **$965B** 的前沿 AI 实验室。2021 年由 7 位前 OpenAI 成员创立，其中兄妹 [[dario-amodei]]（visionary/CEO）与 [[daniela-amodei]]（operator/President）是两位。是业内**唯一 co-founder 全部留任**的公司。

> "we're basically the only company in the space that has all of its co-founders still here... You don't get to be a company of the size and scale that we are with that happening. Like that almost never happens." — Dario

## 使命

Anthropic = 希腊语「人」，指向使命：为人类长期利益构建 **responsible AI**。

> "All of this technical safety research that we do, it's to make the products more aligned with human values, to make sure that we're not building something that could cause societal issues that previous technology companies have accidentally caused." — Daniela

## 产品

| 产品 | 定位 |
|------|------|
| **Claude** | chatbot，训练遵循 [[claude-constitution|Constitution]] |
| **Claude Code** | 自动化大部分软件工程（见 [[claude-code]]） |
| **Claude Cowork** | 把 Claude Code 的能力交给所有人（不止工程师） |

今年**首次盈利**，主要归功于押注更赚钱的企业工具，而非 splashy consumer app。

### 为什么押注 enterprise 而非 consumer

> "if you pick a business model that fundamentally conflicts with your values, you're gonna have a hard time... Either you betray your own values or you become irrelevant." — Dario

Dario 认为 consumer/social media/AI video 的商业模式鼓励 engagement 甚至 addiction（广告收入驱动最大化注意力时长）；而 enterprise（biotech、pharma、学术研究、能源）与「用 AI 治病、让能源更便宜」的价值观对齐。参见 [[ai-impact-on-industry]]。

## 增长曲线

- API 用量同比近 **17×**
- 过去 12 个月发 **8 个 frontier model**
- 今年 Q1 年化增速约 **80×**
- 「第一年增速**超过 exponential**」（first year we've grown faster than the exponential）
- 底层现象学是 Dario 的 **smooth exponential**（见 [[scaling-laws]]）

## SaaSpocalypse

Claude Cowork 发布后，软件板块**一夜蒸发 $285B 市值**，交易员称之为「白领 wipeout」（white collar wipeout）；部分软件股连跌九日。

> "$285 billion in market value vanished overnight. Traders called it the SaaSpocalypse."

Dario 的解读：AI 让「pie 变大」，软件产业整体不会缩小，但会有「big losers」——那些看不清趋势、认不清自己护城河（moat）的公司会很难。参见 [[tasks-vs-jobs]]、[[ai-impact-on-industry]]。

## 关键人物

- **Boris Cherny** — [[claude-code|Claude Code]] 与 Claude Cowork 背后的工程师，2024 年从日本乡村（做 miso、慢生活）被招入。他的赌注：coding agent「can do all of it」，而非只是自动补全一行代码；并提出为 Claude 配备可运行的验证流程可将产出质量提升 2–3 倍（见 [[agentic-code-review]]）。
- [[addy-osmani]] — Claude Code 团队成员，公开阐述了 Anthropic 内部应对日均 30,000+ monorepo 变更与 90% AI 编写代码的六层审查体系（[[claude-code-team-code-review]]）。
- [[dario-amodei]] — 兄长、visionary/CEO。
- [[daniela-amodei]] — 妹妹、operator/President。

## 安全定位

- Claude 遵循 [[claude-constitution|Constitution]]。
- Dario 发表长文《**Machines of Loving Grace**》《**The Adolescence of Technology**》，思考 AI 的奇迹潜力与最坏情形。
- 自我定位为 AI 竞赛中的「good guys」。

## 张力

- **与 Pentagon 角力**（head-to-head with the Pentagon）——预告集将深入。
- 模型强到「能击穿现代网络安全的墙」；早期客户称其为 **super weapon**，请求不要发布。
- 下一代模型代号 **Mythos**（预告集）。**市场层面的续集**（见 [[citrini-all-along-the-ai-watchtower|Citrini]]）：**Mythos Preview** 发布后数周揭出数千零日漏洞（27 年 OpenBSD bug、FFmpeg、Squid）；IBM 7/14 转述客户「Mythos 让人停下来问：网络安全要投多少？」。Anthropic 借势组建第三方安全联盟 **[[project-glasswing|Project Glasswing]]**（PANW/CSCO/CRWD/NET → 扩至 Okta/Rubrik/Netskope）——因为没有 CISO 愿把模型与防御押在同一供应商。
- Dario 自比 **Leo Szilard** 而非 Oppenheimer（视 Oppenheimer 为「failure case」），主张「**checks and balances everywhere**」。

## 用户侧批评：模型拒绝与生态锁定（DHH，Lex #501）

- **拒绝翻译**：Claude 拒绝把 [[dhh|DHH]] 一篇关于移民的文章翻成意大利语，理由大意是不认同文章内容。DHH 把这比作 HAL 9000。对照之下，他在美国推理服务上运行的中国开源模型，却能直接回答 1989 年的问题。他的结论是：生物武器之类的护栏是合理的，但用于拒绝翻译文章，就会让所有护栏都显得像扯淡（[[dhh-lex-fridman|DHH × Lex #501]]）。
- **生态锁定**：切断第三方 harness（OpenCode）使用 Claude 订阅；Claude Code 坚持用 `CLAUDE.md` 而不是 `AGENTS.md`。
- **仍然在用**：他认为 Claude 的 harness 和写作能力依然领先，“代码生成器不需要和我政见一致”，多家竞争加上开源模型就是替代方案。
- **政府施压事件**：Lex 担心这会开坏的先例。DHH 认为事情经过仍不清楚，如果公司自称握有足以“抢银行”的网络武器，政府想参与也不奇怪。这和上文提到的 Mythos / [[project-glasswing]] 叙事相关，访谈中的 “Fable” 与 Mythos 是什么关系，目前无法确认。

## 嘉宾视角：招股书投票权黑箱、METR 审计争议与“好公司必须赢”的权力悖论（Vitalik & Afra，2026-10-29）

在《硅谷101》E257 期（[[silicon-valley-101-vitalik-ea-ai-safety]]）中，主持人 Yiwen、科技记者 Afra 与 [[vitalik-buterin|Vitalik Buterin]] 从 [[effective-altruism|有效利他主义（EA）]] 的视角对 Anthropic 进行了深度剖析：

- **招股书中的安全高频词与保密接班人**：主持人口述指出，Anthropic 近期提交的招股书包含近 100 页风险因素（含前沿 AI 威胁人类生存的表述），`safety` 出现 248 次、`AI safety` 出现 36 次。七位联合创始人通过特殊股份掌握一般表决事项 **50.1%** 投票权，“长期利益信托”可选举董事会多数成员；创始人可提前指定自己失能后的投票权接替人选，但**名单对公众保密**。
- **EA 基因与 METR 独立审计争议**：Anthropic 七位创始人因嫌 [[openai|OpenAI]] 不够重视安全而出走，[[dario-amodei|Dario Amodei]]（曾捐助 GiveWell、撰写《Machines of Loving Grace》）、[[daniela-amodei|Daniela Amodei]]（丈夫 Holden Karnofsky 为 GiveWell 与 Open Philanthropy 联创）及 **Chris Olah**（Vitalik 在多伦多微型私立高中 Abelard School 的十一年级学长，也是带 Vitalik 入门 Linux 与开源的启蒙者）均与 EA 渊源深厚（此外，曾作为 EA 头号资助者的 FTX 创始人 **SBF** 在 2021–2022 年也曾挪用客户资金向早期 Anthropic 投资约 5 亿美元，FTX 破产后该笔股权被清算变现十余亿美元用于偿还债权人，详见 [[effective-altruism]]）。2026 年 9 月研究员 Jacob Coxon 辞职警告竞速风险后，评论者 Kevin Bass 质疑为 Anthropic 做独立安全评估的 **METR** 等机构，其核心金主 Coefficient Giving（Dustin Moskovitz）同时持有大量 Anthropic 股份。
- ⚠️ **张力：“好公司必须赢” vs. 加速竞赛与 90% 权力利益重合**：支持 Anthropic 的 EA 派认为“唯有让有原则的好人公司赢下竞赛才能保障安全”。Vitalik 对此提出三点反驳：
  1. **实质加速了 AI Race**：2024–2025 年 OpenAI 一度放慢基座模型步伐去做 Sora 等支线；今年初 Anthropic 发布 **Mythos** 与 **Fable** 展现领跑势头后，倒逼 OpenAI 砍掉支线全力重回前沿大模型竞速——其参战带来的“竞赛加速效应”可能已超过其内部安全研究的正面抵消作用；
  2. **“因为我们是好人所以权力该归我们”**：这套安全哲学与独裁逻辑同构（DeepSeek 有研究者甚至撰文将 Anthropic 垄断比作希特勒级灾难）；
  3. **商业/权力相关性 >90%**：其反开源、推监管的公开主张与扩大自身公司权力的事情相关性高于 90%，而现实中几乎所有最危险的攻击仍是通过闭源的 GPT 和 Claude 完成的。本库将 Anthropic 的自我定位与 Vitalik 的外部批判并列保留。

## 嘉宾视角：21 小时发现 ART 酶、MCP 湿实验闭环与生物护栏拒答困境（硅谷101 E256，2026-10-20）

在《硅谷101》E256 期（[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]）中，主持人泓君、[[zheqing-zhu|朱哲清]] 与华盛顿大学助理教授 [[sheng-wang|王晟]] 补充了 Anthropic 在编码、消费级办公与生物医药领域的最新动态：

- **Opus 4.6 的历史节点 vs. Fable 的高昂成本**（[[zheqing-zhu|朱哲清]]）：Coding 领域真正的范式跃迁发生在 Claude Opus 4.5→4.6（工具调用几乎不再出错，从改几个文件跃升至自主长程编程）；而最新一代 **Fable / Fable 5** 与 [[gpt-6-astra|GPT-6 Astra]] 同属极高价模型，且 Claude Code / Cowork 之所以聚焦白领工作流，正是为了避开消费级 Browser Use 被电商平台封禁 IP 的死胡同。
- **Claude 21 小时发现 ART 酶与自建/外联湿实验室**（[[sheng-wang|王晟]]）：2026 年 9 月底，Claude 仅用 **21 小时**自主发现结构酷似 CRISPR 的新酶系统 **ART**（引发基因编辑股下跌，但生物界仍在等待实验室验证）。Anthropic 已招募 AlphaFold 诺奖得主 **John Jumper（江珀）** 并自建湿实验团队，同时与刚融资 **4000 万美元**的云端湿实验初创 **Adaptyv Bio** 合作——模型通过 **MCP** 协议直接下单启动酶/蛋白质湿实验验证（详见 [[wet-lab-verification-loop]]）。
- ⚠️ **张力：能力越强、科研体验越差的拒答悖论**（[[sheng-wang|王晟]]）：继 [[dhh|DHH]] 批评 Claude 拒绝翻译文章后，王晟从生物科研一线指出，随着 Opus、Fable 与 Astra 能力增强，其生物安全护栏愈发严苛，面对正常生物医学科研任务动辄 **Refuse to answer（拒绝回答）**，迫使实验室日常改用 **Kimi K3** 或 **Muse Spark 1.3**。

## 相关页面

- [[dario-amodei]]
- [[daniela-amodei]]
- [[claude-code]]
- [[claude-constitution]]
- [[scaling-laws]]
- [[tasks-vs-jobs]]
- [[ai-impact-on-industry]]

## References

- [[inside-anthropic-the-circuit]] — Bloomberg「The Circuit」深访（Emily Chang × Dario & Daniela Amodei，2026-06-10）
- [[citrini-all-along-the-ai-watchtower]] — Citrini Research 投研，给出 Mythos / [[project-glasswing]] 的市场层面连锁反应（2026-07-20）
- [[dhh-lex-fridman]] — Lex Fridman #501 DHH 访谈（2026-08-26）
- [[claude-code-team-code-review]] — Addy Osmani：How the Claude Code team does code review（2026-10-26）
- [[silicon-valley-101-vitalik-ea-ai-safety]] — 《硅谷101》E257 对话 Vitalik Buterin 与 Afra：AI安全背后的哲学思想与有效利他主义（2026-10-29）
- [[silicon-valley-101-gpt6-astra-agent-robotics-pharma]] — 《硅谷101》E256 Agent、机器人与制药，谁先被GPT-6 Astra改写？（2026-10-20）
