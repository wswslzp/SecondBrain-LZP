---
title: "LLM Inference Systems"
type: concept
tags: [ai, inference, systems, serving]
date_created: 2026-06-01
date_modified: 2026-06-01
related: ["[[compute-infrastructure]]", "[[multi-stage-decode]]", "[[sglang-omni]]"]
---

# LLM Inference Systems

LLM 推理系统负责把模型权重、KV cache、调度器、通信和显存管理组织成可服务多用户请求的在线系统。标准文本 LLM 推理通常由 prefill 与 decode 两个阶段组成：prefill 处理完整 prompt、计算密集；decode 逐 token 生成、受 KV cache 读写和显存带宽约束。

## Core Concepts

- **Prefill** — 一次性处理输入上下文，生成 KV cache，通常 compute-bound。
- **Decode** — 逐 token 生成并更新 KV cache，通常 memory-bound。
- **Continuous batching** — 每一轮 decode 动态合并活跃请求，提高 GPU 利用率。
- **Paged KV cache** — 把 KV cache 切成 page 管理，减少显存碎片和预留浪费。
- **CUDA Graph / kernel launch overhead** — 在单步计算变轻时，kernel 启动和同步开销会成为主瓶颈。

## Why It Matters

推理系统的核心不是“把模型跑起来”，而是识别不同计算阶段的瓶颈，并用相应的调度、缓存、通信和显存策略匹配它们。[[sglang-omni]] 的价值在于把这一原则推广到语音/多模态 multi-stage 推理。

## Sources

- [[sglang-omni-llm-inference]]
