---
title: "OpenClaw"
tags: [ai-agents, openclaw, personal-ai, open-source, agentic-engineering, china]
date_created: 2026-07-21
date_modified: 2026-10-25
related: ["[[openclaw-foundation]]", "[[vincent-koc]]", "[[gateway-architecture]]", "[[hermes-agent]]", "[[claude-code]]", "[[microsoft]]", "[[agentic-engineering-primitives]]", "[[dhh]]", "[[dhh-lex-fridman]]"]
---

# OpenClaw

**OpenClaw** 是 2026 年初引爆全球 AI 圈的现象级**个人 AI agent**——由 **Peter Steinberger** 出于「个人 AI 的承诺一直没兑现」的挫败感自己动手做起，社区随之成形，最终交由 **[[openclaw-foundation|OpenClaw 基金会]]** 托管。它此前在本 vault 里被十几处提及却无独立页；本页由 [[silicon-valley-101-vincent-koc-openclaw|硅谷101 对话首席架构师 Vincent Koc]] 建立为中心实体。

> [[jensen-huang|黄仁勋]]称这类 agentic coding 为「OpenClaw」，把它叫作 **the iPhone of tokens**、史上增长最快的应用之一（见 [[claude-code]]）。

## 与 coding agent 的根本区别：**能改自己的代码**

| | Coding agent | OpenClaw |
|---|---|---|
| 形态 | 被 harness 锁死，只**生成**代码 | **个人 agent**，替你**做事** |
| 记忆 | 弱/无 | 持久记忆 + 自建 **skills** |
| 自我修改 | ✗（harness 是天花板） | ✅ **agent 能修改自身代码** |
| 运行模式 | turn-based / 线程 | **always-on** 服务 + heartbeat（见 [[gateway-architecture]]）|

代表性例子：某 lab 发布新模型、OpenClaw 尚无支持 → 你直接让它「帮我加上这个功能」，它**改自己的代码**完成适配。「The agent can modify itself」是它区别于 coding agent 的分水岭。它也能生成代码去买菜、连消息应用、拿电话号码、浏览网页——「可能性几乎无限，取决于任务」。

## 爆火与「小龙虾」狂热

- **时间线**：Vincent 2025 年 12 月在 X 上注意到（polymarket 交易员在用）；2026 年 2 月 SF 一场活动成峰值——几百人 guest list、**5 点到都算晚、队伍绕楼一圈**。
- **中国比硅谷更疯**：深圳腾讯楼下的阿姨、Twitter 说唱歌手都在用；**Apple Mac / Mac Mini 一度断货**；全球出现**龙虾（lobster）主题装机活动**。项目吉祥物就是一只小龙虾，Vincent 的头衔梗是「minister of lobster affairs」。
- **中国为什么火**（心态 × 可得性）：
  - 心态——中国「能赋能我就快速拥抱、边试边学」，西方先「太吓人了，block 起来」（重演 2023–24 ChatGPT 进企业被封的剧本）。有企业给员工下 **KPI：用 OpenClaw 自动化 N 件事**；换别的市场装了反而算安全事故。
  - 可得性——Codex / Claude Code（他戏称 "uncle code"）在中国市场用不了，**开源可得成了关键催化剂**。
  - 对基金会而言，中国是「下一步会发生什么的窗口」——采用最快、大量企业全员在用、团队里也有常驻中国的 maintainer。

## 「后 Claw 时代」：降温 = 假摔

炒作退潮**同时**发生两件事：(1) 疯狂降温（是好事）；(2) 他们**确实搞砸过**——想让 agent 当主力高速造软件，学到「how **NOT** to build software with agents」，因不稳定流失大量用户。约两个月前修复后：

> 炒作前 npm ~**2.5–3M/周**；几周前冲到 **4M+/周**——**比任何时候都高**（还不含中国镜像站）。

Vincent 称其为 **postclaw era**：OpenClaw 引爆了下一代 agentic framework 与 model labs / token 用量的爆发。

## 大厂造 Claw

腾讯 **Qclaw**、火山引擎 **art claw**、阿里 **Dclaw**、**[[microsoft|微软 Scout]]**（美国版 OpenClaw）、腾讯 **workbody**（不基于 OpenClaw 但**完全兼容其 skills/framework**）。很多没做成（Vincent 未细究，猜是功能或成本）。OpenClaw 的立场：**赋能生态**——别人在其上造、把 agent 送到用户手里，对基金会就是好结果；自己**不想做基础设施/托管服务器**（会偏离「把软件做到很好」的本分）。大厂合作按 case-by-case，但追求「一套适配大多数人的方案」。

