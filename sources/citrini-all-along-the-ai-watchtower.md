---
title: "All Along the AI Watchtower（AI 瞭望塔全程）"
author: "Citrini Research（笔名 Citrini Semis）"
date_ingested: 2026-07-21
date_published: 2026-07-20
tags: [investing, ai-capex, semiconductors, cybersecurity, sovereign-ai, meta, qualcomm, equity-research]
url: ""
---

# All Along the AI Watchtower

**[[citrini-research|Citrini Research]]** 的付费主题投研长文（2026-07-20）。原文英文，本 vault 收录的是一份**中英对照译版**（图片水印显示经由微信公众号转载，含大量图表截图）。技术形态特殊：一份 **iPhone（iOS 18.3.2）导出的"长截图"PDF**——单页高 34604pt、宽 212pt、含 164 张拼接图、**无文字层**，靠**渲染切片 + 视觉 OCR** 读取（见新建的 `pdf-ocr` skill）。文末声明：仅供信息参考，不构成投资建议。

## 一句话

借鲍勃·迪伦《All Along the Watchtower》起兴——AI 价值链上人人都想给「整块饼」定价，却无人真正知其价值；近期回调不是「开源替代 / 成本竞争 / Kimi3 / 地缘冲突」能解释的，而是**高杠杆、拥挤的 AI 交易自身的脆弱性**（"the unwind generally mirrors the vigor of the ascent"）。作者要找的是**被错误归类、定价错误（mispriced / put in the wrong category）的受益标的**，围绕 **AI 资本开支正在往哪里重新导流**展开四个主题。详见综合页 [[ai-capex-beneficiaries]]。

## 四个主题（关键 takeaways）

### 1. 高通（[[qualcomm|Qualcomm / QCOM]]）——把约束变成优势的移动芯片商
- 先辟谣了自家关于「高通×[[anthropic|Anthropic]] 合作」的传闻报道（隐藏 HTML，双方否认后撤稿）。
- **投资者日（6/24）**：FY29 非手机营收指引从 **$22B 上调至 $40B**，近乎翻倍。
- 主线是数据中心的 **HBC（High Bandwidth Compute）** 架构——LPDDR + 近存计算，处理器经硅通孔堆叠在内存正下方，绕开 HBM，**2027 面世**。宣称对比 HBM **6x 带宽/瓦**、对比 SRAM **200x 容量/瓦**、**4-8x** 解码性能/瓦与 TCO、聚合 **133 TB/s**（详见 [[memory-wall]]）。
- 路线图 **AI200（2026）→AI250→AI300**，2028 出 CPU；Alphawave（SerDes/光学 DSP/CXL-UCIe/chiplet）、两个超大规模定制硅项目 FY27 起贡献、**Meta 多代 CPU 协议（C1000，2028 H2 量产）**、收购 **Modular** 补软件可移植层。
- 上行期权：汽车（Q1 $1.33B/+38%，$65B 管道）、IoT（~$14B）、消费 AI（[[ar1-plus-chip|Snapdragon AR1]] 进 [[meta-ray-ban-glasses|Ray-Ban/Oakley Meta 眼镜]]，单副 BOM ~$50-60，~$14 亿营收潜力）、机器人（Dragonwing IQ10，~$8 亿）。对标 **MediaTek（2454 TT）** 的 TPU/数据中心 re-rating。

### 2. 构建者工具包（The Builder's Toolkit）
价值在「基础设施/模型/应用」各层如何分配（Citrini 2025-04 的 **Phase 2** 框架：Data / Design / Deployment / Distribution）。个股论点：
- **软件仓库 GitLab（GTLB）**：从「记录系统」转向「治理执行」；定价从按席位转向**按用量**（GitLab Flex / Orbit 平台 / Credits / Duo Agent Platform）。对比 JFrog（FROG）。
- **DBaaS MongoDB（MDB）**：「加热工作集」——智能体对状态持续读写，Atlas 消费级定价（list price 自 2020 未变）自动把 workload 转成收入；增速重回 **29%**、破 **$2B** 年化。风险：编码智能体默认 Postgres/Supabase/Neon/pgvector、CSP 捆绑。
- **Elastic（ESTC）**：「索引是副本而非指针」，混合检索（语义+关键词+权限+时效）；FY26 营收 +17%、cRPO +20%，但 FY27 指引 ~14% 减速。
- **设计 Figma（FIG）**：手工艺式 AI，46% YoY / 139% NRR；设计循环≈「ask→retrieve→reason→act→update」。
- 定价范式转变本身独立成页：[[usage-based-pricing]]。

