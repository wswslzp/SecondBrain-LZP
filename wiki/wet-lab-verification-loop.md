---
title: "生物医药干湿实验闭环与 Human Use（Wet-Lab Verification Loop）"
tags: [ai-for-science, biomedical, drug-discovery, wet-lab, mcp, benchmark, concept]
date_created: 2026-10-29
date_modified: 2026-10-29
related: ["[[sheng-wang]]", "[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]", "[[gpt-6-astra]]", "[[agent-comfort-zone]]", "[[physical-ai-computing]]", "[[haozhe-wang]]", "[[atomic-microscopy]]", "[[autogenic-intelligence]]", "[[anthropic]]"]
---

# 生物医药干湿实验闭环与 Human Use（Wet-Lab Verification Loop）

在 AI for Science（尤其是生物医药与新药研发）中，**干实验（Dry Lab，计算机内的模拟、结构预测与代码分析）** 与 **湿实验（Wet Lab，真实实验室里通过试管、培养皿、细胞、小鼠与灵长类动物进行的物理化学验证）** 之间存在着巨大的时间与认知断层。华盛顿大学助理教授 **[[sheng-wang|王晟]]** 在《硅谷101》E256 期（[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]）中系统阐述了这一断层，并提出从 **Computer Use（计算机操作）** 迈向 **Human Use / Instruction Generation（人类调度 / 指令生成）** 的新范式。

## 为什么干实验满分救不了新药研发？

1. **现有生物 Benchmark 的 Kaggle 化**：许多公开生物医学评测集为了迎合 AI，给定干净的数据集预测固定指标，本质上退化成了数据科学竞赛（MLE-bench）。随着 [[gpt-6-astra|GPT-6 Astra]] 等模型通用 Coding 能力跃升，这类干实验问题已基本被攻克（Astra 在 Terminal-Bench Science 上的表现已超越人类顶尖教授）。
2. **科学发现的“无答案悖论”**：真正高价值的科学问题（如“设计一款治愈某癌症的新药”）在进湿实验之前是**没有标准答案**的——如果人类已经知道答案并写进测试集，就不需要研究了。当 GPT 和 Claude 各自给出一个候选分子式时，唯一能检验对错的考场是真实世界的湿实验。
3. **自然代谢周期的硬约束（数学 vs. 生物）**：AI 能在数学上攻克千禧年级别猜想（见 [[agent-comfort-zone]]），因为数学可在计算机内瞬间验证；而生物医药受制于动物新陈代谢的自然规律：

| 阶段 | 典型耗时（王晟口述） | 核心瓶颈与商业节点 |
|---|---|---|
| **1. AI 干实验设计分子** | 几小时 ～ 几天 | AlphaFold 1/2/3 与大模型已将此环节从半年压缩至数小时，但无法跳过后续验证 |
| **2. 细胞与小鼠实验** | 数周 | 等待活体新陈代谢反应；**往往一次小鼠实验还没做完，底层大模型已从 GPT-6 迭代到 6.1/6.2** |
| **3. 灵长类（猕猴）实验** | **4 个月 / 轮**（做两轮即 **8 个月**） | 临床前最关键的安全性与有效性验证；耗时漫长且极其昂贵 |
| **4. 授权大药厂（License-out）** | 总临床前周期 **6–12 个月** | AI 制药初创公司通常在猴子实验结束后直接 License 给拥有庞大患者网络的大药企，**单笔授权费通常 >1000 万美元**；人体临床 I–III 期仍需 5–10 年 |

4. **实验周期决定 AI 突破顺序**：大模型在生物细分领域的突破速度，严格正比于该领域湿实验反馈的快慢。**酶（Enzyme，工业催化剂，如将地沟油转化为可用油、研发低温高活性洗衣粉）** 与 **蛋白质设计** 因实验验证周期极短（如 Claude 21 小时发现类 CRISPR 的 **ART** 新酶系统），成为最先跑通商业化的方向；而**抗衰老**与**罕见病**因反馈周期极长、数据匮乏，模型进展依然缓慢。

## 30% 完成度瓶颈：从“给分子式”到“Human Use”

