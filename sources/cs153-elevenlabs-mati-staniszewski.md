---
title: "CS153 '26: Audio Intelligence Frontiers — Mati Staniszewski, ElevenLabs"
author: "Mati Staniszewski"
date_ingested: 2026-04-18
date_published: 2026-04-09
tags: [ai, audio, speech, voice-agents, elevenlabs, tts]
url: "https://www.youtube.com/watch?v=TnL10oBZc6U"
type: lecture-transcript
---

# CS153 '26: Audio Intelligence — Mati Staniszewski (ElevenLabs)

Stanford CS 153 第 2 周讲座。Mati Staniszewski 是 ElevenLabs 联合创始人 CEO（原 Google/Palantir）。讨论 ElevenLabs 从 Discord bot 到 $430M+ ARR 的历程与前沿音频/语音系统。

## 核心论点

音频 AI 的下一阶段是**实时交互 voice agents**。关键架构辩论：**cascaded** vs **fused**——每种都有其场景。ElevenLabs 专注企业场景（cascaded），因为可靠性 > 延迟。

## 关键要点

### 起源故事：波兰配音问题
- 在波兰，外国电影被单一的单调男声配音（同一个人读所有角色）
- 这激励两位创始人（都来自波兰）：未来任何人都应能用任何语言消费内容，保留原声的情感和语调
- 研究表明：当时的模型能创造"科学怪人"版本的配音——足够好做概念验证，但不够好发布

### 2022 年聚焦：Text-to-Speech
原本三段 pipeline（转录 + 翻译/LLM + TTS）三个组件都不够好 → 聚焦 TTS：
- **自然语感**：让声音听起来像人
- **情感控制**：角色在上下文中的情绪
- **抽象声音特征**：不是硬编码性别/口音/年龄，让模型学习

### 年度路线图 2022-2026
- **2022**：TTS 突破——上下文感知的音调
- **2023**：语言扩展、voice marketplace、创作工具
- **2024**：AI 配音 + localization（Javier Milei 联合国演讲、Lex Fridman 与 Modi/Zelenskyy 对话）
- **2025**：实时 voice agents 真正 work（Clara、Revolut、Deutsche Telekom）
- **2026**：融合 cascaded 与 fused 架构，个性化

### Cascaded vs Fused（详细讨论）

**三段 cascaded**（ElevenLabs 当前企业路线）：
```
[Speech-to-Text（转录 + 情感检测）]
    ↓
[LLM（推理 + 工具调用）]
    ↓
[Text-to-Speech（情感生成）]
```

**Fused**：一个模型端到端

### 三个评估维度

| 维度 | Cascaded | Fused |
|------|----------|-------|
| 情感质量 | 可修复 | 已有（如 Sesame CSM） |
| **可靠性** | **胜** | 输 |
| **延迟** | 输 | **胜**（~300ms） |

### 为什么企业选 cascaded
预订机票的 voice agent 需要：
1. 通过两因素认证
2. 从 email/数据库拉取客户信息
3. 处理支付认证
4. 每步可追踪（"哪个模型哪步出错了？"）

Fused 模型把这些都包起来，无法追踪 → 对关键业务不适合。

但：如果只是"what are your products"，fused 可以。**ElevenLabs 正在探索两种混合部署**。

### 情感理解的突破（2026 初）
- 以前缺少"peppy/sad/stressed"的标注数据
- 过去一年大量投资标注 pipeline
- 新版 voice agent：检测情感 → 传给 LLM 作为上下文 → 合成对应情绪响应
- 与 Sesame（Brendan Iribe，前 Oculus CEO）竞赛"情感图灵测试"

### 与 Sesame 的协作
**非竞争的文化**：
- Midha 曾在 Discord 面对同样问题，请教 Staniszewski
- Staniszewski 倾囊相授，最终 Brendan（Sesame 创始人）成为 ElevenLabs 天使投资人，反之亦然
- Sesame 2024 年开源了 CSM（Conversational Speech Model）
- "You can go further together, especially in a new space"

### 小团队 + 大 ownership 文化
- 450 人公司
- 每个团队 <10 人
- 大 mandate，独立决策权
- "速度理解客户/问题 > 职业进程"

### Value-based pricing
- 从你给客户带来的价值反推
- 目标：抓住提供价值的 ~10%
- **不要从成本出发**

### 可预测的部署引擎
- ElevenLabs 收入增长按**部署**规模可预测
- vs Anthropic 按**compute**可预测
- >50% 收入来自企业，<50% PLG
- Q1 2026 增加了 $100M+ ARR（总 ARR $430M+）

### 安全与身份验证
- 所有生成内容可追溯
- 水印 + 公开可用检测器
- **反对用语音做银行认证**——这是错误的安全模型
- 反诈骗：让 voice agent 浪费诈骗犯的时间

### 为失声者恢复声音
- ~10,000 ALS、喉癌等患者
- 合成他们失去的声音
- "我们做的最自豪的工作之一"

### 乌克兰政府案例
- 战争中政府服务无法正常运作
- 为 Diia app（中央公民应用）加入语音接口
- 没有互联网的人可以打电话获得政府信息
- 每个部委有自己的技术资源 → 绕过繁文缛节快速部署

### 中国生态观察
- 面对来自中国模型的 distillation 攻击
- 中国模型在其语言/方言上会更好 → 无法竞争
- 视频模型（如 Seedance）从开源转向闭源——担忧趋势
- 对西方开源生态的重要性：**需要保持开源以支持定制**

### 5 年愿景
- 类似云市场（3-4 大云）一样，会有 **3-5 个会话 AI 平台**
- ElevenLabs 要做其中一个
- 平台与应用边界模糊化：任何人都可以在平台上做"一人企业"

### 设备端部署
- 刚找到方法把模型上设备
- 策略：**先做好质量，再考虑设备端**
- 不做"低质量的设备端"妥协

## 关键引语

> "The speed in understanding the customer is much more important than a career process."

> "Always think about the value you deliver to the customer and work backwards. Never from cost."

> "Voice authentication in banking is not the future. That's the wrong approach."

> "For enterprises, reliability > latency. That's why cascaded will win for the next few years."

## 相关页面
- [[mati-staniszewski]]
- [[audio-intelligence]]
- [[cascaded-vs-fused-architectures]]
- [[unified-models]]
- [[multimodal-ai]]
- [[frontier-systems]]
