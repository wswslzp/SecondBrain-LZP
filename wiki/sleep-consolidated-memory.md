---
title: "Sleep-Consolidated Memory (SCM)"
tags: [ai-memory, sleep-consolidation, neuroscience, llm-architecture]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[memory-consolidation]]", "[[forgetting-mechanisms]]", "[[ai-agent-memory]]", "[[working-memory]]", "[[hebbian-learning]]", "[[complementary-learning-systems]]"]
---

# Sleep-Consolidated Memory (SCM)

SCM 是由 Saish Shinde (Clyrai IP Studio) 提出的**受脑科学启发的 LLM 记忆架构** (arXiv:2604.20943, 2026-04)。核心理念：人脑不是 append-only 数据库，而是一个动态自组织系统——AI Agent 的记忆也应该如此。

## 解决了什么问题

现有 LLM 记忆方案的根本缺陷：

| 方案 | 问题 |
|---|---|
| Context Window | Token 预算有限，中段信息丢失 ("Lost in the Middle") |
| RAG / Vector DB | 无限增长，不区分重要性，没有遗忘 |
| MemGPT/Letta | OS 分层隐喻但无生物记忆过程 |
| Mem0 | 只提取事实+相似度检索，"永远清醒"——不巩固也不遗忘 |

## 五模块架构

```
Input → MeaningEncoder → ValueTagger → WorkingMemory (7 items)
                                             ↓
                                    [Sleep Trigger]
                                             ↓
                              ┌──── NREM Consolidation
                              ├──── REM Dreaming
                              └──── Intentional Forgetting
                                             ↓
                                     LongTermMemory (Graph)
```

### 1. MeaningEncoder
将非结构化文本转为**语义图**（概念 + 类型化关系）。用 Llama 3.2 (2B, Q4_K_M) 本地推理 + all-MiniLM-L6-v2 (384-dim) 嵌入。完全本地运行，隐私友好。

### 2. ValueTagger — 4D 重要性向量
每个概念在四个维度上打分：
- **新颖度** (0.30)：与已有记忆的最大余弦相似度的补数
- **情绪价值** (0.20)：LLM 输出的情感分析
- **任务相关性** (0.35)：与当前对话目标的余弦相似度（权重最高）
- **重复频率** (0.15)：归一化访问次数

综合分：$I(c) = 0.30 \cdot v_{nov} + 0.20 \cdot |v_{emo}| + 0.35 \cdot v_{task} + 0.15 \cdot v_{rep}$

### 3. WorkingMemory — 海马体模拟
容量限制 **7 项**（[[working-memory|Miller 定律]]）。FIFO 置换。制造**记忆压力**迫使系统巩固。

### 4. LongTermMemory — 新皮层模拟
NetworkX 有向图。节点=概念，边=类型化关系。三路检索融合：语义搜索 + 图遍历 + 重要性排序。SQLite 持久化。

### 5. SleepCycle — 核心创新

**触发条件**（满足任一）：
- 记忆熵 > 0.9（Shannon 熵）
- 冲突密度 > 0.3（`contradicts` 边占比）
- 超过 1 小时未整理
- 手动触发

**NREM 巩固**（慢波睡眠模拟）：
- 重播工作记忆中的 episode
- [[hebbian-learning|Hebbian 强化]]：共同出现的高价值概念之间连接增强
- 突触下调：所有连接强度乘以 α=0.8（每周期衰减 20%）

**REM 做梦**（快速眼动睡眠模拟）：
- 从高重要性节点出发做**随机游走**（长度 5，seed k=3）
- 转移概率正比于边的连接强度
- 非矛盾的路径被整合为新的 `related_to` 边
- **功能**：产生原始输入中不存在的跨概念联想

**主动遗忘**：
- 保持分数 S(c) = 0.8·I(c) + 0.2·(1−e^{−0.01·Δt})
- 自适应阈值：μ_I − σ_I · (图大小/目标大小)
- 低于阈值的概念被从图中剪枝

## 自我模型 (Self-Model)

SCM 维护一个**元认知层**——追踪自身的记忆状态：
- 工作记忆负载（当前项/7）
- 长期记忆图统计（节点数、边密度、熵）
- 睡眠周期历史（上次触发、巩固效果）
- 检索置信度估计

## 评估结果

| 指标 | 结果 |
|---|---|
| 10 轮对话事实召回 | **22/22 (100%)** |
| 记忆噪声消除 | **90.9%** (45/50 噪声概念被剪枝) |
| 图大小缩减 | **3×** (72→24 概念) |
| 搜索延迟 (360 概念) | **< 1ms** |
| 基准测试 (8 项) | **全部 1.00** |

## 技术栈

全部可本地运行：
- Llama 3.2 (2B, Q4_K_M) via Ollama
- all-MiniLM-L6-v2 (sentence-transformers)
- NetworkX + SQLite
- Python

## 与 Hermes 的对比启示

SCM 的每个模块都可以映射到 Hermes 的现有/可扩展组件：

| SCM 模块 | Hermes 对应 | 差距 |
|---|---|---|
| WorkingMemory | Context Window | Hermes 无 7 项硬限制 |
| LongTermMemory | Hindsight + Memory | Hindsight 有语义检索但无图结构 |
| SleepCycle | Cron Job (可实现) | **当前不存在** |
| ValueTagger | ❌ | 无多维重要性评分 |
| Self-Model | ❌ | 无元认知层 |
| MeaningEncoder | ❌ | 无主动概念提取 |

→ 最具可行性的改进：用 Cron Job 实现定时"睡眠周期"，扫描 sessions + Hindsight 巩固 + Memory 压缩/遗忘。

## 局限性

- 仅在合成基准上评估，未经真实部署验证
- 多 Agent 同步已描述但未基准测试
- 代码未开源（计划同行评审后发布）
- 遗忘阈值手动调参，非自动学习

## References

- [[scm-sleep-consolidated-memory]] (source)
- [[memory-consolidation]]
- [[forgetting-mechanisms]]
- [[ai-agent-memory]]
- [[complementary-learning-systems]]
- [[human-memory-systems]]
- [[hermes-sleep-implementation-plan]] — Hermes 落地方案
- [[ai-sleep-memory-research-survey]] — 完整调研综述
- [[letta-sleep-time-compute]]
- [[catastrophic-forgetting]]
- [[generative-agents]]
