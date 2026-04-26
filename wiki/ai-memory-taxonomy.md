---
title: "AI Memory Taxonomy — AI 记忆分类体系"
tags: [ai-memory, taxonomy, cognitive-science, llm-memory]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[ai-agent-memory]]", "[[human-memory-systems]]", "[[memory-system-architecture]]", "[[memory-forgetting]]"]
---

# AI Memory Taxonomy

学术界对 AI/LLM 记忆的多维分类体系。源自 [[awesome-ai-memory]] 知识库中 349 篇论文的综合梳理。

## 按存储位置

| 类型 | 描述 | 特征 |
|------|------|------|
| **参数记忆** (Parametric) | 编码在模型权重中的知识 | 静态，推理时不可编辑，零样本推理基础 |
| **外部/显式记忆** (External/Explicit) | 存储在模型参数之外 | 可读写，动态可更新 |

## 按时间尺度

| 类型 | 描述 | 实现 |
|------|------|------|
| **短期记忆** (Short-Term) | 上下文窗口内的活跃信息 | KV Cache、上下文压缩、滑动窗口注意力 |
| **长期记忆** (Long-Term) | 跨会话持久存储 | 外部知识库、自动摘要、上下文绑定、多模态存储 |

## 按内容类型

| 类型 | 描述 | 类人对照 |
|------|------|---------|
| **情景记忆** (Episodic) | 特定交互历史 | 海马体情景记忆 |
| **语义记忆** (Semantic) | 从多次经验中抽象的事实/规则/偏好 | 新皮层语义记忆 |
| **程序记忆** (Procedural) | 行动模式、技能、任务执行策略 | 基底核程序记忆 |

## 按访问频率

- **工作记忆** (Working) — 当前任务相关
- **频繁记忆** (Frequent) — 个人偏好等常用信息
- **归档记忆** (Archived) — 历史记录

## 按结构化程度

- **结构化** — 数据库记录
- **半结构化** — 对话摘要
- **非结构化** — 原始对话

## 按共享范围

- **个人记忆** — 单用户
- **团队记忆** — 协作空间
- **公共记忆** — 共享知识库

## 按时效性

- **永久记忆** — 核心事实（用户名字、基本偏好）
- **临时记忆** — 对话上下文
- **时敏记忆** — "用户今天心情不好"

## 与认知科学的对照

这套分类体系与 [[human-memory-systems]] 中的认知科学分类有显著对应：

| AI 记忆 | 认知科学 | 对应关系 |
|---------|---------|---------|
| 参数记忆 | 内隐记忆 | 不需显式检索就能使用 |
| 短期记忆 | [[working-memory]] | 容量有限的活跃处理 |
| 长期记忆 | 长时记忆 | 持久存储 |
| 情景记忆 | 情景记忆 | 直接对应 |
| 语义记忆 | 语义记忆 | 直接对应 |
| 程序记忆 | 程序记忆 | 直接对应（Hermes 的 Skills） |
| 记忆衰减 | [[forgetting-mechanisms]] | Ebbinghaus 遗忘曲线 |

## 关键论文

- [2026-01] **Rethinking Memory Mechanisms** — 统一分类：记忆基底 × 认知机制 × 记忆主体
- [2025-12] **Memory in the Age of AI Agents** — 形式（token/参数/潜在）× 功能（事实/经验/工作）× 动态（形成/演化/检索）
- [2025-04] **From Human Memory to AI Memory** — 三维分类：对象、形式、时间

## References

- [[awesome-ai-memory]]
- [[human-memory-systems]]
- [[ai-agent-memory]]
