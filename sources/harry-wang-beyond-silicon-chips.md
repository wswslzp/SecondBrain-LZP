---
title: "半导体的未来：从新材料到新芯片，AI能否推动自身进化？"
author: "硅谷101；讲者 Haozhe 'Harry' Wang（杜克大学）"
date_ingested: 2026-10-27
date_published: 2026-10-27
tags: [semiconductor, 2d-materials, ai-for-science, yield, autogenic-intelligence]
url: "https://www.youtube.com/watch?v=cmhym0OcoS8"
---

# 半导体的未来：从新材料到新芯片，AI能否推动自身进化？

**来源**：硅谷101「Alignment 2026」年度线下大会 Keynote 演讲（YouTube 2026-10-27 上传，29:44）

讲者 [[haozhe-wang|Haozhe "Harry" Wang]]（杜克大学 ECE 助理教授，AI for Nanofabrication 实验室）从晶体管与摩尔定律讲起，论证硅材料的物理极限与"名义节点"的行业叙事落差，介绍二维半导体（MoS₂）的制备与良率瓶颈，然后依次展示实验室的三项工作——[[atomic-microscopy|ATOMIC]]（AI 控制显微镜做材料表征）、与 Google DeepMind 合作把 Co-Scientist 接入真实实验设备、AI 在缺陷材料上直接造芯（良率 65.6% 提升约 30 个百分点）——最后提出 [[autogenic-intelligence|自生成智能（Autogenic Intelligence）]]设想，并以"蟹化"之问收尾：AI+芯片的智能形态会走向分化还是趋同。

## 一句话

当 AI 不仅能用芯片，还能**看材料、做实验、造芯片**时，模型与硬件就形成互相制造的飞轮——讲者称之为一种新的硅基生命形态。

## 关键 takeaways

### 芯片 101
- 晶体管=水龙头：栅极开关控制源极→漏极的电子流；scaling law 在半导体领域早已存在——单芯片晶体管越多越强（例：NVIDIA Blackwell 300 单芯片 2000 亿晶体管）。
- 演化路径：微米平面 → FinFET → 堆叠 nanosheet；堆叠带来散热问题，缩小带来漏电（leakage）——材料越薄，"水龙头"关得越严。

### 硅的极限与"名义节点"
- **硅缩到 5nm 以下，电子迁移率和速度下降**——开启态电子也流不畅。
- 业界 2nm/1nm 多是**名义节点**：纳米片每层 7nm、堆三层，7÷3≈"2nm"；与 Intel 从单核 Pentium 转向 12/14 核同构。硅材料本身并未真正进入 2nm 时代。

### 二维半导体
- MoS₂（一个钼原子+两个硫原子）总厚约 0.65nm，仍保持电子迁移率；学术研究显示单器件性能优于硅。石墨烯研究获 2010 年诺贝尔物理学奖。
- TSMC 路线图：纳米片 → CFET → 二维过渡金属硫族化合物（TMD）。
- 卡点：CVD 制备的纯度远达不到硅的"10–12 个 9"；柔性衬底上可打印光响应"尺蠖"器件。
- 核心瓶颈一词：**良率（yield）**——数千亿晶体管的良率管理是台积电统治力的来源，新型二维材料需要全新的良率管理思路。

### ATOMIC：AI 控显微镜（详见 [[atomic-microscopy]]）
- LLM agent 控制显微镜 + Meta SAM 分割 + 无监督聚类；**零训练、无数据中心**，只靠提示词。
- 识别人眼可比准确率 99.7%（延迟 6 秒→持续下降）；能逐像素发现人眼忽略的畴界（domain boundary，本身也是缺陷）。

### AI 科学家（与 Google DeepMind 合作）
- 把 Co-Scientist 架构接入真实实验：读文献→提想法→定配方→控制仪器，端到端验证。
- 复现实验的老大难（各实验室设备结构不同）被解决：把自家设备结构喂给 AI，生成适配定制仪器的专属配方，可**一次尝试成功**。
- 目前人工环节仅剩称量前驱体/装管/密封，预计很快被机械臂替代。
- 讲者称论文中有信心表述：有可能制备出"理论预测过但从未被制备出来"的新半导体材料。

### AI 造芯
- 故意选"产业伙伴看了说是垃圾"的缺陷材料（良率 65.6%），AI 挑选无缺陷区域、让每个晶体管布局各不相同，接入洁净室设备实际造出千级晶体管阵列，良率提升约 30 个百分点。
- 由此成立初创公司（演讲前约一个月），方向：AI 原生半导体制造、yield intelligence、lab-to-fab、可能建二维材料小型试验线。
- 资金链观察："你们的钱最终都流向 NVIDIA，NVIDIA 又得付给 TSMC——制造芯片才是最花钱的环节。"

### 自生成智能（详见 [[autogenic-intelligence]]）
- RSI（递归自我改进）缺的一环：让 AI 制造自己的"大脑"（芯片）。AI 设计芯片→AI 造芯片→芯片训练 AI，数据连接成飞轮。
- "模型与芯片分离，而生物的思维与大脑从不分离"——结合后是新的硅基生命形态；命名为 Autogenic Intelligence，名字又绕回 AI，完成闭环。

### 蟹化之问
- 1916 年提出的 carcinization：海洋动物经数百万年演化趋同成螃蟹。问听众：AI+芯片会走向分化还是趋同？硅基生命有自己的"螃蟹形态"吗？

## 与 vault 的关联

- [[accelerated-computing|加速计算]]页里"通用计算的尽头（Moore's Law/Dennard scaling）"从体系结构视角谈瓶颈，本篇从**材料本身**给出同方向的印证与出路。
- [[agi-roadmap-ladder]] 谈 RSI/超级智能阶梯，本篇补上"硬件自造"这一环。
- [[nvidia]] / [[ai-capex-beneficiaries]]：讲者对资金链"NVIDIA→TSMC→制造"的拆解与 vault 已有资本流分析互证。
- [[control-point-convergence]]：yield intelligence 可能成为半导体制造环节的新控制点。

## References

- 演讲视频：https://www.youtube.com/watch?v=cmhym0OcoS8
- 文字稿：`raw/assets/youtube-cmhym0OcoS8-subs-zh.jsonl`（YouTube 官方人工中文字幕，616 段，覆盖 0:00–29:42）
- 中文长文：[[harry-wang-beyond-silicon-chips-chinese-article]]
- 嘉宾背景：Duke ECE — Haozhe "Harry" Wang（https://ece.duke.edu/people/haozhe-wang/）；ATOMIC 公开报道（Duke Pratt School of Engineering）
