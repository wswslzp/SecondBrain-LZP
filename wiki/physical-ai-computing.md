---
title: "具身 AI 的训练仿真部署循环"
tags: [physical-ai, robotics, simulation, digital-twins, verification]
date_created: 2026-10-22
date_modified: 2026-10-29
related: ["[[agent-comfort-zone]]", "[[embodied-ai-supply-chain]]", "[[context-feedback-loops]]", "[[nvidia]]", "[[lindon-gao]]", "[[dyna-robotics]]", "[[lindon-gao-dyna-xiaojun]]", "[[gpt-6-astra]]", "[[huazhe-xu]]", "[[zheqing-zhu]]", "[[sheng-wang]]", "[[wet-lab-verification-loop]]", "[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]"]
---

# 具身 AI 的训练仿真部署循环

[[nvidia-gtc-berlin-2026]] 用“三台计算机”描述具身 AI：训练模型、在数字孪生中学习与验证技能、在现实设备上执行。三者是计算角色，不要求每个项目都按字面购买三台独立机器。

| 角色 | 主要任务 | 反馈 |
|---|---|---|
| 训练计算 | 学习模型或控制策略，可大规模并行 | 数据、目标函数与训练指标 |
| 仿真计算 | 生成场景、模拟物理与传感器、验证动作 | 碰撞、稳定性、任务结果 |
| 部署计算 | 读取真实传感器并控制设备 | 实际延迟、误差、失效及任务表现 |

演讲里的 MicroDuck 演示由 Agent 编排 CAD 建模、场景制作、物理仿真、云端并行训练、策略评估和实机部署。它体现的是**模型与已有专业工具组成闭环**，而不是语言模型直接凭空获得可靠控制能力。

## 仿真扩大试错范围，但不是现实证明

与 [[agent-comfort-zone]] 的封闭可验证环境相通，仿真让许多试验更便宜、更可重复。进入实机后，[[embodied-ai-supply-chain]] 所述的关节背隙、传感器偏差、线束磨损与批次差异仍会改变结果。仿真通过不能替代硬件标定、受控实测和安全要求。

## 具身 AI 不只等于人形机器人

黄仁勋还将无线基站的感知与波束控制、自适应放疗、自动驾驶归入“感知物理世界并采取动作”的范畴。这是演讲采用的广义分类，不表示这些领域共享同一个验证或监管标准。

## 标准平台的取舍

演讲主张通用机器人形态与参考平台能够汇集需求，推动规模和开发工具循环；人形并非每项任务的最优结构。软件和参考机降低启动成本，不会消除执行器性能、热、可靠性和系统整合的约束。

## DYNA：真实工作流反向约束研究

[[lindon-gao-dyna-xiaojun]] 补充了一个现场视角：演示或仿真通过后，空窗、补料、硬件和维护仍会改变全天产量。DYNA 用完整工作流区分预训练能解决的问题与必须在闭环中处理的问题，见 [[robot-workflow-loop]]。

## 嘉宾视角：Real-to-Sim 的视觉假象、控制边界下压与快慢系统（许华哲，2026-10-20）

清华大学助理教授、破壳机器人创始人 [[huazhe-xu|许华哲]] 在《硅谷101》E256 期（[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]）中，针对 [[gpt-6-astra|GPT-6 Astra]] 对本页“训练—仿真—部署”三角色循环的冲击给出了实测拆解：

- **Real-to-Sim 只是视觉 Hype，物理引擎并未变准**：Astra 能凭几张照片极快复现实验室的 3D 仿真环境并登顶 **RoboDojo** 榜首，但许华哲指出这只是把 **3D 视觉外观**做好了，仿真器的底层物理引擎并未因此变准确，单靠 Sim-to-Real 依然训不出最好的机器人策略。
- **控制层边界下压与 TAMP 复兴**：Astra 能将思维链（CoT）反思转化为厘米级低层动作指令（“撞桌后抬高手”“捏窄劈叉花茎再插花”“手往右伸两厘米”），使传统 **TAMP（任务与运动规划）** 在 Agentic 时代重回台前，也直接利好硬件本体（斯坦福团队两周内即把 Astra 接入宇树机器人完成家庭任务论文演示）。
- **端侧 <10B 快系统 vs. 云端慢系统**：Astra 内部长 CoT 极慢（视频需 16–24 倍速播放）、缺直觉物理、做不了双臂叠衣服，且重复执行第 3 次起耗时卡在 **45 分钟常数**。因此实机部署若跑本地芯片，模型理想尺寸应 **<10B**；若走云端 API，则只能处理准静态任务（可容忍 200ms+ 网络延迟），无法处理倒水、抖毛巾等高动态任务。

## References

- [[nvidia-gtc-berlin-2026]] — 1:00:15–1:17:40
- [[silicon-valley-101-humanoid-robot-hardware]] — 硬件、标定与量产约束
- [[lindon-gao-dyna-xiaojun]] — 张小珺对 DYNA 创始人 Lindon Gao 的访谈（2026-10-15）
- [[silicon-valley-101-gpt6-astra-agent-robotics-pharma]] — 《硅谷101》E256 Agent、机器人与制药，谁先被GPT-6 Astra改写？（2026-10-20）
