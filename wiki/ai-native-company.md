---
title: "AI-native 公司"
tags: [ai-native, startups, org-design, evals, go-to-market, y-combinator]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[agentic-engineering-primitives]]", "[[diana-hu]]", "[[garry-tan]]", "[[y-combinator]]", "[[product-management-ai-era]]", "[[nikhyl-singhal]]"]
---

# AI-native 公司

**组织层（org level）** 的论点：当 shipping code 的成本归零、一人能干 500–1000 人的活（见 [[agentic-engineering-primitives]] 的 code 层原语），公司的**运行方式本身**必须重写。主要来自 [[diana-hu|Diana Hu]] 在 [[cs153-garry-tan-diana-hu-ai-native|CS153 讲座]]的下半场，与 [[garry-tan|Garry Tan]] 的 code 层内容互为镜像。

> 一句话对照：[[agentic-engineering-primitives]] = **code 层**（怎么造 agent）；本页 = **org 层**（怎么把公司变成 agent 增强的组织）。

## 从 open loop 到 closed loop（控制系统视角）

[[diana-hu|Diana]] 用 **control systems** 给公司建模：

- **旧公司 = open loop**：信息散落在人脑、Slack DM、没写下来的会议记录、"vibes" 里，反馈稀疏且 lossy → **误差累积 → 系统脱轨**。
- **AI-native 公司 = closed loop**（类比 **PID controller**）：一个 agent（[[hermes-agent|Hermes]] / OpenClaw）**对公司产出的每一个 artifact 有 read access** → 主动建议下一步 work item、bug fix，并把结果写回 [[company-brain|GBrain]] memory → **self-heal**。误差被持续拉回。
- 学生版最小实现：agent 接上 GitHub codebase + Discord + 录下所有 team 会议 → 让它建议下一步。
- **YC 自证**：把这套接进自己工程团队后，**sprint 时间砍半、产出 10x**。

## 经济密度：一员工 = $1–2M 收入

- YC portfolio：**一年 0 → 数千万美元收入**（过去 4–5 年才到 Series B）。
- **人均收入 $1–2M** vs Salesforce 员工人均不到六位数 → **至少 10x**（见 [[agentic-micro-company]]）。

## 三种角色

| 角色 | 定义 | 备注 |
|------|------|------|
| **IC who ships** | 人人都是会交付的 individual contributor | 连非技术岗也是——**销售自己搭 pipeline**、自动化 call/meeting |
| **DRI** | Directly Responsible Individual（Apple 术语），编排 IC 达成一个 outcome | 常是 **founder**；例："本周把收入做到 3x" |
| **AI founder** | 活在未来边缘、试遍每个新工具、把创新带回公司 | [[garry-tan|Garry]] 即化身；"还在 Copilot 水平的人，not gonna make it" |

- 引 **Jack Dorsey 的 "agentic organization"**：组织更**扁平**、**更少中层管理**（中层过去主要做"lossy information routing"）。
- 与 [[nikhyl-singhal|Nikhyl Singhal]] 的"中层被挤压"论一致；参见 [[tasks-vs-jobs]]、[[product-management-ai-era]]。

## Taste 与 evals：唯一不可外包的东西

- **"shipping code 归零，taste 不归零。"** 判断好坏、辨别方向的品味无法自动化。
- 通用 benchmark（**MMLU** 等）**不告诉你产品好不好用**。真正的裁判是"用户到底想不想要"，且**每个 domain 都不同**。
- **eval 三步闭环**：
  1. **捕获 traces**（高度依赖产品形态：video / speech / consumer / B2B SaaS 各异）；
  2. **human-in-the-loop** 亲自读 trace，标注失败（是否守指令、答案对不对、有没有守住 customer trust、达没达业务目标、合不合 domain rules）→ 转成 **evals**；
  3. **replay** 回系统 → self-heal、自动改 prompt。
- **cross-modal eval**（[[garry-tan|Garry]] 预告）：**Opus + GPT-5.5 + DeepSeek V4** 互评彼此 I/O，评分反馈给原 subagent 迭代 → meta-prompt 出比第一版好 10x 的结果。YC 创始人金句："Claude Code 是我的 ADHD CEO，Codex 是我近乎不说话的 200-IQ CTO——两个都要做 cross-modal analysis，**ships zero bugs**。"

## Go-to-market：forward-deployed wedge

- 选一个**痛的 workflow**，作为 **forward-deployed engineer** 扎进客户，**"go undercover"**——**真的去把那份工作干一遍**学会 domain（创始人往往没有该行业背景，"not in the training set"）。
- 不是"demo AI 或做 side project"，而是**交付 full solution**替换掉 phone / email / spreadsheet 的乱摊子。
- 案例（全部一年 0 → 八位数收入）：
  - **Salient** — 贷款服务 voice agent，拿下美国顶级银行；
  - **HappyRobot** — 货运 freight，去年 Series B、收入 10x；
  - **Reducto** — 文档处理（做好文档解析会让所有下游 agent 的 RAG / memory 更好）。
- **Anthropic economic-index 图**：软件 / CS 已 ~50% 渗透，但 back-office / finance / data / 学术 / cybersecurity / 客服是**巨大 whitespace** → "**hundreds of AI unicorns waiting**"。

## 增长统计与时机

- YC 上一批**平均公司 3 个月 3x**；对比 PG 旧标尺"只有 top 1% 达 10%/周"（Airbnb 那种）——**史无前例**。
- "现在是历史上创业最佳时机，我们在革命的第一局第一个投球，你们是 shock troops。"
- 收尾："one-person frontier lab 可以变成 one-person company——那可以是你。"

## References

- [[cs153-garry-tan-diana-hu-ai-native]] — 讲座源页
- [[agentic-engineering-primitives]] — 配套的 code 层原语
