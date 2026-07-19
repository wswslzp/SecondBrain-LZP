---
title: "Multi-Agent Research Loop"
tags: [quant-trading, ai-agents, llm-tooling]
date_created: 2026-05-17
date_modified: 2026-05-17
aliases:
  - 多 Agent 研究循环
related: ["[[ai-quant-system]]", "[[three-gate-evaluator]]", "[[hermes-agent]]", "[[claude-code]]", "[[multi-agent-patterns]]"]
---

# Multi-Agent Research Loop

## Overview

**Multi-Agent Research Loop** 是用多个特化 LLM Agent 协同完成研究工作的设计模式。最具代表性的实现是 [[zostaff]] 的 [[ai-quant-system]]：6 个 Agent + 1 个 Orchestrator + 3 道硬门，**端到端自动化生成、验证、淘汰量化策略**。

## 关键设计原则

### 1. 单一职责

每个 Agent = 单次 LLM API 调用 + **严格的 role prompt** + **狭窄的工具范围** + **明确的接受标准**。

不要做"全能 Agent"。Critic 只批判，不修代码。Code Agent 只生成代码，不评判好坏。

### 2. 对抗式 prompt

Critic 的开场白：
> "ASSUME THIS STRATEGY IS BROKEN until you prove otherwise."

这种**默认怀疑**的提示词比"请审查"产生显著不同的输出 — LLM 倾向于讨好原作者的意图，必须显式反向引导。

### 3. Memory 跨循环累积

Memory Agent 不只是日志，是**多重检验门槛的来源**。每一次失败都让下一个候选的统计门槛更高（详见 [[deflated-sharpe-ratio]]）。

## zostaff 的 6 Agent 架构

| Agent | 角色 | 工具 | 输出 |
|-------|------|------|------|
| **Hypothesis** | 生成具体策略假设（命名机制：行为 / 资金约束 / 信息滞后）| Web search、past failures memory | `Hypothesis` 对象 |
| **Data** | 取数 / 时点对齐 / PIT 修正 / 工程特征 | Data loaders、FeaturePipeline | DataFrame |
| **Code** | 写向量化回测代码（强制 `shift(1)` 和成本）| Code execution sandbox | Python 代码字符串 |
| **Critic** | 对抗审查泄漏、过拟合、p-hacking | Code reader、metrics analyzer | `CritiqueResult` |
| **Risk** | 仓位 + 与现有 book 相关性 | Portfolio state | 仓位决策 |
| **Memory** | 记录所有尝试，提供 `n_total_attempts` | Attempt database (SQLite) | 累积统计 |

## 控制流

```
Orchestrator:
  for i in range(max_iterations):
      h = Hypothesis(memory)            # 避免重复
      data = Data(h)
      h.code = Code(h, columns)
      result = backtest(h.code, data)

      # Gate 1
      critique = Critic(h, h.code, result)
      if not critique.passes: continue

      # Gate 2
      dsr = DeflatedSharpe(oos_ret, memory.n_total_attempts)
      if dsr.verdict == 'reject': continue

      # Gate 3
      if max_correlation_to(accepted) > 0.7: continue

      accepted.append((h, result))
      if len(accepted) >= target: break

  return accepted
```

## 与单 Agent / 普通 LLM 的对比

| 模式 | 优势 | 劣势 |
|------|------|------|
| 单次 LLM 提问 | 简单 | 容易自我说服 / 缺乏验证 |
| 思维链（CoT） | 推理清晰 | 仍是单视角 / 同分布偏差 |
| **多 Agent 对抗** | 不同 prompt 不同视角 / 可验证 | API 成本 / 设计复杂 |

关键：**对抗性来自 prompt 设计**，而不是不同模型。zostaff 全用 Claude Sonnet，差异只在 system prompt。

## 与 [[hermes-agent]] / [[claude-code]] 的关系

- **[[claude-code]]** 是 Anthropic 自己的 CLI，单 Agent 但工具丰富
- **[[hermes-agent]]** 是 Roc 维护的自我学习框架，单 Agent + skills + memory + cron
- **AI Quant Researcher** 是**任务专属**的多 Agent 系统，每个 Agent 单一职责

它们之间不矛盾 — 你可以**用 hermes-agent 来 orchestrate 多个 ai-quant-researcher 风格的多 Agent 工作流**。Hermes 的 cron + skills 可以替代 Orchestrator 的脚手架。

## 个人备注

这个模式的核心可迁移点 **不是量化金融**，是：

> 任何"自我验证"困难的认知任务，都应该拆成 **生成 + 对抗审查 + 统计校正** 三个独立 Agent。

可应用到：
- 投资决策（生成观点 / 红队反驳 / 历史命中率校正）
- 代码 review（写 / 找 bug / 测试覆盖率统计）
- 论文研究（提假设 / 找反例 / meta-analysis）
- 个人笔记综合（concept page generation / contradiction lint / freshness check）

## 与 [[multi-agent-patterns]] 的关系

本模式正是 [[lidang|立党]] 在 [[multi-agent-patterns]] 中称许的「有产出的 multi-agent」正例：单一职责、有明确接受标准与硬门、go-driven，而非「七嘴八舌、无决策者」的组织架构模拟（那类是他所说的「超级大天坑」）。

## Sources

- [[ai-quant-system-zostaff]]

## Related

- [[ai-quant-system]]
- [[three-gate-evaluator]]
- [[deflated-sharpe-ratio]]
- [[hermes-agent]]
- [[claude-code]]
