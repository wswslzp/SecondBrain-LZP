---
title: "LLM 推理是怎么跑的：跟着 SGLang Omni 团队的设计思路走一遍"
author: "鸭哥每日手记 / Superlinear Academy"
date_ingested: 2026-06-01
date_published: 2026-05-30
tags: [ai, llm-inference, sglang, multimodal-ai, speech-ai, systems]
url: "https://yage.ai/share/sglang-omni-llm-inference-20260530.html"
type: article
---

# LLM 推理是怎么跑的：跟着 SGLang Omni 团队的设计思路走一遍

## Summary

这篇文章以 SGLang Omni 为线索，解释标准 LLM 推理中的 prefill/decode、continuous batching 与 paged KV cache，再进一步分析语音输出如何把推理系统从同构 decode 扩展成 multi-stage decode。它真正有价值的地方不是某个单点技术，而是把系统团队的决策链路公开：按计算特性定义边界，逐 stage 分析瓶颈，再落到调度、通信和显存预算设计。

## Key Points

- 标准 LLM 推理分为 **prefill** 与 **decode**：前者 compute-bound，后者 memory-bound，优化方向完全不同。
- 语音输出需要把波形压缩成 codec token；文本 Thinker 与语音 Talker 的 token 频率、KV cache 行为和同步需求都不同。
- SGLang Omni 不按“模态”分类，而按 decode 是否 **multi-stage** 分类：single-stage 交给 SGLang main，multi-stage 才是 Omni 的目标。
- Multi-stage 带来三类系统问题：异构计算瓶颈、stage 间依赖模式分化、多个模型/encoder/KV cache 争抢显存。
- Talker + MTP 被合并到同一 stage，因为它们是同步紧耦合、每步极轻的反馈回路；stage 边界应由依赖松紧决定，而不是模型模块物理边界。
- 通信层分为控制面（ZMQ 事件通知）和数据面（relay 传大 Tensor，共享内存/CUDA IPC/NCCL），避免用一种机制硬套所有依赖。
- 显存管理从单一 `mem_fraction_static` 变成每个 stage 声明 `total_gpu_memory_fraction` 的多方预算制。

## Concepts

- [[llm-inference-systems]]
- [[multi-stage-decode]]
- [[sglang-omni]]
- [[audio-intelligence]]
- [[cascaded-vs-fused-architectures]]
- [[multimodal-ai]]

## Quotes

> “ML 系统研究者只有一个目标——研究给定计算过程的计算特性，为它设计高效、鲁棒的系统。”

> “Stage 边界不由模型模块的物理边界决定，而由依赖关系的松紧程度决定。”

## Source

- Original: https://yage.ai/share/sglang-omni-llm-inference-20260530.html
- Related project: https://github.com/sgl-project/sglang-omni
