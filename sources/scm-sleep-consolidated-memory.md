---
title: "SCM: Sleep-Consolidated Memory"
author: "Saish Shinde"
date_ingested: 2026-04-26
date_published: 2026-04-22
tags: [ai-memory, sleep-consolidation, neuroscience, llm-architecture, forgetting]
url: "https://arxiv.org/abs/2604.20943"
---

## Summary

SCM (Sleep-Consolidated Memory) 是一个**受脑科学启发的 LLM 记忆架构**，将人类睡眠中的记忆处理机制移植到 AI Agent 系统中。由 Saish Shinde (Clyrai IP Studio) 于 2026 年 4 月发表。

核心创新：它不只是给 LLM 加一个外挂记忆库，而是实现了完整的**觉醒-睡眠周期**——觉醒时编码记忆，"睡眠"时自动巩固重要记忆、修剪无用记忆、通过"做梦"建立新联想。

## Key Points

- **五模块架构**：MeaningEncoder（语义编码）→ ValueTagger（4D 重要性标签）→ WorkingMemory（7项海马体模拟）→ LongTermMemory（NetworkX 语义图）→ SleepCycle（NREM/REM/遗忘）
- **4 维重要性评分**：新颖度 (0.30) + 情绪价值 (0.20) + 任务相关性 (0.35) + 重复频率 (0.15)
- **三阶段睡眠**：NREM（Hebbian 强化 + 突触下调）→ REM（图上随机游走产生新联想）→ 主动遗忘（基于保持分数剪枝）
- **工作记忆限制 7 项**（Miller 定律），制造自然的记忆压力
- **全部本地推理**：Llama 3.2 (2B) + all-MiniLM-L6-v2，隐私友好
- **效果**：10 轮对话完美召回 (22/22)，90.9% 噪声消除，图大小缩小 3 倍
- **代码未开源**（计划同行评审后发布）

## Key Formulas

**重要性评分：**
$$I(c) = 0.30 \cdot v_{\text{novelty}} + 0.20 \cdot |v_{\text{emotional}}| + 0.35 \cdot v_{\text{task}} + 0.15 \cdot v_{\text{repetition}}$$

**NREM Hebbian 强化：** Δs_ij = η · I(c_i) · I(c_j)，η = 0.1
**突触下调：** s_ij ← 0.8 · s_ij（每周期衰减 20%）
**遗忘保持分数：** S(c) = 0.8 · I(c) + 0.2 · (1 − e^{−0.01·Δt})

## Concepts

- [[sleep-consolidated-memory]]
- [[memory-consolidation]]
- [[forgetting-mechanisms]]
- [[ai-agent-memory]]
- [[working-memory]]
- [[hebbian-learning]]
- [[complementary-learning-systems]]
