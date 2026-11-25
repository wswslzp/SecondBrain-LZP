---
title: "王晟（Sheng Wang）"
tags: [person, ai-for-science, biomedical, drug-discovery, uw, researcher]
date_created: 2026-10-29
date_modified: 2026-10-29
related: ["[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]", "[[gpt-6-astra]]", "[[wet-lab-verification-loop]]", "[[haozhe-wang]]", "[[atomic-microscopy]]", "[[agent-comfort-zone]]", "[[huazhe-xu]]", "[[zheqing-zhu]]"]
---

# 王晟（Sheng Wang）

**王晟（Sheng Wang，X: `@profshengwang`）** 是华盛顿大学（University of Washington）保罗·艾伦计算机科学与工程学院（Paul G. Allen School of Computer Science & Engineering）助理教授，同时担任 **Apodex** 首席科学家（Lead Scientist）。北京大学本科（2013），研究方向聚焦于 AI for Science、计算生物学、生物医学大模型与 AI 药物发现（曾与微软研究院 Hoifung Poon、华盛顿大学 William S. Noble 等合作发表数字病理全切片基础模型与多组学研究）。

在《硅谷101》E256 期（[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]，2026-09-29 录制）及《硅谷101》Alignment 2026 年度大会论坛上，他系统剖析了 [[gpt-6-astra|GPT-6 Astra]] 在生物医学科研中的真实表现、干湿实验的巨大鸿沟，并提出了 **“[[wet-lab-verification-loop|Human Use（人类/湿实验调度）]]”** 与 **“无上限（Uncapped）Benchmark”** 等核心概念。

## 核心观点与一线观察（硅谷101 E256）

### 1. 为什么团队从 Claude 切换到 GPT-6 Astra？
- **Computer Use 拯救生物医学“古董软件”**：生物信息学中大量必用工具（如网页端质控汇总工具 **MultiQC**）编写于十多年前，界面难用且术语晦涩。Astra 因在预训练中吸收了网上的软件教程（Tutorials）与用户日志（User logs），能直接看屏幕操作这些老旧软件，甚至反向教会跨学科学生使用工具。
- **日夜分流的长程工作流**：白天用反馈快的模型；晚上用 Astra 设计长达 **8–24 小时**的复杂科研 Pipeline 跑通宵。
- **提升源于 Coding 而非生物知识，安全拒答反噬体验**：Astra 在生物医学专有知识测试上并无提升，进步全靠通用 Coding、文献检索与长程规划。同时，由于 Astra、Opus、Fable 的生物安全护栏愈发严苛，动辄 **Refuse to answer（拒绝回答）**，团队日常反而多用 **Kimi K3** 或 **Muse Spark 1.3**；用 Astra 时需套用“我只是在设计 Benchmark”的话术绕过限制。

### 2. 干实验代码题已超人类教授，真瓶颈在 30% 完成度的湿实验设计
- **现有生物 Benchmark 的 Kaggle 化**：明确给定数据集的生物评测已退化为机器学习工程题（MLE-bench）。在 **Terminal-Bench Science** 的生物医学题上，Astra 虽只拿 60 多分（满分 100），但解题表现已超越王晟本人。干实验的下一个计算挑战是如何高效处理单人高达 **2TB** 的复杂生物医学数据。
- **湿实验设计完成度仅 30%**：真正的新药发现没有标准答案，必须进**湿实验（Wet Lab）**。AI 虽能生成分子式，但在“如何合成、何种温湿度储存、小鼠给药周期”及**根据实验室现有器材“看菜做饭”**（厨房只有番茄鸡蛋土豆，Astra 却要求做海鲜大餐）上完成度仅 **30%**，必须靠资深实验技术员（Technician）修改。

### 3. 制药周期、百万美元级授权与单条十万美元的湿实验数据
- **动物代谢不可跳过**：AI 几小时算出的分子，需经细胞与小鼠实验（几周，期间模型已迭代一代）→ **猕猴等灵长类实验（每轮 4 个月，两轮即 8 个月）**。AI 制药初创通常在猴子实验结束（总周期 **6–12 个月**）后，以 **1000 万美元以上**授权费（License fee）卖给拥有患者网络的大药厂做临床人体试验。
- **数据护城河**：AlphaFold 1/2/3 与 OpenFold 开源后，最珍贵的是互联网语料库里不存在的真实动物实验数据——**在活体动物上跑通一条“某分子能否在小鼠体内杀灭癌细胞”的数据，价值高达几万至几十万美元**。
- **周期决定突破顺序**：实验周期越短，AI 迭代越快。**酶（Enzyme，工业催化剂，如地沟油转食用可用油、低温活性洗衣粉）**与**蛋白质**最先跑出来（Anthropic 正通过 **MCP** 接口连接刚融资 4000 万美元的云端湿实验公司 **Adaptyv Bio** 举办酶设计比赛）；而抗衰老与罕见病周期极长，进展依然缓慢。

### 4. 未来范式：从 Computer Use 到“Human Use”与 AI 原生仪器
- **Instruction Generation（指令生成 / Human Use）**：从“人写 Prompt 指挥 AI”转向**“AI 根据科研预算（如 10 万美元）与实验室设备约束，生成清晰无歧义的指令去调度人类技术员或机器人”**。
- **跳过人类视觉的实验设备**：现在的 X 光、CT 合成图像是为了给人眼看；未来的实验仪器将直接把底层原始波形与物理信号喂给 AI。
- **反向蒸馏与人类机长**：跨学科科学家每天都在“反向蒸馏”AI 学习新知；人类科学家的终极角色是**定义无上限的新问题**（如活到 200 岁、把癌细胞杀伤率从 30% 推向 40% 的无上限 Benchmark）并为重大医疗决策提供**人类责任背书**。

## 相关页面

- [[silicon-valley-101-gpt6-astra-agent-robotics-pharma]] — 播客 Source 摘要页
- [[silicon-valley-101-gpt6-astra-agent-robotics-pharma-chinese-article]] — 播客中文长文
- [[wet-lab-verification-loop]] — 生物医药干湿实验闭环与 Human Use
- [[gpt-6-astra]] — GPT-6 Astra 模型页
- [[haozhe-wang]] / [[atomic-microscopy]] — AI for Science 在纳米制造中的对照视角

## References

- 《硅谷101》E256《Agent、机器人与制药，谁先被GPT-6 Astra改写？》（2026-10-20 发布，2026-09-29 录制）
- 个人主页：https://homes.cs.washington.edu/~swang/
- X (Twitter): `@profshengwang`
