---
title: "zostaff"
type: entity
aliases:
  - "@zostaff"
date_created: 2026-05-17
date_modified: 2026-05-17
related: ["[[ai-quant-system]]"]
---

# zostaff

X handle: [@zostaff](https://x.com/zostaff) — 自我描述: "can't play me, i wrote the rules"

## Overview

量化研究者 / 工程师，2026 年 5 月发表长文《[How to Build an AI Quant System. Test 1,000 Strategies per Week.](https://x.com/zostaff/status/2054533153893613839)》（328K Views），提出基于 6 Claude Agent + 三道硬门的 AI 量化研究流水线，开源至 [ai-quant-researcher](https://github.com/zostaff/ai-quant-researcher)（~4500 行代码 + 54 测试）。

文章核心论点："LLM 把策略生成速度提升 50×，但没把验证速度提升 50× 的话，得到的只是 50× 的统计垃圾"。是 2026 年中少数把"研究纪律"做成系统约束的公开作品。

## Notable Work

- **ai-quant-researcher**（GitHub: zostaff/ai-quant-researcher）— 开源研究验证引擎
  - vectorized + event-driven backtest（含 slippage / partial fills）
  - feature pipeline + 泄漏检测器
  - walk-forward + purge / combinatorial purged CV
  - **Deflated Sharpe Ratio 作为硬门**（无人工 override，TradingAgents/AgentQuant/QuantEvolve 都没有的）
  - 5 个 Claude Agent：Hypothesis、Code、Critic（per-market templates）、Risk、Memory（SQLite）
  - AST-validated sandbox 执行 LLM 生成的代码
  - Production kill-switch
  - 5 个示例（无需 API key，合成数据）展示 DSR 如何杀掉 1000 个随机策略

## Sources

- [[ai-quant-system-zostaff]]

## Related

- [[ai-quant-system]]
- [[deflated-sharpe-ratio]]
- [[three-gate-evaluator]]
