---
title: "Memory Consolidation"
tags: [neuroscience, memory, hippocampus, sleep]
date_created: 2026-04-25
date_modified: 2026-04-25
related: ["[[human-memory-systems]]", "[[forgetting-mechanisms]]", "[[ai-agent-memory]]"]
---

# Memory Consolidation

记忆不是一次写入就完成的，需要持续的**后台加工**才能从临时状态转为永久存储。

## 两阶段巩固

### 突触巩固 (Synaptic Consolidation)
- 编码后**数小时**内发生
- 通过长时程增强 (LTP) 强化突触连接
- 依赖蛋白质合成

### 系统巩固 (Systems Consolidation)
- **数天到数年**的时间尺度
- 海马体 (Hippocampus) 中的记忆逐渐"教给"新皮层 (Neocortex)
- 睡眠中的记忆重播 (replay) 是关键机制

## 睡眠的角色

| 睡眠阶段 | 巩固类型 | 机制 |
|---|---|---|
| 慢波睡眠 (SWS) | 陈述性记忆 | 海马体-新皮层对话 |
| REM 睡眠 | 程序性+情绪记忆 | 突触可塑性重组 |
| 睡眠纺锤波 | 记忆整合 | 协调信息传递 |

## 再巩固 (Reconsolidation)

**关键发现** (Nader et al., 2000)：
- 回忆/激活一段记忆时，它会暂时变得**不稳定**（~6小时窗口）
- 在此期间可以被修改、增强或削弱
- 然后重新稳定存储
- **临床应用**: PTSD 治疗——回忆创伤时干预可减弱情绪强度

## AI Agent 启示

AI Agent 缺少"离线巩固"过程。可能的实现：
- 定时后台任务扫描近期 sessions
- 提取高频模式为持久知识
- 类似"睡眠巩固"的周期性记忆整理

## References

- [[human-memory-cognitive-science]]
