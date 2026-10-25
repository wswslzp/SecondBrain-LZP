---
title: "Omarchy"
tags: [linux, operating-system, arch-linux, ai-agents, open-source, dhh]
date_created: 2026-10-25
date_modified: 2026-10-25
related: ["[[dhh]]", "[[malleable-computer]]", "[[claude-code]]", "[[dhh-lex-fridman]]"]
---

# Omarchy

[[dhh|DHH]] 主导的 Linux 桌面发行版。它基于 Arch Linux，以 Hyprland（Wayland 平铺合成器）为核心，取向非常鲜明。名字里的 “Oma” 来自 **omakase（主厨精选）**：预装哪些软件由作者决定。

## 演进

| 版本 | 要点（DHH 口述） |
|---|---|
| Omakub | 前身，基于 Ubuntu，采用传统桌面形态，社区只有几千人 |
| Omarchy 1–3 | 2025 年夏在勒芒期间开始做。从 Arch 起步，“往下深了七层”；早期 Bash 脚本是手写的，后来部分由智能体加速；平铺窗口管理器反而带来了更强的吸引力 |
| **Quattro（4）** | 约三个月开发，2026 年 8 月发布。新代码 100% 由智能体编写，合并了 1000 多个 PR，发布后数万次下载 |

## 智能体优先的特性（Quattro）

- **插件和 skills**：系统附带 skills，教你带来的任何智能体如何扩展操作系统的界面、面板和功能。插件市场三天内出现 330 个插件。
- **Crash watcher**：应用崩溃时，会询问是否让 AI 诊断。智能体会翻日志、拉源码、定位到具体代码行，再生成 bug 报告。
- **默认智能体**：首次启动时会提示设置。如果关掉提示，这些 AI 功能就都不会启用，系统仍然可以完全手工使用。
- **工具链**：用 mise 管理一天更新好几次的智能体 CLI；内置 ChatGPT/Codex、Claude 等 harness 的一键安装；计划支持多订阅切换。
- **自带应用**：Omawrite（C++/Qt 的 Markdown 写作器，用来替代 Typora）、Omacut（纯键盘剪片工具）、TTFX（用 Rust 重写的终端特效屏保，比原版 Python TTE 快约 46 倍）、Voxtype 听写（可选安装）。

## 安装速度执念

目标从 15 分钟一路压到 2 分钟、1 分钟，当前纪录是 **45 秒**；Dell XPS 专用 turbo 镜像的目标是约 12 秒。手段包括：利用用户回答问题的时间在后台预加载，把镜像从 7.5GB 压到约 5.85GB（精简 JetBrains 字体包、NVIDIA 驱动改用 zstd 最高压缩级别）。DHH 拿来对比的是新 Mac 开箱要 42 分钟、预装 Windows 的 PC 要 1 小时 35 分。

## 定位与争议

- **不做“仿 Windows/Mac”**：它的卖点是可塑性，而不是熟悉感（见 [[malleable-computer]]）。
- **与 Arch 社区的关系**：两者共享技术底座，但目标相反。Arch 社区偏好一切自己动手，Omarchy 是开箱即用的“主厨精选”。
- **愿景**：做 Omarchy 手机版（基于 Android 分支）。

## References

- [[dhh-lex-fridman]] — Lex Fridman #501
