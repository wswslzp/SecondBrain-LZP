---
title: "How to Build an AI Quant System. Test 1,000 Strategies per Week."
author: "[[zostaff]]"
date_ingested: 2026-05-17
date_published: 2026-05-13
url: "https://x.com/zostaff/status/2054533153893613839"
repo: "https://github.com/zostaff/ai-quant-researcher"
type: article
tags:
  - quant-trading
  - ai-agents
  - backtesting
  - statistical-validation
  - llm-tooling
  - finance
---

# How to Build an AI Quant System

## Summary

zostaff 提出：LLM 把量化策略生成速度提升 50×（从数月到一晚），但若**验证**不同步加速，结果只是把"统计垃圾"产量也放大 50×。文章给出一套基于 6 个 Claude Agent + 1 个 Orchestrator 的研究流水线，三道硬性门槛（Critic 审查、Deflated Sharpe Ratio、组合相关性）阻止策略未经验证就上线。所有组件以 ~4500 行代码 + 54 个测试开源在 [ai-quant-researcher](https://github.com/zostaff/ai-quant-researcher)。

## Key Points

- **核心洞察**：生成速度 ≠ 生产力。研究纪律必须做成系统约束，让 AI 没法走捷径
- **6 Agent 架构**：Hypothesis / Data / Code / Critic / Risk / Memory，每个 = 单次 Claude 调用 + 严格 role prompt
- **三道硬门** ([[three-gate-evaluator]])：
  1. Critic 结构审查（"ASSUME THIS STRATEGY IS BROKEN"）
  2. Deflated Sharpe Ratio（多重检验惩罚，无人工 override）
  3. 与已接受策略的 OOS PnL 相关性 < 0.7
- **5 类数据泄漏** ([[backtest-leakage]])：centered windows / 忘记 shift(1) / 全样本标准化 / 幸存者偏差 / 财报重述
- **Deflated Sharpe Ratio**（[[deflated-sharpe-ratio]]）：测 10,000 个零 alpha 策略，纯运气下 IS Sharpe 也能超过 3.5。DSR 用 `n_trials` 把 Sharpe 打折，`dsr_pvalue < 0.95` 直接拒
- **Critic Agent 的对抗式 prompt**：检查 look-ahead / 幸存者 / 过拟合 >50% / trades <100 / 机制不一致 / 隐藏优化 / 不实际成本 / Sharpe 下隐藏的尾部风险
- **真实迭代示例**：6M 动量策略 IS Sharpe 2.1 → Critic 揪出 look-ahead → 修正后 IS 0.7（**look-ahead 就是全部 alpha**）→ 加入横截面 vol 归一化 → DSR 0.97 接受
- **AI 仍然失败的场景**：regime breaks、真正创新、对抗市场（别人也用 LLM）、容量（$100k 工作 / $10M 崩）、审计可解释性
- **关键判别测试**：如果你无法用大白话向一个怀疑的 senior PM 解释"why"策略应该 work，不要交易它

## Concepts

- [[ai-quant-system]] — AI 量化系统架构与流水线（核心概念页）
- [[deflated-sharpe-ratio]] — 多重检验下的夏普率惩罚机制
- [[backtest-leakage]] — 五类数据泄漏与防御
- [[walk-forward-validation]] — 时序数据的正确验证方法
- [[three-gate-evaluator]] — 三道硬门评估器设计哲学
- [[multi-agent-research-loop]] — 多 Agent 研究循环（Hypothesis-Code-Critic-Risk-Memory）

## Entities

- [[zostaff]] — 文章作者，开源 ai-quant-researcher 仓库

## 个人备注

- 本文是 [[hermes-agent]] / [[claude-code]] 之外，最务实的"LLM 做严肃研究工作"案例 —— 关键不是 LLM 写代码，而是**对抗式验证 + 多重检验惩罚**作为系统约束
- 与 [[memory-consolidation]] 和 [[forgetting-mechanisms]] 有微妙呼应：Memory Agent 跟踪所有失败尝试是为了正确计算多重检验门槛，类似"经验丰富的研究员凭直觉知道这条路不通"的工程化版本
- 对长期持有 + 风控敏感的投资者：文章里 Kill-switch 设计 + Audit Log 思路可以套用到任何**有规则的资产管理决策**上，不只是高频量化
- 标题"1000 strategies/week"是标题党 —— DSR 的设计本身就在说"试得越多门槛越高"，作者其实是在反对盲目暴力搜索
