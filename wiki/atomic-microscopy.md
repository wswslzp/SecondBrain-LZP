---
title: "ATOMIC：AI 控制的光学显微镜"
tags: [ai-for-science, microscopy, sam, materials, agent]
date_created: 2026-10-27
date_modified: 2026-10-27
related: ["[[haozhe-wang]]", "[[2d-semiconductor]]", "[[harry-wang-beyond-silicon-chips]]"]
---

# ATOMIC：AI 控制的光学显微镜

**ATOMIC**（Autonomous Technology for Optical Microscopy & Intelligent Characterization）是杜克大学 [[haozhe-wang|Haozhe "Harry" Wang]] 实验室 2024 年前后发表的 AI 显微镜平台：用大语言模型作为 agent 控制一台现成的光学显微镜，对二维材料做表征与分类（[[harry-wang-beyond-silicon-chips|演讲 source]]）。

## 系统构成

- **LLM agent 控制显微镜**：移动样品台、对焦、调光等基础操作交给模型（论文完成于 agent 概念早期，当时只敢自称"工作流"）。
- **Meta SAM**：对拍到的显微图像做分割，识别薄片、缺陷区域等离散对象。
- **无监督聚类**：判断材料状态——单层/多层/裸硅/空白。"别忘了机器学习是 AI 的起点。"

## 关键特性与结果

- **零训练**：不建数据中心、不做微调，搭好智能体系统 + 写好提示词即可用。
- 与受过训练的人眼相比，识别准确率 **99.7%**；主要代价曾是约 6 秒延迟（演讲时称已大幅降低）。
- 部分任务反超人类：让人标注所有 MoS₂ 薄片，人只标出显眼区域，模型能**逐像素**发现人眼忽略的**畴界**（domain boundary，晶畴间边界，本身也是一种缺陷）。
- 跨材料泛化：石墨烯及多种二维半导体上表现一致良好。
- 公开报道补充：在过曝、失焦、弱光等不完美成像条件下仍保持性能，有时能发现人眼不可见的缺陷。

## 意义

把"良率管理仍靠人看材料"这一半导体行业的现实瓶颈，变成了 AI 可自动化的第一环——是 [[2d-semiconductor]] 材料路线从实验室走向 fab 的"看"这一步，也是后续"AI 做实验"与"AI 造芯"工作的基座。

## References

- Duke Pratt School：Duke Engineers Build AI Optical Microscope for Materials Research
- [[harry-wang-beyond-silicon-chips]]（硅谷101 Alignment 2026 Keynote）
