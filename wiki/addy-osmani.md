---
title: "Addy Osmani"
tags: [person, anthropic, claude-code, software-engineering, code-review]
date_created: 2026-10-27
date_modified: 2026-10-27
related: ["[[anthropic]]", "[[claude-code]]", "[[agentic-code-review]]", "[[claude-code-team-code-review]]"]
---

# Addy Osmani

[[anthropic|Anthropic]] 的 [[claude-code|Claude Code]] 团队成员（X 简介：`Claude Code @anthropicai`），知名软件工程作者与技术传播者（个人网站 `addyosmani.com`）。

## 核心贡献与观点（本知识库收录）

在《[[claude-code-team-code-review|How the Claude Code team does code review]]》（2026-10-26）中，Addy Osmani 系统拆解了当 Claude 编写了 Claude Code 约 90% 的代码时，团队如何重构代码审查体系（详见 [[agentic-code-review]]）：

- **重新定义代码审查问题**：从“有人读过代码了吗？”转向“这次变更可能出什么错？哪一层检查（自动化或人类）最适合拦住它？”，把审查从“事后关卡”变成写作时持续运行的“拼写检查”。
- **人类时间的双面成本**：省下审代码的时间却增加了修线上 Bug 的时间，等于没有省时间。以**回滚率（revert rate）和线上事故率（incident rate）为护栏指标**，追求绝大多数 PR 在最多 1 名人类介入下合并。
- **六层防御 + 快速回滚**：Pre-PR 可运行验证与全新上下文 subagent 审查（配合 `CLAUDE.md` 与 `REVIEW.md`）→ 多 Agent 并行找 Bug + 投票过滤的 PR 审查 → 阻断式安全审查 → 阻断式 CI → 基于变更风险分类器的人工审批 → Merge queue + Feature flags + 内部 dogfooding → 秒级回滚与周度 on-call 复盘。
- **审查收敛与事故即 Eval**：用历史线上事故集（incidents + reverts）每日评估审查系统；针对 Agent 作者与 Agent 审查员曾出现的“一夜死循环 50+ 次”现象，建立 3 轮上限、仅审增量 diff、按 Bug 类别报错等收敛机制。
- **机器读代码时代的工程文化**：人类聚焦于愿景/品味（该不该做）、高危路径审计、架构规范、核验证据（Proofs）与最终问责（“You land it, you own it”）；团队通过让 Claude 即时生成代码切片讲解（Explainer）或可视化微型组件（Mini artifact）来替代逐行读琐碎 diff 的知识传递。

## References

- [[claude-code-team-code-review]] — How the Claude Code team does code review（2026-10-26）