### 3. 企业支出：安全且自主（Secure and Sovereign）
- **IBM 7/14 预警**：客户在 6 月最后几周把资本开支转向**服务器/存储/内存 + 网络安全**（"secure supply-constrained infrastructure ahead of expected price increases" + "industry-wide cybersecurity concerns"）。CEO Arvind Krishna 转述客户："Mythos 让人停下来问：我到底要在网络安全上投入多少？"
- **安全**：[[anthropic|Anthropic]] 的 **[[project-glasswing|Project Glasswing]]** 网络安全联盟——Mythos Preview 发布后数千个零日漏洞被揭（27 年 OpenBSD bug、FFmpeg、Squid），CISO 不会把模型与防御押在同一供应商；联盟含 PANW/CSCO/CRWD/NET，6 月扩至 Okta/Rubrik/Netskope。
- **物理安全**：Fortinet（FTNT，FortiASIC：NP7/CP9/SP5，硬件即护城河，OT 安全 ~70% billings 增长）；Yubico（YUBICO SS，瑞典，YubiKey，与 [[openai|OpenAI]] 的 Trusted Access for Cyber(TAC) 合作，YaaS）。
- **数据安全**：DLP + DSPM；Rubrik（收 Laminar）、Commvault（收 Satori）、Veeam/Securiti（$1.7B）、Cohesity/Cyera、并购目标 Varonis（VRNS）。
- **AI 主权**（详见 [[sovereign-ai]]）：[[satya-nadella|Nadella]] 「为智能付两次费」；Microsoft 因成本停用内部 [[claude-code|Claude Code]]；**Palantir（PLTR）× [[nvidia|Nvidia]] 「AI 的未来在本地」** 主权 AI OS 参考架构（Nemotron + Dell PowerEdge R670，$5-70M/套）；工作负载回流本地（Dropbox「魔法口袋」、GEICO、37signals、Barclays 88% CIO），受益者 Dell/HPE/联想(992 HK)/富士通(6702 JP)/NetApp/F5(FFIV)/Nutanix。作者产出「企业安全与主权篮子」。

### 4. PEMDAS —— Please Excuse Meta's Determined AI Spending
把 **[[meta-ai-ad-flywheel|Meta / META]]** 类比谷歌：自有一体化用户 + 无云积压，能把 GPU **立即**转成 P&L 收入（"the right order of operations"）。
- **MSL（Meta Superintelligence Labs）** + Scale AI 人才（Alexandr Wang）带来 RL 数据优势；Muse Spark 1.1 在 HealthBench Professional 拿 **0.656**（压 GPT-5.6 Sol / GPT-5.5 / Opus 4.8），且是「最便宜的高质量闭源模型」（定价优于 Grok）。
- **模型变现三件套**（GPU 优化广告）：Advantage+（自动化+创意生成）、Andromeda（检索，围绕 Grace Hopper 协同设计，模型容量 10,000x、推理效率 10x、检索召回 +6%、广告质量 +8%）、GEM/Adaptive Ranking。Advantage+ 使 ROAS **+22%**、转化 **+7%**。
- 进军 **CTV**（$40-50B 空间，与 Magnite/FreeWheel/电视厂商洽谈）；「现金→算力→广告收入→算力」飞轮；3 年内消化近 **14GW**，「必须成为云平台」是安抚投资者的烟雾弹。

## OCR 可信度说明
文中大量具体数字/基准分/股票代码由视觉 OCR 读取，个别可能有细微误读（如 133 TB/s、$45.2B、6702 JP、HealthBench 0.656 等）。关键数字如需引用，可用 `pdf-ocr` skill 重渲对应切片复核（源文件 [raw/All Along the AI Watchtower_Citirni.PDF](../raw/All%20Along%20the%20AI%20Watchtower_Citirni.PDF)）。

## 与 vault 的关联
- 首次系统落地一份**卖方/主题投研**视角，与 vault 既有的 [[jensen-huang-lex-fridman|Jensen]]、[[cs153-satya-nadella-frontier-ecosystem|Nadella]]、[[inside-anthropic-the-circuit|Anthropic]] 等一手素材互为印证——尤其 **Mythos**：[[anthropic]] 页早已把它记为「能击穿网络安全墙的 super weapon」，本文给出其市场层面的连锁反应（[[project-glasswing]]）。
- **AI 主权**从「国家层面数据不出境」扩展到「企业层面 repatriation + on-prem 硬件受益链」，大幅充实 [[sovereign-ai]]。
- **内存墙 / 近存计算**与 [[llm-inference-systems]]（KV cache、显存墙）、[[token-economics]] 直接接续。
- Meta 广告飞轮与 [[nvidia|Nvidia]] 的 extreme co-design、[[meta-ray-ban-glasses]] 消费硬件线交叉。
