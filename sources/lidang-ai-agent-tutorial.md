---
title: "立党AI学习研究完整教程（第一期）"
author: "立党 lidang"
date_ingested: 2026-07-19
date_published: 2026-06-23
tags: [ai-agents, coding-agent, multi-agent, claude-code, matlab, eda, lean4, china]
url: "https://www.youtube.com/watch?v=BqF6PUAXY1M"
type: youtube-transcript
---

# 立党AI学习研究完整教程（第一期）

[[lidang]] 面向 2026 年 AI agent 初学者/大学生/非程序员的一期"学习路线"更新。整期围绕五个话题展开，从「怎么选模型」一直讲到「multi-agent 什么时候该用、什么时候是天坑」。

## 五个部分

### 1. 选模型：85 分 vs 95 分

- 以前无脑推荐 OpenAI / Anthropic 订阅；现在认为对**大部分普通编程工作**，中国大陆用户直接买国产 coding plan 即可——智谱、Moonshot（月之暗面）、阿里、DeepSeek、小米、快手、MiniMax、阶跃星辰等一线二线厂商他"一碗水端平"。
- 这些 80–90 分模型性价比很高，够学生和上班族日常 coding。
- 95 分模型确实强大但对普通人**太贵**。**对日常 agentic coding，85 分和 95 分没有显著差异**——就像初中数学题不需要陶哲轩来做。95 分只对"世界级难题"才有意义。
- 详见 [[build-your-own-agent]] 的「选模型」小节。

### 2. 手写最小 agent（每个大学生的第一节课）

- 立党声称自己**2023 年 4 月**就提出 coding/SWE agent 概念，早于姚顺宇的 2023 年 9 月 ReAct/SWE agent。
- 主张：当代计算机/AI 专业大学生的**第一节课 = 从头手写一个 minimum SWE/coding agent 并跑通**。类比过去学生手搓 Lisp interpreter、编译器、操作系统、数据库、transpiler。
- 三步法：**看懂 → 想明白/设计 → 实现并通过测试**。
- 然后对照现代 coding agent（[[claude-code]] / Codex / OpenCode / Kimi code）学它们已经历"四五次工业革命"的机制。详见 [[build-your-own-agent]]。

### 3. 非程序员的 headless 用法（价值 10 万–30 万刀）

- 给"不会编程的 99% 人"的**万能方法**：给 Claude Code 绑银行卡 → 建 temp folder 塞进所有任务相关材料 + 指令 → 写 Node/Bun/Python 脚本从 terminal 以 **headless 模式**调用、`--dangerously-skip-permissions` 开全权限 → 状态写入 JSON → 让 agent 自己端到端解决并汇报。
- "高中生都能干"。核心心法：把 agent 抽象成"一个有人格、能解决问题、办事自动化的人"；99% 场景一个好的通用 agent + 买得起的最好模型胜过自己手搓 bespoke agent。详见 [[headless-agent-pattern]]。

### 4. Agent 的能力边界与舒适区

- **能力边界**：AI agent 不是神/超人/黑箱，不能违反 causality 或 information theory——预测不了彩票、明日股价、黎曼猜想、三年后墨西哥 GDP。判断准则：先问"人有没有合理流程与方法论能系统解决"。
- **舒适区** = 封闭、可完整编译/运行/模拟/仿真、可无限试错、可精确验证的环境（这是 "go-driven" 的前提）。五大领域：编程、数学（Lean 4）、电子/芯片设计（HDL/EDA）、MATLAB + Simulink、CAD/机械设计。**金融/市场是开放对抗环境，不是舒适区**。详见 [[agent-comfort-zone]]。

### 5. Multi-agent 的适用与不适用

- **不适合**：编程并行（merge 地狱）、顺序 role-play 流水线（MetaGPT）、公司/组织架构模拟（CrewAI、AutoGen、腾讯 workbody）——后者是"过去两三年公认的超级大天坑"。
- **适合**：map-reduce 式大规模并行（爬虫、research、数据清洗、并行客服、审核）；以及有良好流程控制 + go-driven 的 multi-agent（他已开源、1000+ star）。
- **价值判断**：只有当 1000× 成本换来 ≥10–100× 的**时间**提升才值得；token 越来越便宜/快、模型越来越聪明 → multi-agent 是唯一值得相信的 agent scaling 路径。详见 [[multi-agent-patterns]]。

## 关键要点

> "Claude Code 设计出来就是为了让你这么用的。" —— headless 用法不是 hack，是官方期待的用法。

> "go-driven 的前提是你必须可以验证、可以仿真、可以在本地运行。"

> "只要搜索空间巨大，让 agent 跑 10 个小时，它一定能帮你解决一些问题。"

- 作者称舒适区里的**每一个领域都值 1000 万美元**（举例数学公司 Axiom 已融资 1 亿美元）。
- 下一期预告：用**管理学方式**做真正合理的 multi-agent 管理。

## 相关页面

- [[lidang]] — 作者实体页
- [[build-your-own-agent]] — 手写最小 agent + 现代机制清单
- [[headless-agent-pattern]] — 非程序员的通用 headless 方法
- [[agent-comfort-zone]] — 封闭可验证环境 = agent 舒适区
- [[multi-agent-patterns]] — multi-agent 适用/不适用判断
- [[claude-code]]
- [[ai-destroying-programmer-jobs]] — 同作者早前一期
