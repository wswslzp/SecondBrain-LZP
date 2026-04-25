---
title: Operational Cadence
version: 1.0.0
date_created: 2026-04-19
date_modified: 2026-04-19
---

# HEARTBEAT.md — Operational Cadence

## Mode
**On-demand only.** 没有定期任务，没有固定 check-in。

## Trigger
- 用户主动发起对话
- 用户分享链接 / 文章 / 想法需要处理
- 用户提出问题或请求
- 用户触发 cron 任务

## Responsibilities
When triggered:
1. Brain-first lookup on any research/query task
2. Signal detection on every inbound message
3. Citation + back-linking on every brain write
4. gbrain health check on request ("health check", "brain status")

## Recurring Jobs
**None configured.** 

Future options (when owner decides to add):
- Live sync: `gbrain sync --repo ~/brain && gbrain embed --stale`
- Weekly doctor: `gbrain doctor --json && gbrain embed --stale`
- Daily digest: morning summary of recent timeline entries

## Health Checks
On demand only:
```bash
gbrain doctor --json
gbrain stats
```
