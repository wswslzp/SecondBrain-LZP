---
title: "Anthropic"
tags: [anthropic, ai, ai-safety, frontier-lab, company, enterprise]
date_created: 2026-07-19
date_modified: 2026-10-25
related: ["[[dario-amodei]]", "[[daniela-amodei]]", "[[claude-code]]", "[[claude-constitution]]", "[[scaling-laws]]", "[[tasks-vs-jobs]]", "[[ai-impact-on-industry]]", "[[dhh]]", "[[dhh-lex-fridman]]"]
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

- **Boris Cherny** — [[claude-code|Claude Code]] 与 Claude Cowork 背后的工程师，2024 年从日本乡村（做 miso、慢生活）被招入。他的赌注：coding agent「can do all of it」，而非只是自动补全一行代码。
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
