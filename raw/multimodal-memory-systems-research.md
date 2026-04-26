# 多模态记忆系统调研

> 调研日期：2026-04-26
> 问题：AI 记忆系统是否已经超越纯文本/向量，支持图像、音频、视频等多模态？

---

## 一、核心发现

**答案是肯定的**——2025-2026 年已经出现了一批真正的多模态记忆系统，不再只是"把图片转成文字再存"，而是原生支持多模态编码、存储和检索。

这个领域正在经历三个范式转变：
1. **文本记忆 → 多模态记忆**：从只记对话文本，到能记住图像、音频、视频
2. **被动存储 → 主动巩固**：从简单 RAG 检索，到有遗忘和巩固机制
3. **单 Agent → 记忆操作系统**：从单一记忆工具，到统一的记忆管理层

---

## 二、项目全景图

### 🏆 Tier 1：原生多模态记忆系统

#### 1. SimpleMem / Omni-SimpleMem
- **论文**: arXiv:2604.01007 (2026-04)
- **GitHub**: [aiming-lab/SimpleMem](https://github.com/aiming-lab/SimpleMem) ⭐3,200 | MIT
- **模态**: 文本 + 图像 + 音频 + 视频
- **架构**: 三阶段管线
  - Semantic Structured Compression — 将交互蒸馏为紧凑索引单元
  - Online Semantic Synthesis — 写入时实时巩固
  - Intent-Aware Retrieval Planning — LLM 驱动的三层索引检索（dense向量 + BM25稀疏 + 符号元数据）
- **Omni 扩展**: 熵驱动的选择性摄入 + FAISS+BM25 金字塔渐进检索 + 知识图谱增强跨模态推理
- **性能**: LoCoMo F1 0.613 (+411%)，Mem-Gallery F1 0.810 (+214%)，检索速度3.5×
- **安装**: `pip install simplemem`，支持 Claude / Cursor / LM Studio

#### 2. MemOS（记忆操作系统）
- **论文**: arXiv:2507.03724 (2025-07)
- **GitHub**: [MemTensor/MemOS](https://github.com/MemTensor/MemOS) ⭐8,700 | Apache-2.0
- **模态**: 文本 + 图像 + 工具痕迹 + 人设
- **架构**: **MemCube** 抽象统一三种记忆形式：
  - 明文记忆（plaintext）
  - 激活记忆（activation-based）
  - 参数记忆（parameter-level）
- 记忆可组合、可迁移、可融合；后端 Neo4j + Qdrant
- **性能**: 准确率比 OpenAI Memory +43.70%，Token 节省 35.24%
- **定位**: 不是一个记忆工具，而是记忆的"操作系统"——类似于 Linux 之于进程管理

#### 3. M3-Agent（字节跳动 Seed）
- **论文**: arXiv:2508.09736 (2025-08) — **ICLR 2026**
- **GitHub**: [bytedance-seed/m3-agent](https://github.com/bytedance-seed/m3-agent) ⭐1,300 | Apache-2.0
- **模态**: 视频帧 + 音频 + 文本
- **架构**: 双进程设计
  - **记忆化进程**: 在线处理视频/音频流 → 构建实体中心的多模态记忆图（情景记忆 + 语义记忆）
  - **控制进程**: 多轮迭代推理 + 记忆检索执行指令
- 通过强化学习训练，基于 Qwen2.5-Omni-7B
- **性能**: 超过 GPT-4o / Gemini-1.5-Pro +6.7-8.2%

#### 4. MemVerse
- **论文**: arXiv:2512.03627 (2025-12)
- **GitHub**: [KnowledgeXLab/MemVerse](https://github.com/KnowledgeXLab/MemVerse) ⭐138
- **模态**: 文本 + 图像 + 音频 + 视频
- **架构**: 受 Kahneman 快/慢思维启发的双通道设计
  - **慢通道**: 分层检索记忆（短期滑动窗口 + 长期多模态知识图谱，含核心/情景/语义三类型）
  - **快通道**: 轻量参数记忆（Qwen2.5-7B 微调）
  - Memory Orchestrator 统一调度
- 多模态输入通过预训练 MLLM 转换后存储
- **性能**: MSR-VTT 文本→视频 R@1 90.4%，ScienceQA 85.48%，Token 节省 90%

#### 5. MIRIX
- **论文**: arXiv:2507.07957 (2025-07) — 79 citations
- **模态**: 文本 + 视觉（高分辨率截屏，约 20,000 张/序列）
- **架构**: 6 种记忆类型协调的多 Agent 框架
  - Core Memory（核心）
  - Episodic Memory（情景）
  - Semantic Memory（语义）
  - Procedural Memory（程序）
  - Resource Memory（资源）
  - Knowledge Vault（知识库）
- 实时屏幕监控 + 本地存储
- **性能**: 比 RAG 基线 +35% 准确率，存储压缩 99.9%，LOCOMO 85.4% SOTA

#### 6. TeleMem
- **论文**: arXiv:2601.06037 (2025-12, revised 2026-01)
- **模态**: 文本对话 + 视频 + 音视频流
- **架构**: 
  - Narrative Dynamic Extraction（防幻觉）
  - Structured Writing Pipeline（批处理/聚类/巩固）
  - Multimodal Memory Module + ReAct 推理（observe→think→act）
- **性能**: 比 Mem0 准确率 +19%，Token 减少 43%，速度 2.1×

---

### 📱 Tier 2：屏幕/感知级记忆系统

#### 7. Screenpipe（"开源 Rewind"）
- **GitHub**: [screenpipe/screenpipe](https://github.com/screenpipe/screenpipe) ⭐18,400 | MIT
- **模态**: 屏幕截图（视觉/OCR）+ 系统音频 + 麦克风 + 键盘输入
- **架构**: 持续事件驱动的屏幕+音频捕获 → 本地存储 → AI 语义搜索
  - OCR + 无障碍树提取文本
  - Whisper 语音转写
  - 语义嵌入检索
  - 插件系统（"Pipes"）+ MCP Server
- **资源**: 5-10% CPU，0.5-3GB RAM，~5-10GB/月存储
- **定位**: Rewind.ai / Microsoft Recall 的开源替代

#### 8. Rewind AI / Limitless
- **类型**: 商业产品
- **模态**: 屏幕（5-10 FPS）+ 音频（16kHz）+ 文本
- **技术栈**: CLIP-ViT 嵌入 + Whisper 语音 + OCR，存储在本地 LanceDB 向量数据库
- **硬件**: Limitless Pendant 可穿戴设备（100h 电池，波束成形音频，声纹识别）
- **性能**: 92% top-1 检索准确率，320ms 搜索延迟
- **值得关注的风险**: 认知萎缩——如果海马体不再需要编码，会退化吗？（类似 GPS 削弱空间导航能力）

#### 9. Google Vertex AI Memory Bank
- **类型**: 托管云服务（ADK 框架开源）
- **模态**: 文本 + 图像 + 视频 + 音频
- **架构**: 使用 Gemini 处理多模态文件，提取结构化"记忆"；按主题组织；gemini-embedding-001 语义搜索

---

### 🧭 Tier 3：具身/导航 Agent 的多模态记忆

#### 10. VideoAgent (ECCV 2024, 220 citations)
- 视频事件时序 + 对象跟踪，统一结构化记忆

#### 11. CMMR-VLN (2026-03)
- 全景视觉图像 + 地标索引的多模态经验记忆，成功率比 NavGPT +52.9%

#### 12. MAGNet/SAVN-CE (CVPR 2026)
- 双耳音频 + 视觉在连续3D空间中的记忆增强目标推理，开源 ✅

#### 13. ReMA — Recursive Multimodal Agent (2026-03)
- 视频（181.1小时）+ 多模态终身流，递归信念状态更新

#### 14. NS-Mem (2026-03)
- 三层神经符号架构：情景 + 语义 + 逻辑规则，混合检索

---

### 🔬 Tier 4：基础研究 / 跨模态绑定

#### 15. ImageBind（Meta AI, CVPR 2023）
- 六模态统一嵌入空间（图像/文本/音频/深度/热/IMU）
- 以图像为锚点模态——类似大脑以视觉为空间绑定中心
- 跨模态检索 + 模态算术 + 零样本识别

#### 16. 脑科学多感官整合研究
- **神经相干性模型** (Engel 2012): γ 波段振荡 (>30Hz) 实现跨模态绑定
- **多时间尺度动力学** (Nature Rev Neurosci 2024): δ 到 γ 多频段同步，α 频率决定时间绑定窗口
- **三大原则**: 空间规则 + 时间规则 + 反向有效性（最弱单模态刺激产生最强多感官增强）
- **贝叶斯推断**: 大脑按可靠性加权各模态

---

### 📊 重点比较：文本记忆 vs 多模态记忆

| 对比维度 | Mem0 (文本代表) | SimpleMem (多模态代表) | MemOS (OS级代表) |
|---|---|---|---|
| **Star 数** | 54.1K | 3.2K | 8.7K |
| **模态** | 文本为主 | 文本+图像+音频+视频 | 文本+图像+工具+人设 |
| **存储形式** | 向量 + 图 | 三层索引（向量+稀疏+符号） | MemCube（明文+激活+参数） |
| **巩固机制** | 单次 ADD 提取 | 在线语义合成 | 可组合/迁移/融合 |
| **遗忘** | ❌ 无 | 熵驱动选择性摄入 | ❌ 无 |
| **LoCoMo F1** | 91.6 (v3) | 61.3 (Omni) | N/A |
| **许可证** | Apache-2.0 | MIT | Apache-2.0 |

---

## 三、与 Hermes 当前系统的对比

| 维度 | Hermes 现状 | 多模态记忆前沿 |
|---|---|---|
| **支持模态** | 纯文本（Memory/Hindsight/Sessions/Skills 全是文本） | 文本+图像+音频+视频+屏幕 |
| **图像记忆** | ❌ 无——能看图但不记住图 | ✅ CLIP/MLLM 嵌入后存储检索 |
| **音频记忆** | ❌ 无——能听/说但不记住声音 | ✅ Whisper 转写 + 音频嵌入 |
| **结构化程度** | 自由文本片段 | 语义图/知识图谱/MemCube |
| **检索融合** | 各子系统独立检索 | 多信号融合（向量+稀疏+符号+图） |
| **巩固/遗忘** | ❌ 无 | 部分有（SimpleMem 在线合成, MemVerse 蒸馏） |
| **可扩展性** | Memory 2.2KB 硬限制 | 自适应增长+压缩 |

### Hermes 理论上可以做但没做的

1. **图像记忆**: Hermes 有 `vision_analyze` 工具能理解图片 → 可以把分析结果存入 Hindsight，但目前不会自动做
2. **音频记忆**: Hermes 有 TTS 和语音消息能力 → 但不记忆音频内容
3. **屏幕记忆**: Hermes 有 `browser_vision` 能截屏分析 → 但截图用完即弃
4. **跨模态关联**: 理论上可以通过 SecondBrain wiki 的 wikilinks 做简单关联，但不是自动的

---

## 四、技术路线分析

### 路线 A：嵌入统一（ImageBind 式）
- 所有模态投射到同一向量空间
- 优势：跨模态检索天然支持
- 劣势：高维嵌入存储成本大，解释性差

### 路线 B：转写归一（MemVerse 式）
- 多模态输入通过专用模型转为文本/结构化描述后统一存储
- 优势：复用现有文本记忆基础设施
- 劣势：信息损失（颜色、语调、空间关系等难以文本化）

### 路线 C：MemCube 多形态（MemOS 式）
- 不同模态用不同最优形式存储，通过统一接口管理
- 优势：每种模态保持原生表示
- 劣势：架构复杂度高

### 路线 D：持续捕获（Screenpipe 式）
- 记录一切，事后 AI 索引
- 优势：零遗漏
- 劣势：隐私、存储、噪声

### 对 Hermes 最可行的路线：**B + 部分 A**
- 短期：用现有 MLLM 能力将图像/音频转为文本描述后存入 Hindsight（路线 B）
- 中期：为关键多模态内容生成嵌入并存储原始文件引用（路线 A 补充）
- 这能在不重构架构的前提下获得 60-70% 的多模态记忆能力

---

## 五、关键洞察

### 脑科学启示
1. **大脑的多感官记忆不是分开存的**——走进森林，你记住的不是"视觉绿色+听觉鸟叫+嗅觉松木"的三个独立条目，而是"在森林里"这个统一体验
2. **γ 振荡是绑定机制**——不同感官皮层通过 >30Hz 同步来"绑定"。当前 AI 多模态系统用静态嵌入替代，缺少时间绑定窗口
3. **反向有效性原则**——最弱的单模态信号产生最强的多感官增强。这意味着模糊的图像 + 模糊的声音 → 比清晰图像单独更好的记忆。AI 系统普遍忽略了这一点

### 产业趋势
1. **MemOS 的 8.7K Star 说明需求爆发**——社区需要的不是又一个 RAG，而是记忆的"操作系统"
2. **Screenpipe 的 18.4K Star 说明"记住一切"有市场**——但隐私是最大阻力
3. **Google 入场了**——Vertex AI Memory Bank 意味着多模态记忆即将成为云平台标配
4. **认知萎缩风险**——如果 AI 替你记住一切，你的海马体是否会退化？这已经从理论风险变成了 Limitless 用户反馈的真实关切

---

## 六、推荐关注的项目（按可操作性排序）

| 优先级 | 项目 | 理由 |
|---|---|---|
| 🔴 最值得研究 | **MemOS** ⭐8.7K | 记忆操作系统概念最成熟，MemCube 抽象优雅 |
| 🔴 最值得研究 | **SimpleMem** ⭐3.2K | 真正的多模态 SOTA，MIT 开源，pip 可装 |
| 🟡 值得跟踪 | **M3-Agent** ⭐1.3K | ICLR 2026，字节跳动出品，视频+音频记忆 |
| 🟡 值得跟踪 | **Screenpipe** ⭐18.4K | 如果想给 Hermes 加"全记录"能力 |
| 🟢 长期关注 | **MIRIX** | 6 种记忆类型协调，最接近完整认知架构 |
| 🟢 长期关注 | **ImageBind** | 六模态统一嵌入，基础研究价值高 |

---

## References

- SimpleMem: https://github.com/aiming-lab/SimpleMem | arXiv:2604.01007
- MemOS: https://github.com/MemTensor/MemOS | arXiv:2507.03724
- M3-Agent: https://github.com/bytedance-seed/m3-agent | arXiv:2508.09736
- MemVerse: https://github.com/KnowledgeXLab/MemVerse | arXiv:2512.03627
- MIRIX: arXiv:2507.07957
- TeleMem: arXiv:2601.06037
- Screenpipe: https://github.com/screenpipe/screenpipe
- Mem0: https://github.com/mem0ai/mem0 | arXiv:2504.19413
- ImageBind: arXiv:2305.05665
- VideoAgent: arXiv:2403.11481
- Neural Coherence: NCB Bookshelf (Engel 2012)
- Multi-timescale Dynamics: Nature Reviews Neuroscience (2024)
- Memory in the Age of AI Agents (Survey): arXiv:2512.13564
