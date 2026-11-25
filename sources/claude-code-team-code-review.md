---
title: "How the Claude Code team does code review"
author: "Addy Osmani (@addyosmani)"
date_ingested: 2026-10-27
date_published: 2026-10-26
tags: [claude-code, code-review, anthropic, ai-agents, software-engineering, evals]
url: "https://x.com/addyosmani/status/2114604912520921136"
type: social-article
related: ["[[addy-osmani]]", "[[agentic-code-review]]", "[[claude-code]]", "[[anthropic]]", "[[agentic-engineering-primitives]]", "[[multi-agent-patterns]]", "[[ai-native-company]]", "[[context-management]]"]
---

# How the Claude Code team does code review

[[addy-osmani|Addy Osmani]]（[[anthropic|Anthropic]] [[claude-code|Claude Code]] 团队）对 Anthropic 官方工程文章《Solving Code Review at Anthropic》的重写版。核心背景：Claude Code 约 **90%** 的代码由 Claude 自己编写；Anthropic 主 monorepo 日均合并变更从 2026 年 5 月的 ~2,500 飙升至 9 月的 **30,000+**。在 6–9 月间，Claude Code 合并的 PR 数翻倍，但**被回滚（revert）的 PR 比例下降了 40% 以上**（上述数字均为团队自述，未独立审计）。

核心命题：人工逐行读代码已不可持续，“有人读过代码了吗？”是错误的问题；正确的问题是**“这次变更可能出什么错？哪一层检查（自动化或人类）最适合拦住它？”**

---

## 核心要点与方法论

### 1. 人类时间的“双面成本”与护栏指标
- **双面成本**：人类时间 = 花在审查代码上的时间 + 花在修烂代码引入的 Bug 上的时间。只降前者不降后者，只是转移成本。
- **目标**：绝大多数 PR 在**最多 1 名人类介入（可以是作者本人，即操控 Agent 的工程师）**下完成合并，且不增加回滚率或线上事故率。
- **指标体系**：
  - **效率指标**：每个 PR 的人类批准数中位数与 P95、人类评论数、PR 等待人工时长；
  - **护栏指标（Guardrails）**：回滚率（revert rate）与线上事故率（incident rate）。

### 2. 六层检查 + 一层快速回滚（详见 [[agentic-code-review]]）
1. **PR 前验证（Pre-PR verification）**：核心在创建 PR 前完成。要求 Claude 提供**可运行的证据（proof）**（测试、构建、UI 截图对比设计稿），并用**干净上下文的 subagent** 审查 diff（呼应 [[context-management]]）。Boris Cherny 估计配备验证流程能将 Claude 产出质量提升 **2–3 倍**。高频重复问题沉淀到 `CLAUDE.md`（保持简短，引用其他文档）和 `REVIEW.md`（由 Code Owners 定义“项目级失败”、限制 nitpicking、要求精确行号与顶层问题计数总结）。
2. **PR 级多智能体审查（AI review on every PR）**：每个 PR 必经 Claude 审查（外部产品为 *Code Review for Claude Code* 及本地 `/code-review`，设 Quick / Standard / Deep 三档）。引入后内部 PR 获实质性审查评论的比例从 **16% 升至 54%**。底层采用**多智能体并行找 Bug + 独立投票过滤误报 + 过滤纯代码风格/清理项**；保留项按 Important / Nit / Pre-existing（历史遗留不罚当前作者）分级。所有讨论串必须修复或附理由 resolve，常由 Agent 夜间自动修完并重审。
3. **可阻断的安全审查（Security review）**：未关闭的安全或代码审查发现一律阻断合并；后续 Commit 修复后自动关闭（开源 GitHub Action 或 `/security-review`）。
4. **可阻断的自动化 CI 检查**：全平台测试、lint、类型检查、构建，PR 模板强制回答“如何测试”与“如何回滚”（Claude 可代写，作者负责核实）。
5. **按风险分级的人工审批（Human approval scaled by risk）**：风险等级由分类器根据**变更内容（而非作者身份）**判定；敏感路径与 CI 工作流文件强制额外审批。仅仓库受信任名单（Trusted list）作者享宽松路径；**Agent 的批准绝不计入人类批准**；Agent 提 PR 时其人类操控者（Operator）算作一名审查人；每次批准仅对单次 Commit 有效，一旦推送新不可信 Commit（如 Agent 再次 push 或手动解冲突）即撤销批准。
6. **合并队列、特性开关与分阶段发布**：Merge queue 防止两个各自绿灯的 PR 合出挂掉的 `main`；Feature flags 先向 Anthropic 员工灰度，再按 `latest` → `stable` 渠道推进。
7. **快速反馈与回滚（Fast feedback & rollback）**：特性开关支持免部署秒级关闭；每周轮值 on-call，事故复盘必问**“本该由哪一层拦住这个问题？”** 漏网之鱼会反哺为新的 `CLAUDE.md` 规则、Skill 或自动化检查。

