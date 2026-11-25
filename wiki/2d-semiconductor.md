---
title: "二维半导体（2D Semiconductor）"
tags: [semiconductor, 2d-materials, mos2, graphene, tsmc]
date_created: 2026-10-27
date_modified: 2026-10-27
related: ["[[haozhe-wang]]", "[[harry-wang-beyond-silicon-chips]]", "[[atomic-microscopy]]", "[[memory-wall]]"]
---

# 二维半导体（2D Semiconductor）

**二维半导体**指只有一个或几个原子层厚的半导体材料，是硅基芯片逼近物理极限后的下一代沟道材料候选。核心论据来自 [[haozhe-wang|Haozhe "Harry" Wang]] 在硅谷101 Alignment 2026 的 Keynote（[[harry-wang-beyond-silicon-chips|source]]）。

## 为什么需要它：硅的极限

- 硅材料缩小到 **5nm 以下**时，电子迁移率和速度显著下降——即使晶体管"开启"，电子也流不畅。
- 业界宣传的 2nm/1nm 节点多为**名义节点**：纳米片结构每层硅约 7nm、堆三层，7÷3≈"2nm"。这与 Intel 从单核 Pentium 转向 12/14 核是同一逻辑——**单个单元无法继续缩小，行业靠堆叠**。
- 晶体管缩小的经典失效模式是**漏电（leakage）**：材料太厚时，即使栅极关闭，电子仍从材料下方流过，白白耗电发热。对策是把沟道做得尽可能薄。

## 代表材料

- **石墨烯**（graphene）：2010 年诺贝尔物理学奖；本身零带隙，更常作为研究范式。
- **MoS₂（二硫化钼）**：一个钼原子+两个硫原子，总厚约 **0.65nm**，仍能保持电子迁移率；过去十年的学术研究表明其单器件性能优于硅。
- 更广的一类：二维过渡金属硫族化合物（TMD）。台积电路线图：纳米片 → CFET（互补场效应晶体管）→ 二维 TMD。

## 制备与良率：真正的瓶颈

- 主流工艺是 **CVD（化学气相沉积）**：两种前驱体由气体携带，在衬底上沉积单层材料。
- 纯度对比悬殊：硅可提纯到"10–12 个 9"（12 英寸晶圆逐原子检查仅一两个堆垛层错），CVD 二维材料做不到，现有工业流程需为此改变。
- 核心卡点一个词：**良率（yield）**。数千亿晶体管的良率管理是台积电统治力的来源；新型二维材料需要全新的良率管理思路——目前行业仍靠人观察材料、查缺陷。
- 延伸应用：打印在柔性衬底上可做光响应器件（"尺蠖"式光驱动）。

## AI 的切入（Harry Wang 实验室）

1. **看**：[[atomic-microscopy|ATOMIC]] 用 LLM agent + SAM + 无监督聚类做零训练材料表征，识别准确率 99.7%，能发现人眼忽略的畴界。
2. **做**：与 Google DeepMind Co-Scientist 合作，AI 查文献、生成适配定制设备的实验配方，控制仪器执行，可一次尝试成功。
3. **造**：AI 在良率仅 65.6% 的缺陷材料上挑选无缺陷区域、差异化布局晶体管，造出千级晶体管阵列，良率提升约 30 个百分点。

## 与 vault 的关联

- [[accelerated-computing]]：体系结构视角的"通用计算尽头"；本页是材料视角的同题回答。
- [[memory-wall]]：另一类器件级瓶颈（存储带宽），与晶体管缩小极限并列。
- [[control-point-convergence]]：yield intelligence 可能成为制造环节的新控制点。

## References

- [[harry-wang-beyond-silicon-chips]]（硅谷101 Alignment 2026 Keynote）
- Duke ECE 人物页与 ATOMIC 公开报道
