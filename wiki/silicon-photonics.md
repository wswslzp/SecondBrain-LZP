---
title: "Silicon Photonics (硅光)"
type: concept
tags: [光通信, 半导体, 先进封装, foundry]
date_created: 2026-05-18
date_modified: 2026-05-18
aliases: ["硅光", "SiPh", "Silicon Photonics"]
related: ["[[cpo-co-packaged-optics]]", "[[oio-optical-io]]", "[[control-point-convergence]]"]
---

# Silicon Photonics — 硅光

## Overview

硅光（SiPh）是基于 CMOS 兼容工艺、12 吋晶圆的光子集成平台。在 [[cpo-co-packaged-optics|CPO]] 时代，硅光是**最符合系统架构需求的制造平台**——可以把波导、调制器、探测器与一部分控制电路放进同一条工艺语言里。

## 关键认知：硅光不是单一材料神话

硅光是**材料协同平台**，不是单一材料：

| 材料 | 分工 |
|------|------|
| SiPh（硅光） | 波导与基础平台 |
| InP / GaAs | 激光与部分高性能器件 |
| Ge-on-Si | 探测器 |
| SiN | 低损耗波导 |
| TFLN（薄膜铌酸锂） | 高性能调制器（未来变量） |

> 真正竞争的从来不是『硅光对磷化铟』这种二元对立，而是谁能把多种材料放进同一个制造体系里，并把它们做成可量产的系统级产品。

## Foundry 平台格局

### TSMC（最大赢家）
- **COUPE 平台**：65nm SiPh + 先进制程 EIC + CoWoS + SoIC + Hybrid Bonding
- 优势：把光互联第一次按先进封装语言量产化
- 作者预判：**吃掉 8 成以上 AI 光互联 CPO 代工份额**
- ⚠️ 8 成预测**缺乏量化数据支撑**，可能高估（作者 95% 重仓 TSMC，存在偏差）

### Intel
- IDM 路线
- 硅光研究最早，PIC 出货历史最长
- 最强 IP 矩阵
- 但**生态相对封闭**

### GlobalFoundries
- Fotonix 平台
- 较早开放生态，但影响力不足
- 双波导层，对外部客户更灵活
- 已绑定 Lightmatter 等新创

### Tower
- SiGe、特殊制程
- 维持细分光电/模拟环节壁垒

### Samsung
- 在追赶
- 整体硅光与封装收敛能力尚未成头部

## 容易被忽略的关键点

### 1. 设计工具与 PDK 生态

PIC Studio、pMaxwell、PhotoCAD、pLogic、pVerify、pSim 这些设计工具是**产业化基建**。当光子器件进入 Foundry 时代，EDA 与 PDK 不再是附属品。

**国际玩家**：Synopsys、Cadence（已垄断电子 EDA，正在扩展硅光）

### 2. MPW 与开放平台战略价值

TSMC、GF、IMEC、AIM Photonics 之所以重要，不只是能做硅光，更因为它们在**培育未来客户与新创生态**。Lightmatter、Ayar Labs 这些公司能不能长大，往往取决于能不能在这些平台上把设计做成、把良率跑出来。

### 3. 可靠性与标准化

CPO 跨光学、电学、热学、机械与材料界面。JEDEC、Telcordia 等现有标准对硅光局限性大。**谁能率先建立可靠性、测试与标准语言，谁就更有可能在商用竞赛里占先**。

这一点不是设备商能主导的，而是**系统公司、Foundry 与标准联盟共同主导**。

## 硅光的 OIO 终局

台积电的 **MRM（微环硅光）方案**是目前所有技术路线中唯一具备步入 [[oio-optical-io|OIO]] 可能的制造方案。加上 NVIDIA、Broadcom 全力支持，未来将形成不可逆的行业地位。

## References

- [[optical-interconnect-migration-leslie]]