### 3. 审查系统的持续评估与“收敛性危机”
- **线上事故即评估集（Incidents are the eval）**：收集所有引发事故的 PR、向前修复（fix-forwards）与回滚，由熟悉代码库的工程师标定真值，**每天**用该集合评估审查系统。
- **噪音控制**：按人类对评论的反应（修复 / 拒绝 / 澄清有意为之 / 认为无关紧要）分类监控，并在已知干净的 PR 上测“有害修改建议率”。
- **Agent 循环失控案例**：人类忽略一条 nit 只需 1 秒，而 Agent 处理一条 nit 会产生新 Commit 并触发新一轮审查。团队曾观察到 CLI 项目的一个 PR 因 **Agent 作者与 Agent 审查员来回拉锯，一夜之间死循环了 50 多次**。`git blame` 显示被反复标记的代码中约 **59%** 从第一轮就在那里（每轮都在翻旧账而非找新 Bug）。
- **收敛机制（Convergence）**：
  1. 限制轮数：**3 轮后**要求作者重新评估整体方案；
  2. 初始几轮后，**仅对新增 diff 重审**；
  3. 指明 **Bug 类别（Class of bugs）** 让作者一次性全修，而非只改一行；
  4. 禁止重复报告已见问题；夜间单独在全库跑历史 Bug 扫描。

### 4. 回路中的人类、团队上下文与文化
- **人类不可替代的五件事**：① 决定“到底该不该做”（愿景、品味、目标）；② 审计高危代码（计费、自动更新、CI、认证、安装器）；③ 架构审查（确立后续规范）；④ 核验证据（Proofs）——“说不出自动化检查会漏掉什么，就别求 👍”；⑤ **承担责任**（“无论谁敲的代码，每个发布的变更背后必须有一个人负责”）。
- **机器读代码时代的团队学习**：没人拥有也不需要拥有完整代码库的心智模型。需要改某块代码时，让 Claude 现场生成**最新切片讲解（Explainer）**甚至**可视化交互组件（Mini artifact）**，比逐行读琐碎 diff 学到更多。
- **“谁合入，谁负责”（You land it, you own it）**与**及时转向（Changing course）**：公开 Slack 频道协作；写代码成本极低，因此在讨论串早期直接关掉方向不对的 PR 没有沉没成本痛感。

---

## 与既有材料的关联与张力

- **对 [[dhh-lex-fridman|DHH]] / [[garry-tan|Garry Tan]] 个人工作流的团队级补完**：DHH（16 线程 + 多模型互审）与 Garry Tan（一人软件工厂）展示了**单人 / 极小团队**如何用 Agent 高速产出；本文则展示了**数十人工程团队与上万日均 PR 的代码库**如何防止被 Agent 海量 PR 冲垮（如 DHH 在 Basecamp 5 遇到的“每个 PR 单看合理、合起来毁掉架构”）。
- **对 [[multi-agent-patterns]] 的正反印证**：
  - **正面**：PR 审查阶段的“多 Agent 并行找 Bug + 独立投票去误报”是干净的 map-reduce 式验证，与 [[multi-agent-research-loop]] 同构；
  - **反面**：Agent 作者与 Agent 审查员一夜死循环 50+ 次，是两个无收敛硬门的 Agent 互相触发的典型工程事故，为立党的“多 Agent 自由交互天坑”提供了 Anthropic 内部实证。
- **与 [[ai-native-company]] 的闭环呼应**：“把线上事故变成每日运行的 Eval 集合”以及“漏检问题转化为 `CLAUDE.md` / `REVIEW.md` / Skill”，正是 Diana Hu 所说的 **open-loop → closed-loop（PID 控制）** 在软件工程质量体系中的具体实现。

---

## 原始材料

- [[raw/How the Claude Code team does code review - Addy Osmani|中英对照原文与配图]]
