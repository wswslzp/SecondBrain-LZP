---
title: "模型蒸馏（Distillation）"
tags: [ai, training, architecture, diffusion]
date_created: 2026-04-18
date_modified: 2026-10-29
related: ["[[visual-intelligence]]", "[[open-weights-strategy]]", "[[andreas-blattmann]]", "[[gpt-6-astra]]", "[[huazhe-xu]]", "[[zheqing-zhu]]", "[[sheng-wang]]", "[[wet-lab-verification-loop]]", "[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]"]
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

## 人类数据蒸馏的三重视角：普通人还有“被蒸馏”的价值吗？（硅谷101 E256，2026-10-20）

在《硅谷101》E256 期（[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]）中，针对前沿实验室研究员“训练信号转向专家数据与可验证环境后，普通人已失去被大模型蒸馏价值”的观点，三位嘉宾将“蒸馏”的概念从模型间压缩扩展到了**“从人类向 AI 提取知识与直觉”**：

1. **具身机器人视角（[[huazhe-xu|许华哲]]）：人人皆是生活专家**：在机器人领域，做家常菜、叠衣服、走路都是高价值数据，每个普通人在未来 1–2 年内都极具被蒸馏价值，远未到只需蒸馏米其林大厨（Gordon Ramsay）的阶段；同时机器人数据标注正从“卖生肉”转向提取人类操作成败背后的**物理因果与直觉物理**（“熟肉”单价翻 10 倍）。
2. **科学探索视角（[[sheng-wang|王晟]]）：双向/反向蒸馏与定义问题**：跨学科科学家每天都在**“反向蒸馏 AI”**以快速获取陌生领域知识；而人类永远保有**“定义新问题”**（如抗衰老活到 200 岁、个体化疾病诉求）与重大医疗决策背书的不可替代价值。
3. **强化学习视角（[[zheqing-zhu|朱哲清]]）：蒸馏“如何从零学习”而非表层技能**：当前大模型只是死记硬背并在特定场景上过拟合（Overfit）；未来真正需要从人类身上蒸馏的，是**人类如何用极少样本从零开始快速学会一个新领域的底层学习方法与直觉（Intuition）**。

## 来源
- [[cs153-bfl-andreas-blattmann]]
- [[silicon-valley-101-gpt6-astra-agent-robotics-pharma]] — 《硅谷101》E256 Agent、机器人与制药，谁先被GPT-6 Astra改写？（2026-10-20）
