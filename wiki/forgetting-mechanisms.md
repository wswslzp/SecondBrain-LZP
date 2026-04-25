---
title: "Forgetting Mechanisms"
tags: [cognitive-science, memory, forgetting, ebbinghaus]
date_created: 2026-04-25
date_modified: 2026-04-25
related: ["[[human-memory-systems]]", "[[memory-consolidation]]", "[[ai-agent-memory]]"]
---

# Forgetting Mechanisms

遗忘不是记忆系统的缺陷，而是优化认知资源的**功能性机制**。

## Ebbinghaus 遗忘曲线 (1885)

Hermann Ebbinghaus 用无意义音节进行自我实验，发现遗忘呈**指数衰减**：

- 20分钟：保留 58%
- 1小时：保留 44%
- 1天：保留 34%
- 31天：保留 21%

2015年 Murre & Dros 复现实验，结果高度一致。

## 四种遗忘理论

| 理论 | 机制 | 现代评价 |
|---|---|---|
| **衰减理论** (Decay) | 记忆痕迹随时间自然退化 | 单独不足以解释所有遗忘 |
| **干扰理论** (Interference) | 新旧记忆互相竞争干扰 | 主流理论之一 |
| **提取失败** (Retrieval Failure) | 信息仍在但缺少提取线索 | Tulving 编码特异性原则 |
| **动机性遗忘** (Motivated) | 主动压抑不愉快记忆 | 争议较大但有实验证据 |

干扰的两个方向：
- **前摄干扰**: 旧→干扰→新（学法语后学西班牙语容易混）
- **后摄干扰**: 新→干扰→旧（新地址覆盖旧地址记忆）

## 对抗遗忘

- **间隔重复** (Spaced Repetition) — SuperMemo/Anki
- **提取练习** (Retrieval Practice) — 主动回忆 > 被动重读
- **精细编码** — 关联已有知识
- **情绪加权** — 有意义的信息更持久

## AI Agent 启示

当前 AI Agent 最大缺失之一是**没有遗忘机制**。可借鉴方向：
- 给记忆加时间戳+访问计数，低频记忆自动降权
- 模拟干扰效应：新信息更新旧信息时主动替换

## References

- [[human-memory-cognitive-science]]
