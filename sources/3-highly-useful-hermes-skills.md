---
title: "3 Highly Useful Hermes Skills"
author: "0xJeff"
date_ingested: 2026-04-20
date_published: 2026-04-20
tags: [ai-agents, hermes, productivity, automation, personal-knowledge-management]
url: "https://x.com/0xJeff/status/2046164193326628880"
---

# 3 Highly Useful Hermes Skills

## Summary

0xJeff 分享了他使用 Hermes AI agent 的三个核心用例和经验教训。Hermes 的核心优势在于**自我学习**（自动创建 skills）和**自我记忆**（跨 session 保留上下文），但随着 skills 和 cron jobs 增多，维护复杂度也会快速上升。

## Key Takeaways

### 三大用例

1. **Fetch & Analyze X insights** — 每日早晨通过 cron job 抓取 X 上关于宏观、地缘政治、科技、AI 的洞察
   - 教训：Bird CLI 有写权限，会导致 hallucination 发推。改用官方 X API（$0.5/天）更安全

2. **Breaks down X bookmarks** — 自动从每日 10-20 个书签中筛选 15 个，按优先级排序并摘要
   - X API v2 无法读取 X articles，需配合 [[browser-harness]] 爬取全文
   - 工作流：X API → Browser → LLM → wiki 存储

3. **Reflect** — 综合历史信息、偏好、关系，检测模式，产出 Top 5 Daily Insights
   - 依赖外部 memory provider，作者推荐 [[hindsight]]（recall accuracy 第一）

### 实用工具

- **last30dayskill**: 获取 X/TikTok/IG/Reddit 近 30 天活动（无需 API）
- **Coingecko & Defillama**: 实时市场数据
- **delegate task**: 适合长运行任务
- **Opencode Go**: $5/月入门，inference 额度充足

### 教训与警告

- ⚠️ Bird CLI 默认有写权限，需手动禁用或改用 X API
- ⚠️ Hindsight + Openrouter + Claude Sonnet 4.6 = $50+/天 token burn
- ⚠️ Browser Harness 需隔离浏览器，不暴露敏感凭证
- 💰 Token 管理是长期使用 AI agent 的核心挑战
- 💰 Claude 快但贵，开源模型性价比更高

### 下一步计划

- **Pre-call context**: 通话前 30-60 分钟自动整理对方项目/团队信息
- **Prediction markets**: 低风险复利策略，优化 DeFi lending R/R

## Connections

- [[llm-wiki-pattern]] — Hermes 的 wiki 存储与 Karpathy 的 LLM Wiki 模式同源
- [[ai-for-learning]] — 0xJeff 的核心目标是 accelerate/augment learning
- [[vibe-coding]] — Claude Code 用于 one-off 任务（dashboards, travel sites）

## Original

[[raw/3 Highly Useful Hermes Skills - 0xJeff.md|原文]]
