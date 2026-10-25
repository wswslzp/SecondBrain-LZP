---
title: "Memory Wall & Near-Memory Compute（内存墙与近存计算）"
tags: [ai-hardware, memory, hbm, inference, semiconductors]
date_created: 2026-07-21
date_modified: 2026-07-21
related: ["[[qualcomm]]", "[[llm-inference-systems]]", "[[token-economics]]", "[[ai-capex-beneficiaries]]", "[[nvidia]]"]
---

# Memory Wall & Near-Memory Compute

**内存墙（memory wall）**：算力扩张速度已超过「把数据喂给算力」的能力——**解码密集的推理受限于每秒字节传输量（bytes-per-second）**，而非算力本身。这造就了一个极度短缺 DRAM/HBM 的市场，也逼出一批绕过 HBM 的架构。

## 问题
- Decode-heavy inference 是 **bandwidth-bound**：通过先进封装（硅中介层）堆叠 DRAM 得到 **HBM（高带宽内存）** 是当前答案，但 HBM 昂贵且供给受限。
- 经济学定律：「高价自解」——高 DRAM/HBM 价格既激励扩产，也**激励创新绕过它**（"The higher DRAM prices go, the more incentive there is to find ways around HBM"）。呼应 Jevons 悖论：内存越便宜，越强化「少用 HBM 字节/token」架构的合理性。

## 两条绕行路线
- **软件侧**（见 [[llm-inference-systems]]、[[token-economics]]）：把模型数据留在片上、用更便宜介质替代 DRAM、把计算移近内存、按推理阶段匹配内存层级、跨加速器池化。多数是软件/架构层，边际利润画像与内存交易相似（同受 Jevons 悖论支配）。
- **硬件侧——近存计算（near-memory compute）**：把加速器直接堆到内存下方，绕开中介层。代表是 [[qualcomm|Qualcomm]] 的 **HBC（High Bandwidth Compute）**。

## Qualcomm HBC（2027）
- 处理器经**硅通孔（TSV）**堆叠在 **LPDDR** 内存正下方，带宽垂直穿过内存密度实现类 SRAM 性能，省去中介层与昂贵 CoWoS 封装，可无先进封装地在单设备内拼堆多块 HBC。
- 宣称（**厂商数字，非作者**）：对比 HBM **6x 带宽/瓦**、对比 SRAM **200x 容量/瓦**、**4-8x** 解码性能/瓦与 TCO、聚合 **~133 TB/s**（作者提醒：133 TB/s 很可能是 LPDDR↔HBC 间的聚合有效带宽，端到端持续解码速度会更低）。
- 由「移动设备低功耗/小面积」约束反推而来的技术路径——把约束变成卖点。

## 与 vault 的关联
- 是 [[llm-inference-systems]]（prefill/decode、KV cache、显存管理）在**硬件封装层**的延伸，也是 [[ai-capex-beneficiaries]] 主题 1 的技术底座。
- 与 [[nvidia]] 的 extreme co-design / HBM 依赖形成对照：HBC 是「绕开 HBM 收费站」的路线之一。

## References
- [[citrini-all-along-the-ai-watchtower]]
