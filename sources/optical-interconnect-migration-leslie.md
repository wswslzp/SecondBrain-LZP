---
title: "光互联大迁徙 - 从光纤、光模块、1.6T 到 CPO 与 OIO 的全产业链终局推演"
author: "[[wu-zihao-leslie]]"
date_published: 2026-04-17
date_ingested: 2026-05-18
url: "https://articles.zsxq.com/id_08rgo2quvhuh.html"
type: article
source_platform: 知识星球
source_group: 半导体大佬的会议室
tags:
  - 光通信
  - cpo
  - 硅光
  - 半导体
  - ai-infrastructure
  - 产业链分析
related: ["[[cpo-co-packaged-optics]]", "[[control-point-convergence]]", "[[silicon-photonics]]", "[[wu-zihao-leslie]]"]
---

# 光互联大迁徙 - 从光纤、光模块、1.6T 到 CPO 与 OIO 的全产业链终局推演

## Summary

作者吴梓豪leslie（半导体行业资深人士，95% 重仓TSMC）从全产业链视角推演光互联未来十年的演进路径。核心观点：AI 不是把光模组卖更贵，而是把整个互连产业从「可插拔模组」→「封装内光学(CPO)」→「计算系统内光学(OIO)」推进，**价值链最终向系统架构者(NVIDIA/Broadcom)、Foundry 制造平台(TSMC)、先进封装收敛**。文章把光互联产业链分成 8 层并对每层做控制点分析，主动去神化 A 股光模块龙头与 FiconTEC 等炒作叙事。

## Key Points

- **「控制点收敛」框架**：光互联产业演进的本质不是器件竞赛，而是控制点从分散的模块层向上收敛到系统架构 + 制造平台
- **三极论**：6.4T CPO 时代的三极是 **NVIDIA（系统架构）+ Broadcom（交换 ASIC）+ TSMC（制造平台）**，作者预判 TSMC 将吃掉 8 成以上 AI 光互联 CPO 代工份额
- **A 股光模块龙头长期价值中心下移**：2028 年 6.4T CPO 面世后失去最高端市场，2030 年 12.8T 时代仅能固守低端 LPO，估值逻辑应从「高成长股」转向「制造交付股」
- **去神化 FiconTEC 炒作**：自动化耦合与测试设备是「必要但可替代」的工程层，不是卡脖子环节，台积电完全可能扶持二供
- **CPO 爆发条件**：「不是技术终于成熟，而是不用它已经撑不住」——GPU cluster 规模超过电互连物理极限时，系统公司被迫改写架构
- **硅光是材料协同平台**：SiPh + InP/GaAs + Ge-on-Si + SiN + TFLN 多材料协同，TSMC 的 COUPE 把光互联第一次按先进封装语言量产化
- **时间线**：2024-2026 可插拔/LPO 主导 → 2026-2029 CPO 进入高端核心 → 2028-2032 6.4T/12.8T → 2030+ OIO 渗入计算内部
- **OIO 唯一可行制造方案**：台积电 MRM 微环硅光，加上 NVIDIA/Broadcom 全力支持，未来形成不可逆地位

## 产业链 8 层分类

详见 raw 文件中的完整公司分层表。核心层级：

1. **系统架构** — NVIDIA、Broadcom、Marvell、Cisco、AMD、Huawei
2. **交换/DSP/PHY** — Broadcom、Marvell、Intel、MaxLinear、MACOM
3. **PIC/硅光平台** — TSMC、Intel、GlobalFoundries、AIM Photonics、IMEC
4. **激光/光源** — Lumentum、Coherent、住友电工、Fujikura、OpenLight
5. **光引擎/OIO 新创** — Ayar Labs、Lightmatter、Celestial AI、Ranovus、Lightelligence、Rockley Photonics
6. **模块整合** — 中际旭创、新易盛、Innolight、光迅、海信宽带、华工科技
7. **无源与耦合件** — 天孚通信、SENKO、上诠、中航光电、Molex、Samtec
8. **材料与设备** — Soitec、IQE、AIXTRON、Veeco、ASM Pacific、FiconTEC

## 作者偏差备忘 ⚠️

- 作者**95% 重仓 TSMC**，疑似台积电背景，因此对 Foundry 层判断存在 confirmation bias
- "TSMC 吃 8 成 CPO 代工" 缺乏量化数据支撑，可能高估
- 对 COHR/LITE 仅划入"光源与 III-V"层，**可能低估**——NVIDIA 自己花 $40 亿绑定它们，说明并非可替代工程层
- 对模块整合层时间表预判（2028 增速放缓、2030 进入估值杀）属于线性外推，半导体技术替代历史上普遍**比预测慢 2-3 年**

## Concepts

- [[cpo-co-packaged-optics]] — Co-Packaged Optics：把光从前面板搬进封装
- [[oio-optical-io]] — Optical I/O：光进入计算内部，chiplet 间互连
- [[silicon-photonics]] — 硅光：CMOS 兼容的 12 吋晶圆光子集成平台
- [[control-point-convergence]] — 光互联产业控制点向上收敛的核心分析框架
- [[optical-interconnect-roadmap]] — 800G→1.6T→3.2T→6.4T→12.8T 演进路径

## Entities

- [[wu-zihao-leslie]] — 文章作者，半导体行业 20+ 年经验
- [[tsmc]] — 作者认为的 CPO/OIO 制造层最大赢家
- [[broadcom]] — 交换 ASIC + CPO 量产节奏组合优势
- [[nvidia]] — AI Fabric 整机定义能力
- [[coherent-corp]] — 高端激光/光源卡脖子环节
- [[lumentum]] — NVIDIA $40 亿 photonics deal 双供之一
- [[zhongji-innolight]] — A 股光模块龙头，作者预判长期价值中心下移
