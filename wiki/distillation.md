---
title: "模型蒸馏（Distillation）"
tags: [ai, training, architecture, diffusion]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[visual-intelligence]]", "[[open-weights-strategy]]", "[[andreas-blattmann]]"]
---

# 模型蒸馏

把一个大/慢模型的能力压缩到一个小/快模型。BFL 的核心技术优势之一。

## 两种蒸馏维度

### 大小蒸馏（Size）
- 大模型 → 小模型
- 常见于 LLM（Claude Opus/Sonnet/Haiku）
- 参数量减少

### 步数蒸馏（Steps）
- 同样大小的模型
- 推理步数减少（如 50 步 → 4 步 → 1 步）
- **diffusion 模型独有的优势**（LLM 无法类似操作）

## Latent Adversarial Distillation（BFL）

BFL 的关键技术，对业务和技术双重 unlock。

### 技术贡献
- 把 flow matching / diffusion 模型的 50 步蒸馏到 4 步、2 步
- 质量几乎无损
- **Pipeline 更稳定成熟**（比直接训练 1-step 模型好）

### 业务 unlock
**Flux 三包**（见 [[open-weights-strategy]]）：
- Flux Schnell：同样大小，蒸馏到 ~4 步（开源）
- Flux Dev：中间（开源 + 许可）
- Flux Pro：多步、高质量（API）

让 BFL 既服务开源社区（要快）又服务企业（要质量），同时保持商业可持续。

## Diffusion vs LLM 的蒸馏对比

### Diffusion（可步数蒸馏）
- Iterative 方向正交于数据（artificial time axis）
- 可以把多步轨迹学到一步内
- 用 adversarial loss 确保 1-step 输出与多步等效

### LLM（难步数蒸馏）
- Iterative 方向沿着数据（token by token）
- 有些技巧如 speculative decoding
- 但无法简单"跳过"token 生成

## GAN 在蒸馏中的回归

> "We still use GANs quite a lot, particularly in distillation networks." — Blattmann

虽然 GAN 主流地位被 diffusion 取代（2017-2022 的 StyleGAN 时代），在以下场景仍有用：
- Distillation networks
- 实时系统
- 对抗性 loss 帮助 1-step 模型匹配多步输出

但 GAN 的缺点：
- 不可预测（研究者不喜欢）
- 不像 transformer 那样 scale

## 关键引语

> "For flow matching type models, you can actually distill a model down. We've written papers on adversarial diffusion distillation where you get from 50 steps to 4 or 2." — Blattmann

> "In language models you have to generate token by token—there are some hacks like speculative decoding, but essentially you still cannot just skip." — Blattmann

## 来源
- [[cs153-bfl-andreas-blattmann]]
