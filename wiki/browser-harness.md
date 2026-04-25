---
title: "Browser Harness"
tags: [tools, browser-automation, ai-agents, web-scraping]
date_created: 2026-04-20
date_modified: 2026-04-20
related: ["[[hermes-agent]]", "[[vibe-coding]]"]
---

# Browser Harness

By Gregor Zunic (@gregpr07), released April 19, 2026.

## What is it?

A **self-healing harness** that can complete virtually any browser task. 与传统浏览器自动化框架的根本区别：**移除了限制 LLM 的框架层**。

## Features

- **Self-healing** — 运行时动态修改 `helpers.py`
- **Direct CDP** — 一个 websocket 直连 Chrome
- **No framework restrictions** — LLM 自由操作浏览器

## Use Cases

在 [[hermes-agent]] 生态中：

1. **爬取 X articles** — X API v2 无法读取长文，Browser Harness 可以直接点击进入并提取全文
2. **动态网页交互** — 像人一样点击、滚动、填表
3. **Debug 自己** — 遇到问题时自动调整策略

## Typical Workflow

```
X API → fetch bookmarks list with tweet text + linked URLs
Browser Harness → navigate to each article URL → extract full text
LLM → summarize each article
Output → daily report & store insights in wiki
```

## ⚠️ Security Warnings

> If you're using Browser Harness, practice extreme cautions.

- 使用**隔离/全新浏览器**
- **不要**共享敏感凭证
- **不要**让它随意浏览互联网

Browser Harness 的强大能力也意味着风险 — 它能做的事情几乎没有限制。

## Stats (Apr 19, 2026)

- 143 replies, 299 reposts, 3.1K likes, 5.9K bookmarks, 734K views

## References

- [[3-highly-useful-hermes-skills]] — 0xJeff 的实战应用
- [Original Tweet](https://x.com/gregpr07/status/2045566281991311483)
