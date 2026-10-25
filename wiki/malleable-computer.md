---
title: "可塑的计算机（Malleable Computer）"
tags: [ai-agents, operating-system, linux, end-user-programming, concept]
date_created: 2026-10-25
date_modified: 2026-10-25
related: ["[[omarchy]]", "[[dhh]]", "[[vibe-coding]]", "[[claude-code]]", "[[openclaw]]"]
---

# 可塑的计算机（Malleable Computer）

这个概念的意思是：当你能 vibe code 任何应用时，也应该能 vibe code 自己的**操作系统**。界面、面板、功能、快捷键都能通过和智能体对话来改。这是 [[dhh|DHH]] 在 [[omarchy|Omarchy]] 上押注的核心，他称之为“智能体化的个人计算机”。

## 为什么是 Linux

- **Unix 哲学正好合智能体的胃口**：一切都是配置文件和 CLI 小工具，智能体可以直接调用和修改。
- **旧缺点变成新优势**：Linux 报错晦涩、配置繁琐，曾是它的主要缺点。现在智能体读过它的全部源码，晦涩的报错反而能帮它精准定位问题。
- **封闭系统的劣势**：macOS 的快捷键和 Raycast 配置无法自动化，安装软件要先过 Apple 的许可；WSL 只是个沙盒。苹果“精心策划的封闭体验”，在智能体时代反而成了负担。
- **上游态度**：Linus Torvalds 表态欢迎 AI 进入内核。不过 DHH 观察到，多数 Linux 和开源社区对 AI 仍持怀疑甚至敌意。

## 与早年“人人编程”承诺的区别

四十多年来，第四代语言、Lisp/Smalltalk、Access/Excel 都承诺过“让普通人自己写程序”，最后都只走到了终端用户编程的层面。Commodore 64 开机就进入 BASIC，本来就是一台可塑的机器，只是当时你得懂“象形文字”。DHH 的说法是，智能体就是那块**罗塞塔石碑**。

## 产品信号

- Omarchy 插件市场三天内出现 330 个插件，很多来自非传统程序员。
- 用户用大白话描述 20 分钟，就能把系统改成自己想要的样子。DHH 把这种情绪高涨的反馈视为产品市场契合的信号。
- 延伸设想：像 Jarvis 那样完全靠语音操作；像实时生成画面的游戏模型那样实时改变界面；手机也要变得可塑（例如 Omarchy mobile）。

## 风险与边界

- **代码库会腐化**：可塑性越强，越需要有人把关架构。Basecamp 5 中设计师 vibe 出来的 PR 就毁过一次架构（见 [[vibe-coding]]）。
- **执行要隔离**：智能体能改系统，就需要隔离执行和受控权限（见 [[agent-runtime-security]]）。
- **生活领域的担忧**：有用户把智能体接入健康数据和特斯拉后，车被擅自改道去了超市。DHH 认为把可塑性扩展到全部生活很有“黑镜”感，也因此对 [[openclaw|OpenClaw]] 式的全面托管保持距离。

## References

- [[dhh-lex-fridman]] — Lex Fridman #501
