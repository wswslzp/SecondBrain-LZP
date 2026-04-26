---
title: "ImageBind — 六模态统一嵌入"
tags: [imagebind, meta-ai, multimodal, embedding]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[cross-modal-binding]]", "[[multimodal-memory]]"]
---

# ImageBind (Meta AI)

六模态统一嵌入空间，以图像为锚点模态，CVPR 2023。

## 支持模态

图像 / 文本 / 音频 / 深度 / 热成像 / IMU（惯性测量）

## 核心思路

以**图像为锚点**——因为几乎所有模态都有对应的图像配对数据（音频+视频、文本+图片、深度+图片等），通过图像作为桥梁将所有模态投射到同一嵌入空间。

这类似于大脑以**视觉为空间绑定中心**的机制。

## 能力

- 跨模态检索（用音频搜图片、用文本搜视频等）
- 模态算术（狗的图片 + 海浪的声音 = 海边的狗）
- 零样本识别

## 论文

arXiv:2305.05665

## Sources

- [[multimodal-memory-systems]]
