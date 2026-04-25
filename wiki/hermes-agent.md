---
title: "Hermes Agent"
tags: [ai-agents, automation, productivity, personal-ai]
date_created: 2026-04-20
date_modified: 2026-04-20
related: ["[[llm-wiki-pattern]]", "[[ai-for-learning]]", "[[vibe-coding]]"]
---

# Hermes Agent

Hermes 是一个**自我学习、自我记忆**的 AI agent 框架，能够持续学习用户偏好、工作流程，并将其转化为可复用的 skills。

## 核心特性

### Self-Learning

Hermes 观察用户的操作模式，**主动**（无需用户指示）将其合成为 skills。随着 skills 积累，agent 对用户偏好的理解越来越精准。

### Self-Remembering

- 内置 memory config
- 支持外部 memory provider（如 [[hindsight]]）
- 跨 session 保留上下文
- 可搜索历史知识库

### Cron Jobs

支持定时任务，常见用例：
- 每日早晨抓取 X insights
- 定时处理书签并生成摘要
- 生成 Daily Reflection 报告

## 典型用例

根据 [[3-highly-useful-hermes-skills|0xJeff 的分享]]：

1. **信息抓取** — 从 X/社交媒体定时获取特定领域洞察
2. **书签管理** — 自动处理、排序、摘要每日书签
3. **Reflect** — 综合历史数据生成个性化洞察
4. **Pre-call context** — 通话前自动整理对方信息

## 工具生态

| 工具 | 用途 | 注意事项 |
|------|------|----------|
| X API | 安全读取 tweets | $0.5/天，权限清晰 |
| Bird CLI | X 操作 | ⚠️ 默认有写权限，易 hallucinate 发推 |
| Browser Harness | 爬取网页/X articles | ⚠️ 需隔离浏览器 |
| Hindsight | 外部 memory provider | ⚠️ 避免连 Openrouter，token 消耗大 |
| last30dayskill | 社交媒体历史数据 | 无需 API |
| Coingecko/Defillama | 实时市场数据 | — |

## 成本与挑战

- **Token 管理**是长期使用的核心挑战
- Claude 快但贵，开源模型性价比更高
- Skills/cron jobs 多了后，配置调整和 debug 复杂度急剧上升
- 作者 2 周花了 $150-200 在 debugging 和测试上

## 入门建议

- Opencode Go 订阅 $5/月入门
- 从简单 skills 开始，逐步扩展
- 严格控制 agent 的写权限
- 隔离浏览器环境，保护敏感凭证

## References

- [[3-highly-useful-hermes-skills]] — 0xJeff 的实战经验分享