## 架构要点（详见 [[gateway-architecture]]）

- **Gateway** = 中枢神经：连接消息通道、模型、记忆、工具；**always-on** + **heartbeat**（每 10–30 分钟触发对话链，替你在后台干活/跑定时任务）。
- **存储重构**：会话从「一切写文件」改为写进**数据库**（放在一个小文件里）→ 企业可换成数据库系统、做备份，更易规模化部署与二次开发。
- **安全边界**：凭证入 vault（非明文）；主推容器化 + OS 级原生隔离；**auto mode** 让 LLM 按意图判断安全再请求批准（可用前沿模型审查 + 本地模型推理的 hybrid）。
- **模型 × harness**：表现是二者组合；部分中国开源模型在 OpenClaw 上 **post-train** 后更好用；正做 **~100–120 任务的公开 benchmark**；承诺模型公平（zero-day、不偏袒、feature parity）。

## 反复出现的判断

- **多智能体瓶颈是 context 而非成本/延迟**：9/10 单 agent 足够，只在有独立 system prompt 的可重复任务时才「切」出专门 agent；心法是「管理一个员工、拆分工作量」。
- **记忆远未解决**：换模型后旧记忆能否被理解、团队**多租户**共享哪些记忆——是当前最难的问题空间之一。
- **康威定律**（见 [[conways-law-agents]]）：别把旧组织架构镜像进 agent，要白纸重来 agent-first。
- **Aha 时刻未到**：卡在成本、可靠性、模型，以及**外部服务（银行等）是否允许 agent 交易**；最大 unlock 是 **computer use 模型**（经许可接管浏览器点击）。
- **企业↔个人飞轮**：消费者采用 → 带进企业 → 企业采用使产品在规模下更可靠 → 反哺消费者。
- **下一步预测**：**agent 间通信协作**是下一个爆点（像手机——人人不同但能互打），比安全更复杂。

## 与 vault 的关联

- [[claude-code]] — Jensen 的「OpenClaw = the iPhone of tokens」；coding agent 正逐渐「变成 OpenClaw」。
- [[microsoft]] — Scout = enterprise OpenClaw（heartbeat + dreaming），MXC 容器与 OpenClaw 基金会合作。
- [[agentic-engineering-primitives]] / [[garry-tan]] — Garry Tan 从 OpenClaw / [[hermes-agent|Hermes]] 逐周学到 skill/resolver/skillify；「工厂」隐喻同构。
- [[ai-memory-open-source-landscape]] — 第四代记忆项目 **MemClaw / SkillClaw** 即建在 OpenClaw 上。
- [[hermes-agent]] — 同为个人 agent 的另一条产品路线。

## 外部用户案例：DHH 的 web-only bot（Lex #501）

- **实验**：2026 年 2 月，[[dhh|DHH]] 用 OpenClaw 做了一个 bot（字幕记作 KEF）。他觉得 MCP 对接 Web 系统太繁琐，于是让智能体直接用网页界面：自己去 HEY 注册邮箱、注册 Fizzy、通过邮件接受 Basecamp 邀请，再到 AI 频道里自我介绍，全程约 12 分钟。他说这是“未来的一瞥”，但当时太慢、太费 token，实际使用仍离不开 CLI 和 MCP（[[dhh-lex-fridman|DHH × Lex #501]]）。
- **之后的选择**：他回到用 Claude 手机 App 遥控 Claude Code，原因之一是妻子不希望家里出现“会自己开关灯的鬼”。他转述了一个案例：有人把智能体接入健康数据和特斯拉，智能体为了让主人多喝水，擅自让车改道去超市。
- **Lex 的看法**：OpenClaw 和 [[hermes-agent]] 这类通过 IM 交流、自带记忆系统的智能体，值得体验一下这种不同的交互方式。

## References

- [[silicon-valley-101-vincent-koc-openclaw]] — 硅谷101 对话 Vincent Koc（WAIC 2026）
- [[dhh-lex-fridman]] — Lex Fridman #501 DHH 访谈（2026-08-26）
