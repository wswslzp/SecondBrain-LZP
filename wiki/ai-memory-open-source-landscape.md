---
title: "AI Memory Open Source Landscape — 开源记忆系统全景"
tags: [ai-memory, open-source, tools, agent-memory]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[memory-system-architecture]]", "[[ai-memory-taxonomy]]", "[[ai-agent-memory]]", "[[memos-memory-os]]", "[[hindsight]]"]
---

# AI Memory Open Source Landscape

AI 记忆领域开源项目全景图，截至 2026 年 4 月共 43 个活跃项目。

## 时间线演化

```
2023 ──────── 2024 ──────── 2025 ──────── 2026 ────→
│              │              │              │
│ Zep          │ Mem0         │ LangMem      │ MAGMA
│ AgentMemory  │ Supermemory  │ A-Mem        │ MemClaw
│ Cognee       │ Memary       │ MemEngine    │ SwarmVault
│ Letta(MemGPT)│ Memobase     │ MemOS        │ SkillClaw
│              │ Second-Me    │ Hindsight    │ ToolPipe
│              │              │ ReMe         │
│              │              │ EverMemOS    │
│              │              │ MineContext  │
```

## 第一代（2023）：探索期

| 项目 | 特点 |
|------|------|
| **Zep** | 最早的独立记忆服务，对话历史 + 摘要 |
| **Letta/MemGPT** | 首个将记忆管理比喻为操作系统的框架 |
| **Cognee** | 知识图谱驱动的记忆 |

## 第二代（2024）：产品化

| 项目 | 特点 |
|------|------|
| **Mem0** | "记忆层即服务"，嵌入任何 LLM 应用 |
| **Second-Me** | 个人 AI 分身，学习用户行为模式 |
| **Memobase** | 用户画像提取 + 可配置记忆策略 |

## 第三代（2025）：系统化

| 项目 | 特点 |
|------|------|
| **LangMem** | LangChain 生态的记忆模块 |
| **A-Mem** | Agentic Memory — 自主管理记忆的 Agent |
| **[[memos-memory-os]]** | MemCube 统一三种记忆形式（明文/激活/参数）|
| **[[hindsight]]** | 语义搜索 + 实体图 + 重排序 |
| **MemEngine** | 可插拔记忆引擎，支持多种后端 |
| **MineContext** | 字节跳动火山引擎出品，企业级 |
| **EverMemOS** | 永久记忆操作系统 |

## 第四代（2026）：融合与专业化

| 项目 | 特点 |
|------|------|
| **MAGMA** | 多 Agent 记忆协作 |
| **MemClaw** | 基于 OpenClaw 的记忆爪 |
| **SwarmVault** | Swarm Intelligence + 记忆保险库 |
| **SkillClaw** | 技能记忆蒸馏 → 可复用工具 |
| **ToolPipe** | MCP Server 形式的记忆管道 |

## 架构对比

| 项目 | 存储 | 检索 | 遗忘 | 多模态 | MCP |
|------|------|------|------|--------|-----|
| Letta | 分层 | 语义 | ✗ | ✗ | ✗ |
| Mem0 | 向量 | 混合 | ✗ | ✗ | ✗ |
| MemOS | 统一三层 | 多策略 | ✓ | ✗ | ✗ |
| Hindsight | 向量+图 | 语义+实体+重排 | ✗ | ✗ | ✓ |
| A-Mem | 自适应 | Agent驱动 | ✓ | ✗ | ✗ |
| EverMemOS | 持久 | 多模态 | ✓ | ✓ | ✗ |

## 与 Hermes 的关系

Hermes Agent 目前使用：
- **[[hindsight]]** 作为外部记忆 provider（recall accuracy 优先）
- **Memory** 作为轻量级键值对（2200 字符上限）
- **Skills** 作为程序记忆
- **Session Search** 作为情景记忆检索

参见 [[ai-agent-memory]] 了解改进方向。

## References

- [[awesome-ai-memory]]
- [[ai-agent-memory]]
- [[memos-memory-os]]
- [[hindsight]]
