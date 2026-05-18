---
title: "CPO (Co-Packaged Optics, 共封装光学)"
type: concept
tags: [光通信, 半导体, ai-infrastructure, 先进封装]
date_created: 2026-05-18
date_modified: 2026-05-18
aliases: ["共封装光学", "Co-Packaged Optics"]
related: ["[[silicon-photonics]]", "[[oio-optical-io]]", "[[control-point-convergence]]", "[[optical-interconnect-roadmap]]"]
---

# CPO — Co-Packaged Optics 共封装光学

## Overview

CPO（Co-Packaged Optics）是把光学元件从前面板可插拔模块**搬进交换芯片封装内部**的下一代光互联架构。

它不是单纯的模块小型化，而是一次**价值链重写**：把原本塞在光模块盒子里的 DSP、Driver、TIA、激光器、光引擎、耦合与测试，按照系统与封装的需求**重新分布**到芯片、封装、平台中。

## 为什么 CPO 必然爆发

CPO 的真正爆发条件**不是技术终于成熟，而是不用它已经撑不住**。

随着 GPU cluster 从几千卡扩展到几万卡、几十万卡，[[optical-interconnect-roadmap|可插拔光模块]] 在三个维度同时崩溃：

1. **功耗**：1.6T 可插拔模块的 DSP/SerDes 吃掉约一半功耗，完整模块 20-28W；CPO 单位 800G 可降到 3.5-5.4W
2. **PCB 电损**：电信号在 PCB 上的损耗越来越大
3. **前面板密度**：物理空间不够

放到十万卡、百万卡 AI 工厂里，差距会被放大成数十 MW 等级的全系统用电与散热差。

## CPO 的供应链重构

```
传统光模块时代：
  芯片设计商 → 光器件供应商 → 光模块商 → 系统设备商 → 云厂

CPO 时代：
  系统架构定义者 → 交换 ASIC / DSP / 硅光 IP
                → Foundry / 先进封装平台
                → 光引擎 / 激光器 / 关键器件
                → 系统整合
```

整个产业由「模块装配」逻辑转向「**晶圆与封装**」逻辑。

## 关键玩家

### 系统架构层（最强控制点）
- **NVIDIA** — AI Fabric 内部整机定义
- **Broadcom** — 交换 ASIC + CPO 量产节奏组合优势

### 制造平台层（最强控制点）
- **TSMC** — COUPE 平台 + CoWoS/SoIC/Hybrid Bonding，疑为 8 成份额收敛点
- **Intel** — IDM 路线，硅光研究最早，PIC 出货历史最长，但生态封闭
- **GlobalFoundries** — Fotonix 平台，开放生态但影响力不足
- **Tower** — SiGe 与特殊制程

### 关键器件层
- **Lumentum** — NVIDIA $40 亿 photonics deal 双供之一
- **Coherent** — 高端 EML/CW laser

### OIO 新创层（颠覆者）
- **Ayar Labs**（Intel 投资）
- **Lightmatter**（估值 $44 亿）
- **Celestial AI**

## CPO 时间表

- **2024-2026**：CPO 仍在前沿试点
- **2026-2029**：CPO 在高端交换机侧开始具备不可替代性
- **2028（6.4T）**：CPO 真正从前沿试点走向高端交换机主方案
- **2030+（12.8T）**：CPO 坐实主体地位

## 投资影响（对 [[Roc-Liao-portfolio|Roc 持仓]]）

- **直接受益**：NVDA、AVGO、TSM
- **间接受益**：Coherent、Lumentum（关键器件层，但已涨幅较大）
- **长期承压**：A 股光模块龙头（中际旭创、新易盛等）2028+ 增速放缓
- **被高估**：FiconTEC 等设备股（工程层而非卡脖子）

## 常见认知误区

1. **「在 CPO 供应链上 ≠ 掌握 CPO 核心价值」** — 供应链可以很长，但真正控制点很少
2. **「某细分器件性能很好 ≠ 一定是未来终局」** — 工程化能力、供应链协同、制造收敛比单一性能更重要
3. **「中国供应链每个切入点 ≠ 全球主导权」** — 必要但不等于不可替代

## References

- [[optical-interconnect-migration-leslie]]
