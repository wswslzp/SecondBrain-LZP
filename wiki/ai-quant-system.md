---
title: "AI Quant System"
tags: [quant-trading, ai-agents, backtesting, llm-tooling]
date_created: 2026-05-17
date_modified: 2026-05-17
related: ["[[deflated-sharpe-ratio]]", "[[backtest-leakage]]", "[[walk-forward-validation]]", "[[three-gate-evaluator]]", "[[multi-agent-research-loop]]"]
---

# AI Quant System

## Overview

**AI Quant System** 指利用 LLM Agent 自动生成、验证、淘汰量化交易策略的研究流水线。代表作是 [[zostaff]] 的开源项目 [ai-quant-researcher](https://github.com/zostaff/ai-quant-researcher)（2026-05），主张：

> LLM 把策略生成速度提升 50×（PhD + 数月 → 一晚），但若**验证**不同步加速，得到的只是 50× 的统计垃圾。

核心解法：把"研究纪律"做成系统约束，让 AI 没法走捷径。

## Architecture（zostaff 的版本）

**6 Agent + 1 Orchestrator + 3 Hard Gates**

```
Hypothesis → Data → Code → Backtest → Critic → Risk → Memory → 下一轮
```

| Agent | 职责 |
|-------|------|
| Hypothesis | 生成带"经济故事"的假设（必须命名机制：行为偏差？资金约束？信息滞后？）|
| Data | 取数 / 时点对齐 / point-in-time 修正 |
| Code | 写向量化回测，强制 `shift(1)` 和成本 |
| Critic | 对抗式审稿：找泄漏、过拟合、p-hacking |
| Risk | 仓位 + 与现有组合相关性 |
| Memory | 记录每次尝试，用于多重检验惩罚 |

每个 Agent = 单次 Claude API 调用 + 严格 role prompt + 受限工具集 + 明确接受标准。详见 [[multi-agent-research-loop]]。

## 三道硬门

1. **Critic Agent 通过结构审查**（[[three-gate-evaluator]]）
2. **Deflated Sharpe Ratio 通过多重检验门槛**（[[deflated-sharpe-ratio]]，无人工 override）
3. **Risk Agent 确认与现有 book 不相关**（OOS PnL 相关性 < 0.7）

任意一道挂掉策略就死。

## 与同类项目的区别

| 项目 | DSR 硬门 | 多 Agent | Kill Switch |
|------|---------|---------|-------------|
| ai-quant-researcher (zostaff) | ✅ | ✅ 5 Agents | ✅ |
| TradingAgents | ❌ | ✅ | ❌ |
| AgentQuant | ❌ | ✅ | ❌ |
| QuantEvolve | ❌ | ✅ | ❌ |

DSR 作为**无人工 override 的硬门**是 zostaff 的关键差异点。

## AI 仍然失败的场景

- **Regime breaks** — LLM 不会感知 2020 那种范式断裂（pandemic + 零利率 + meme stocks）
- **真正的创新** — LLM 只会重组，不会发明下一个 cointegration 框架
- **对抗市场** — 别人也用 LLM，alpha 衰减更快
- **容量** — $100k 工作的策略，$10M 就崩（无市场冲击直觉）
- **审计** — "LLM 觉得是好主意" 不是给监管/LP 的合法答复

## 关键判别测试

> 如果你无法用大白话向一个怀疑的 senior PM 解释"**why**"策略应该 work，不要交易它。经济直觉测试自 1986 年以来没变，只有生成速度变了。

## Sources

- [[ai-quant-system-zostaff]]

## Related

- [[deflated-sharpe-ratio]]
- [[backtest-leakage]]
- [[walk-forward-validation]]
- [[three-gate-evaluator]]
- [[multi-agent-research-loop]]
- [[claude-code]]
- [[hermes-agent]]