当前大模型能轻松生成候选分子式，但在**设计具体可执行的湿实验方案**上，完成度仅有约 **30%**（其余 70% 需资深实验技术员 Technician 修改）：
- **细节缺失**：不懂如何具体合成该分子、在何种温度与湿度下保存、以什么周期和剂量给小鼠用药。
- **不会“看菜做饭”（资源盲区）**：每个实验室的仪器和试剂库存不同。王晟比喻：*“饭店厨房里只有番茄、鸡蛋和土豆，让 Astra 设计一道菜，它却张口要求做一桌海鲜大餐。”*

### 核心新范式：Human Use 与 Instruction Generation（指令生成）
- **定义**：如果说 Computer Use 是 AI 通过屏幕操作电脑软件，那么 **Human Use** 就是 **AI 调度真实实验室里的实验技术员（Technician）或机器人去执行物理实验**。
- **反转 Prompt 方向**：过去是人类研究怎么写好 Prompt 指挥 AI（Instruction Following）；未来是 **AI 来 Prompt 真实世界（Instruction Generation）**——人类输入预算与资源约束（*“给你 10 万美元，做一次小鼠实验 2000 美元，本实验室有以下设备，请设计方案”*），AI 输出清晰、无歧义、高可执行性的实验操作指令。
- **AI 原生实验仪器**：未来的实验与医疗设备不再为了迎合人眼而把信号合成为 X 光片或 CT 图像，而是直接将底层的原始波形与物理信号输入给 AI。

## 商业与基建演进：十万美元一条的数据与 MCP 湿实验云

1. **单条动物实验数据价值数万至数十万美元**：AlphaFold 3 与 OpenFold 开源后，模型算法被拉平，护城河转向互联网公开语料中绝不存在的真实湿实验数据。在完整活体动物身上跑通一条“某分子能否在小鼠体内杀灭癌细胞”的数据，价值高达**几万至几十万美元**（远高于几千美元一道的奥数或编程评测题）。
2. **MCP 直连云端湿实验室（Adaptyv Bio 案例）**：[[anthropic|Anthropic]] 不仅招募了诺奖得主 John Jumper（江珀）并自建湿实验团队，还与刚融资 **4000 万美元**的湿实验初创 **Adaptyv Bio** 深度合作——大模型生成蛋白质预测后，直接通过 **MCP（Model Context Protocol）** 协议调用 Adaptyv Bio 立即启动湿实验验证，并以最终湿实验结果作为比赛评判标准。
3. **实验室为 AI 重构（Redesign）**：前沿实验室正将湿实验前置条件（如细胞培养）全部预先备妥，只留出等待 AI 预测的加样步骤，实现干湿闭环无缝衔接。
4. **无上限（Uncapped）Benchmark 飞轮**：摒弃“某基因是否致癌”的静态分类题，改为“将癌细胞杀伤率从 SOTA 的 30% 持续提升至 40%、50%”的无上限任务，在持续迭代中沉淀高价值湿实验数据飞轮（另见扎克伯格夫妇 Biohub 联合 DeepMind、Meta、Isomorphic Labs、DOE、NIH 扩至 **18 亿美元**的“虚拟细胞计划”）。

## 与 Vault 已有知识的关联

- **[[agent-comfort-zone]] / [[physical-ai-computing]]**：本页是“封闭可验证环境 vs. 开放物理/生物世界”在生命科学领域的最典型例证。
- **[[haozhe-wang]] / [[atomic-microscopy]] / [[autogenic-intelligence]]**：杜克大学王浩哲展示的“AI 科学家连接 CVD 生长设备 + ATOMIC 显微镜表征二维半导体”，与王晟提出的“MCP 湿实验云 + Human Use + 仪器直接喂原始信号给 AI”在方法论上完全同构，共同构成 AI for Science 从计算走向物理闭环的双翼。

## References

- [[silicon-valley-101-gpt6-astra-agent-robotics-pharma]] — 《硅谷101》E256《Agent、机器人与制药，谁先被GPT-6 Astra改写？》（2026-10-20）
- [[silicon-valley-101-gpt6-astra-agent-robotics-pharma-chinese-article]] — 播客中文长文
