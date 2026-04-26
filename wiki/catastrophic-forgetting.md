---
title: "灾难性遗忘"
type: concept
aliases:
  - Catastrophic Forgetting
  - 灾难性遗忘
  - Catastrophic Interference
created: 2026-04-26
---

## Overview

灾难性遗忘（Catastrophic Forgetting）是神经网络持续学习中的核心问题：网络学习新任务时会急剧丧失已学任务的性能。这源于神经网络的参数共享特性——新任务的梯度更新会覆盖旧任务中学到的权重。

### 与睡眠的关系

人类大脑通过睡眠中的记忆重播（memory replay）机制天然解决了这个问题。受此启发，多种"睡眠式"训练方法被提出：

- **SRC**（Sleep Replay Consolidation）：无监督睡眠重播算法
- **SIESTA**（TMLR 2023）：Wake/Sleep 双阶段框架，ImageNet-1K 上匹配离线学习器
- **WSCL**：Wake/NREM/REM 三阶段，基于 [[complementary-learning-systems]] 理论
- **Dream2Learn**（2026）：用扩散模型生成"梦境"做前向迁移

### 理论基础

核心理论框架是 McClelland et al. (1995) 的**互补学习系统理论** (CLS)——大脑用两个互补的学习系统避免灾难性遗忘：
- **海马体**（快速学习，高保真，稀疏表征）
- **新皮层**（慢速学习，强泛化，分布式表征）
- 睡眠重播负责将知识从海马体转移到新皮层

## Sources

- [[ai-sleep-memory-research-survey]]

## Related

- [[complementary-learning-systems]]
- [[memory-consolidation]]
- [[sleep-consolidated-memory]]
- [[human-memory-systems]]
