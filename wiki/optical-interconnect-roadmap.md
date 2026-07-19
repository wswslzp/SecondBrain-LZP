---
title: "Optical Interconnect Roadmap (光互联代际演进)"
type: concept
tags: [光通信, 半导体, ai-infrastructure]
date_created: 2026-05-18
date_modified: 2026-05-18
aliases: ["光互联代际演进", "光模块速率路线图"]
related: ["[[cpo-co-packaged-optics]]", "[[silicon-photonics]]", "[[oio-optical-io]]", "[[nvidia]]", "[[extreme-co-design]]"]
---

# Optical Interconnect Roadmap — 光互联代际演进

## Overview

光互联速率每代翻倍，但每升一代整个系统都要重构。当前主线是 **800G → 1.6T → 3.2T → 6.4T → 12.8T**，伴随 [[cpo-co-packaged-optics|CPO]] 与 [[oio-optical-io|OIO]] 的逐步替代。

## 速率代际表

| 代际 | 通道 × 速率 | Baudrate | 主流方案 |
|------|------------|----------|---------|
| 400G | 4×100G | 53.125 GBaud | 可插拔 |
| 800G | 8×100G | 53.125 GBaud | 可插拔为主 |
| 1.6T | 8×200G | 106.25 GBaud | 可插拔 + LPO 并存 |
| 3.2T | 8×400G | 224 GBaud | LPO + NPO + 早期 CPO |
| 6.4T | TBD | TBD | CPO 主方案 |
| 12.8T | TBD | TBD | CPO 坐实主体 |

## 技术路线对比（功耗维度）

| 方案 | 1.6T 单模块功耗 | 特点 |
|------|---------------|------|
| 可插拔（含 DSP） | 20-28W | DSP/SerDes 吃掉约一半功耗 |
| LPO（去 DSP） | 12-15W | 维护性好，供应链成熟 |
| NPO | 中间过渡 | 少数过渡方案 |
| CPO | 3.5-5.4W (单位 800G) | 高端交换核心 |
| OIO | 更低 | 计算/存储内部互连 |

## 时间线（吴梓豪leslie 预判）

```
2024 ──── 2026 ──── 2028 ──── 2030 ──── 2032
│         │         │         │         │
│ 400G/800G/1.6T 可插拔 + LPO 主导
│         │
│         │ 200G/lane → 400G/lane
│         │ CPO 在高端交换机侧具备不可替代性
│         │         │
│         │         │ 6.4T/12.8T 进入主干架构
│         │         │ PCB 在高端场景退场
│         │         │ 光互联从 front panel 进入 package
│         │         │         │
│         │         │         │ OIO 由原型走向计算内部
```

⚠️ **时间表别太当真**：半导体技术替代历史上普遍**比预测慢 2-3 年**（HBM、Chiplet 都是案例）。

## 拐点判断

> 真正决定拐点的，不是某个器件的实验室性能，而是当 GPU cluster 的规模超过电互连可承载极限之后，系统公司被迫改写架构。

也就是说，**CPO 的爆发条件不是技术终于成熟，而是不用它已经撑不住**。

## 多路线并存（不是单线替代）

未来几年大概率不是单线替代，而是**分层共存**：

- **可插拔与 LPO**：维持长尾与成本敏感市场
- **NPO**：少数过渡方案
- **CPO**：进入高端交换核心
- **OIO**：更远时间点渗入计算与存储器内部互连

## 对 A 股光模块龙头的影响

| 时间 | 状态 | 估值逻辑 |
|------|------|----------|
| 2024-2027 | 仍占主流位置，业绩高速增长 | 高成长股（30-50PE） |
| 2028（6.4T CPO） | 失去最高端市场，业绩"增速"放缓 | 估值开始下移 |
| 2030+（12.8T） | 仅能固守低端 LPO | 制造交付股（15-25PE） |

详见 [[control-point-convergence]] 框架。

## 与 NVIDIA 的呼应

本页「拐点不是器件成熟、而是不用它已撑不住」与 [[jensen-huang|Jensen]] 的 [[extreme-co-design]] 完全同构：当「问题装不进一台电脑」、要把上万台机器连成一个 NVLink domain 时，networking / 光互连 / copper 就成了与 GPU 同等的瓶颈（Amdahl's Law）。NVLink-72 把整个机架当作一个 GPU 域来跑万亿参数 MoE——正是电互连逼近极限、系统公司被迫改写架构的直接例证（见 [[nvidia]]）。

## References

- [[optical-interconnect-migration-leslie]]
