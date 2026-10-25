---
title: "对话 Vincent Koc：OpenClaw 的反思与进化，中国的「小龙虾」狂热，与 Agent 的下一步"
author: "硅谷101"
date_ingested: 2026-07-21
date_published: 2026-07-21
tags: [ai-agents, openclaw, personal-ai, open-source, foundation, china, agentic-engineering]
url: "https://www.youtube.com/watch?v=tnvyMcmtAiw"
---

# 对话 Vincent Koc：OpenClaw 的反思与进化

硅谷101 在 **WAIC 2026（上海）** 现场对话 **[[vincent-koc|Vincent Koc]]**——[[openclaw-foundation|OpenClaw 基金会]]首席架构师（chief architect，负责 product & engineering）。这是 vault 里第一份系统讲述 **[[openclaw]]** 这个 2026 年初现象级项目的一手素材：它是什么、为什么在中国比硅谷更火、「降温」后为何下载量反创新高、[[gateway-architecture|Gateway 中枢架构]]怎么设计、以及 Agent 的下一步。

## 一句话

OpenClaw 是一个**能修改自己代码**的个人 AI agent；喧嚣退潮后 npm 周下载反而从 ~2.5–3M 冲到 **4M+**；Peter Steinberger 把它交给一个 **501c 基金会**（「AI agent 界的瑞士」），因为「保持开源、不被任何一家公司/国家/实体控制，才是把它公平地送给全世界的唯一方式」。

## 关键takeaways

### 现象与起源
- **爆火线**：Vincent 早在 2025 年 12 月于 X 上注意到它（一批 polymarket 交易员在用），随即贡献代码 → maintainer → 首席架构师。SF 的峰值时刻在 2026 年 2 月一场活动：几百人 guest list，7 点开始，**5 点到都算晚，队伍绕楼一圈**。
- **中国比硅谷更疯**：深圳腾讯楼下的阿姨、Twitter 上的说唱歌手都在用；**Apple Mac（Mac Mini）一度断货**；全球出现龙虾主题装机活动。
- **中国为什么火**：心态差异——中国「这东西能赋能我，拥抱它、快速试」，西方「太吓人了，先 block」（重演 2023–24 ChatGPT 进企业被封的剧本）；有企业给员工下 KPI「用 OpenClaw 自动化 N 件事」；加上 Codex / Claude Code（他戏称 "uncle code"）在中国市场用不了，**开源可得性成了关键催化剂**。

### 它和 coding agent 的根本区别
- coding agent 被 harness「锁死」，只能生成代码；**OpenClaw 能改自己的代码、能给自己加功能**（例：某 lab 发新模型无支持 → 你让它自己改代码适配）。加上**记忆 + 自建 skills + 常驻替你做事**，才是「个人 AI」。「The agent can modify itself」是分水岭。

### 降温 = 假摔
- 炒作退潮是好事；但他们也**真的搞砸过**——想用 agent 高速造软件，学到「how NOT to build software with agents」，因不稳定流失大量用户；约两个月前修复后，**下载量创历史新高（4M+/周，还不含中国镜像站）**。称之为 **postclaw era**：OpenClaw 引爆了下一代 agentic framework 与 token 用量。

### 大厂造 Claw
- 腾讯 Qclaw、火山引擎 art claw、阿里 Dclaw、**微软 Scout**、腾讯 workbody（不基于 OpenClaw 但**完全兼容其 skills/framework**）。很多没做成。OpenClaw 的立场：**赋能生态**，不想自己做基础设施/托管服务器（会偏离「把软件做好」）。

### Gateway 中枢架构（详见 [[gateway-architecture]]）
- **always-on 服务**（对比 coding agent 的 turn-based/线程），像机器上的一个 service；**heartbeat** 每 10–30 分钟触发一次对话链，检查「要不要做点什么」→ 后台替你干活 + 定时任务，这份「类人」感是 OpenClaw 的「magic」。
- Gateway 持有凭证 + 执行动作 = **最大安全边界**：凭证入 vault（非明文）；主推**容器化**，并与产业伙伴做 OS 级原生隔离（agent 只能碰这些文件/这条网络，越界回来问用户）；**auto mode**——不是开/关二选一，而是让 LLM 读对话、按**意图**判断安全与否再请求批准（可用前沿模型做「安全审查」而把推理跑在本地模型上，形成 hybrid）。

