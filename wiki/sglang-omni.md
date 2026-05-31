---
title: "SGLang Omni"
type: entity
tags: [ai, inference, sglang, multimodal-ai, speech-ai]
date_created: 2026-06-01
date_modified: 2026-06-01
aliases: ["SGLang Omni", "sglang-omni"]
related: ["[[llm-inference-systems]]", "[[multi-stage-decode]]", "[[multimodal-ai]]"]
---

# SGLang Omni

SGLang Omni 是 SGLang 社区面向 multi-stage / omni 模型推理的系统设计方向，目标是支持语音输出等标准 LLM 推理无法同构处理的模型拓扑。它不是简单按输入输出模态划分，而是按 decode 是否 multi-stage 划分系统边界。

## Architecture Ideas

- **调度解耦**：Thinker 与 Talker 维护独立调度循环，各自针对 compute/memory/kernel-launch 瓶颈优化。
- **Talker + MTP 合并**：同步紧耦合的反馈回路放在同一 stage 的 forward 中，避免跨 stage 延迟。
- **分层通信**：ZMQ 做控制面事件通知，relay 做数据面 Tensor 传输。
- **多方显存预算**：每个 stage 声明 `total_gpu_memory_fraction`，启动时汇总校验，避免单一全局显存比例失效。
- **Coordinator 只管拓扑**：路由、输出合并、abort 广播，不绑定具体 stage 实现。

## Significance

SGLang Omni 的重点在于展示推理系统设计的一套方法论：先识别给定计算过程的计算特性，再为其设计高效、鲁棒的系统。这个框架可迁移到其他 [[multi-stage-decode]] 模型和实时语音/多模态系统。

## Sources

- [[sglang-omni-llm-inference]]
- GitHub: https://github.com/sgl-project/sglang-omni
