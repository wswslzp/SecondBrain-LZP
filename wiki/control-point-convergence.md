---
title: "Control Point Convergence (产业链控制点收敛)"
type: concept
tags: [产业分析, 半导体, 光通信, 投资框架]
date_created: 2026-05-18
date_modified: 2026-05-18
related: ["[[cpo-co-packaged-optics]]", "[[silicon-photonics]]", "[[optical-interconnect-roadmap]]"]
---

# Control Point Convergence — 产业链控制点收敛

## Overview

「控制点收敛」是吴梓豪leslie 在 [[optical-interconnect-migration-leslie]] 中提出的核心分析框架，用来理解一个产业链在技术代际切换时**价值如何从分散环节向少数关键节点集中**。

核心观点：判断一家公司的长期地位，**不能只看它在不在主流供应链上，要看它处在哪一层**。系统架构者、关键 IP 控制者、制造平台是天然控制点；模块整合、连接件、自动化设备多数是必要但可替代的工程层。

## 光互联产业的三阶段收敛

```
光模块时代       价值链分散：
  →           芯片设计→光器件→光模块厂→设备商→云厂

CPO 时代         价值链上移：
  →           系统架构 → 交换 ASIC/DSP/硅光 IP
              → Foundry/先进封装 → 关键器件 → 系统整合

OIO 时代         价值链终局：
              光学成为计算架构本身，价值中心继续上移到
              系统公司 + 制造平台
```

## 控制点判断的 4 个维度

判断一家公司是否站在控制点上，看以下 4 个问题：

1. **能否定义系统架构？** — 例如 NVIDIA 定义 AI Fabric，决定带宽节奏与部署形态
2. **能否控制核心 IP？** — DSP、SerDes、PAM4/FEC 这种"最能吃模块价值"的环节
3. **能否量产？** — Foundry/先进封装平台是把所有技术做成可大规模交付的工业流程
4. **能否卡住关键供应？** — 高端 EML/CW laser、特殊材料这种短期无法替代的环节

满足 1-2 项 = 真控制点；只满足 3 或 4 之一 = 必要但可替代的工程层。

## 应用到光互联产业链的判断

| 层级 | 控制点强度 | 代表公司 | 理由 |
|------|------|----------|------|
| 系统架构 | ★★★★★ | NVIDIA、Broadcom | 定义需求与规则 |
| Foundry/封装 | ★★★★★ | TSMC | 制造收敛点 |
| DSP/SerDes | ★★★★ | Broadcom、Marvell | 吃掉模块价值 |
| 高端激光 | ★★★★ | Coherent、Lumentum | 卡脖子但客户绑定深 |
| 模块整合 | ★★ | 中际旭创、新易盛 | 短期出货弹性，长期下移 |
| 无源耦合 | ★★ | 天孚、SENKO | 必要但易替代 |
| 设备耦合 | ★ | FiconTEC | 工程层，可被二供化 |

## 投资启示（对 [[Roc-Liao-portfolio]] 适用）

- **NVDA 持仓 = 已站在最高控制点** ✅
- **AVGO 是 NVDA 的天然产业链补强**（同生态、不同价值层）
- **TSM 是制造层最大赢家**，但对已持有 NVDA 的人来说边际收益有限
- **A 股光模块龙头要谨慎**：短期 2-3 年仍有窗口，但 2028+ 面临"估值杀+业绩杀"双杀风险
- **避开炒作叙事**：FiconTEC 类设备股 = 工程层，不是卡脖子

## 框架的局限性

- **作者主观偏差**：吴梓豪leslie 95% 重仓 TSMC，对 Foundry 层判断可能存在 confirmation bias
- **时间表线性外推**：半导体技术替代历史上普遍比预测慢 2-3 年（HBM、Chiplet 都是案例）
- **低估光源层**：NVIDIA 花 $40 亿绑定 COHR/LITE，说明它们比作者定位的"工程层"更接近核心

## References

- [[optical-interconnect-migration-leslie]] — 框架原始来源