### 模型 × harness、记忆、多智能体
- 表现 = **模型 + harness/记忆/工具的组合**；一些模型（尤其中国开源模型）**在 OpenClaw 上做过 post-train**，会更好用。正在联合研究团队/labs 做 **~100–120 个任务的公开 benchmark**。承诺模型公平：zero-day 支持、不偏袒、feature parity。
- **记忆远未解决**（他强烈反对「已解决」论）：换模型后旧记忆能否被理解？**多租户**（团队共用一个 claw，哪些记忆能给谁）目前只能假设「一切可互换」。是当前最难的问题空间之一。
- **多智能体的瓶颈是 context 而非成本/延迟**：9/10 的情况单 agent 足够；只有当某个可重复、带独立 system prompt 的任务出现，才「切」出一个专门 agent。心法：像**管理一个员工**、拆分工作量。

### 康威定律与 2026 的 agentic engineering（详见 [[conways-law-agents]]）
- 复杂组织把自身架构**镜像**进 agent（manager/planner/sub-agent/嵌套团队），这是继承旧包袱、未必最优；startup 能「白纸重来」agent-first 因而快。真正该问的是 COO 之问：**未来的团队结构/工作场所长什么样**。方法是实验——白纸、一天搭一个、迭代。
- **「工厂」隐喻**：让 agent 当主力工程师非常难，他们造了大量测试设施——任一 maintainer 的 agent 能在 ~20 秒内在多数云上拉起任意 OS/硬件、进去截图/录屏/点击验证、附上 proof。「工厂需要全部机器才能转——QA、灯、水、电，不能只有一条传送带。」

### 移动 App、竞品、整合
- iOS/Android **全原生代码**（不用框架，因为 AI agent 写原生代码很轻松）；App 代码 1 月就在仓库里，等基金会注册成实体才敢用官方名义发。差评→反馈→两周迭代成「几乎全新产品」。核心工程团队**仅 5–6 人**。
- 不视任何人为竞品（Manus / Jspark / **[[hermes-agent|Hermes]]**）；OpenClaw 是**开源 harness 层 / 个人 agent 层**。对 Hermes：开发者觉得它「更线性/更连贯」，记忆与 onboarding「很不一样、很有意思」，但**产品根本不同**。整合？AI 工具至今没整合过（成千上万家公司），会有更多 framework，大尺度上只有少数几家的位置。

### 基金会 = AI agent 界的瑞士（详见 [[openclaw-foundation]]）
- **501c 非营利**，美国注册，不产生 revenue（有也回流社区）；靠社区（GitHub $5）+ 生态捐赠。不被任何一家公司/国家/实体控制 → 被中国、美国科技公司、普通人共同拥抱；很多人**正因为它是基金会才愿合作**。**Positive-sum**：自己不造资本，但为产业创造造资本的机会。
- **Peter Steinberger 去了 OpenAI**：消除单点依赖风险——已是一支工程师团队、commits 在平滑化；「以为只有 Peter」是误解。决策上「从没拍过桌子」，分歧是健康的（美国企业要的 feature，中国 maintainer 说「对我们没用」→ 逼出对所有人都公平的设计）。

### 下一步预测（未来 12 个月）
- **agent 之间如何通信协作**是下一个爆点——像手机：人人一部不同的手机，但能互相打电话；「我的个人 agent 打给我的工作 agent」协同解题。比安全更复杂（不同企业/软件/架构）。对「agent 发明人类看不懂的语言」的惊悚故事保持谨慎：别因为「X 发生了」就断言「所以是 Y」，先搞清成因（呼应 mechanistic interpretability）。

## 与 vault 的关联
- 补齐了长期缺失的 **[[openclaw]]** 中心实体页——此前散见于 [[claude-code]]（Jensen 的「OpenClaw = the iPhone of tokens」）、[[microsoft]]（Scout = enterprise OpenClaw + MXC 容器）、[[agentic-engineering-primitives]]（Garry Tan 从 OpenClaw 逐周学原语）、[[ai-memory-open-source-landscape]]（MemClaw/SkillClaw）。
- Vincent 的康威定律警告，与 [[multi-agent-patterns]] 里 [[lidang|立党]]「组织架构模拟是天坑」正面互证。
- 「工厂」隐喻与 [[garry-tan|Garry Tan]] 的 software factory、[[ai-native-company]] 同构。
- 「记忆未解决 + 多租户」为整套记忆研究（[[ai-agent-memory]] 等）补一条来自生产一线的现实注脚。
