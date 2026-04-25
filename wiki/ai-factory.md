---
title: "AI Factory（前沿 AI 制造管线）"
tags: [ai, training, infrastructure, post-training]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[frontier-systems]]", "[[context-feedback-loops]]", "[[unified-models]]"]
---

# AI Factory

[[anjney-midha]] 在 CS 153 反复强调的前沿 AI 制造模板。每个前沿 lab（Anthropic、BFL、Luma、ElevenLabs、Periodic Labs）都在运行这个基本管线的变体。

## 基本模板

```
[Pre-training]      大规模、通用、多模态
     ↓
[Mid-training]      添加能力、高分辨率、新任务
     ↓
[Post-training]     对齐、蒸馏、客户反馈、人工标注
     ↓
[Deployment + RL]   实时交互、持续学习
     ↓
(反馈回流 → pre-training/post-training)
```

## 各阶段详解

### Pre-training
- **数据大**，质量可变——可以自动标注
- 目标：获得通用的自然表征
- Luma：30PB，~100K H100/GB300
- 多模态：图像、视频、音频联合训练
- 用 [[distillation]] 和架构如 Self Flow 实现对齐

### Mid-training
- 数据量减少，质量提升
- 添加新任务/能力（高分辨率、image editing、action prediction、computer use）
- 条件化：在 audio+image 条件下预测"用这个声音说这句话"

### Post-training（离线）
- **蒸馏**让模型更高效（[[distillation]]）
- 根据团队对客户需求的直觉进行对齐
- 人工标注员（trainers、tutors、labelers）的角色至关重要
- 这是一个 frontier lab 看起来完整的关键

### Post-training（在线）
- 将模型部署到实际 context
- 收集**交互数据**（不只是像素——还有轨迹、偏好、失败模式）
- 对于机器人/robotics：连接物理世界，产生可验证反馈

### RL & 持续学习
- RLHF（最早的形式）
- 现在发展到"continuous post-training"
- 消耗近一半的 compute（[[frontier-systems]]）

## 三个实例

### Anthropic（代码）
- Context：monorepo、git history、IDE 文件
- 反馈：单元测试通过/失败
- 结果：代码能力随 compute 可预测扩展

### BFL（图像 → 多模态）
- Flux 1：text-to-image pre-training
- Flux Context：用户反馈驱动添加编辑能力
- 未来：post-training 包含与物理世界的**交互**（不止观察）

### Luma（多模态视频）
- Pre-training：图像 + 视频 + 文本
- Mid-training：添加高分辨率能力
- Post-training：
  - 客户数据（studio 特定）
  - 用户偏好（点赞/下载，过滤 trolling）
  - 人工标注（skills library，如"如何做好幻灯片"的 50 页文档）
- Deployment：agent 框架 + tool calling + continuous RL

### ElevenLabs（语音）
- Pre-training：跨语言音频
- Mid-training：添加情感检测、多语言
- Post-training：企业定制化
- Deployment：cascaded voice agents，收集情感标签数据

## 关键洞察

### 完整的 factory 包含人
> "A frontier lab is not just data, compute, and algorithms. It also has huge parts of what we call skills and trainers and tutors and people doing data labeling." — [[amit-jain]]

没有人工标注/策展层，factory 不完整。

### 产品就是工厂的一部分
> "The product needs to give you enough information to make sure the next model is better than the previous one." — Amit Jain

产品设计本身是 factory 的一部分——它决定了你能收到什么反馈。

### 反馈从像素到轨迹
早期：点赞=好、下载=好
现在：整个 chain of thought、用户如何修改、哪一步失败

## 关键引语

> "A frontier lab has these components of data, compute, and algorithm, but it also has huge parts of skills and trainers and tutors." — Amit Jain

> "Every interaction is learned from—whether they liked it, disliked it, in what way, whether the full chain of work was any good, which elements of that weren't."

## 来源
- [[cs153-luma-amit-jain]]
- [[cs153-bfl-andreas-blattmann]]
- [[cs153-elevenlabs-mati-staniszewski]]
- [[cs153-frontier-systems]]
