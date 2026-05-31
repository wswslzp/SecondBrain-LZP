---
title: "Multi-stage Decode"
type: concept
tags: [ai, inference, multimodal, speech-ai, systems]
date_created: 2026-06-01
date_modified: 2026-06-01
related: ["[[llm-inference-systems]]", "[[audio-intelligence]]", "[[cascaded-vs-fused-architectures]]", "[[sglang-omni]]"]
---

# Multi-stage Decode

Multi-stage decode 指推理过程不是单一的 prefill → token-by-token decode，而是由多个异构 stage 共同完成，每个 stage 可能有独立权重、KV cache、调度循环和实时依赖关系。语音输出模型常见的 Thinker-Talker 架构就是典型例子。

## Thinker vs Talker

- **Thinker** 生成文本 token，频率低，计算模式接近标准 LLM：prefill compute-bound，decode memory-bound。
- **Talker** 生成 codec token，频率高，每秒可达约 100 token，单步计算轻，容易变成 kernel-launch-bound。
- **MTP** 与 Talker 是同步紧耦合反馈回路：Talker 生成第 0 个 codec token 后，MTP 立刻补全并写回，下一步依赖该结果。

## System Problems

1. **异构计算瓶颈** — compute-bound、memory-bound、kernel-launch-bound 不能用同一个调度策略硬管。
2. **依赖模式分化** — Thinker→Talker 可以异步缓冲，Talker↔MTP 必须极低延迟同步。
3. **显存竞争** — 多个模型、encoder 激活峰值、多个 KV cache pool 和 feedback buffer 同时占用 GPU。

## Design Principle

Stage 边界应该由依赖关系的松紧程度决定，而不是由模型模块的物理边界决定。松耦合的 stage 拆开独立调度；紧耦合的反馈回路合并在同一 forward 内，避免跨进程/跨调度器同步开销。

## Sources

- [[sglang-omni-llm-inference]]
