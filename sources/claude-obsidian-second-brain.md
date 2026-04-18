---
title: "Claude + Obsidian have to be illegal"
author: "@defileo"
date_ingested: 2026-04-11
date_published: 2026-04-09
tags: [ai, obsidian, claude-code, productivity, knowledge-management]
url: "https://x.com/defileo/status/2042241063612502162"
type: twitter-thread
---

# Claude + Obsidian have to be illegal

## 核心论点

用 Claude Code + Obsidian 搭建 LLM Wiki 模式的"第二大脑"，让 LLM 负责所有知识维护工作，人类只负责策展和提问。

## 方案来源

基于 [[andrej-karpathy]] 的 LLM Wiki 模式。

## 三层架构
- **Raw Sources**: 不可变的原始资料
- **Wiki**: LLM 生成维护的 Markdown 页面
- **Schema**: CLAUDE.md 配置文件

## 三种操作
- **Ingest**: 添加新资料，LLM 自动提取、摘要、交叉引用（一个来源可触及 10-15 页面）
- **Query**: 向 wiki 提问，好的回答存回 wiki
- **Lint**: 定期健康检查，发现矛盾、孤立页面、过时内容

## 实用命令示例
- 摄入文章并更新 wiki
- 每周 lint 检查生成健康报告
- 早晨自动 briefing 脚本（cron job）
- 处理会议记录自动归档

## 核心洞察

> "你甚至不需要打开 Obsidian。Claude Code 指向文件夹，在终端工作，第二大脑在后台自动构建。Obsidian 只是你想看看里面有什么时的窗口。"

> "人类的工作是策展来源、提出好问题、思考这一切意味着什么。Claude 的工作是其他所有事情。"

## 相关页面
- [[llm-wiki-pattern]]
- [[andrej-karpathy]]
- [[knowledge-management]]
