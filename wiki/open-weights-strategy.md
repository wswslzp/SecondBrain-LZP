---
title: "Open Weights 作为商业策略"
tags: [ai, business, open-source, bfl]
date_created: 2026-04-18
date_modified: 2026-10-25
related: ["[[andreas-blattmann]]", "[[visual-intelligence]]", "[[sovereign-ai]]", "[[nvidia]]", "[[satya-nadella]]", "[[microsoft]]", "[[frontier-ecosystem]]", "[[sam-altman]]", "[[intelligence-as-utility]]", "[[deepseek]]", "[[restraint-as-strategy]]", "[[dhh]]", "[[dhh-lex-fridman]]", "[[lindon-gao]]", "[[dyna-robotics]]", "[[lindon-gao-dyna-xiaojun]]"]
---

# Open Weights 作为商业策略

[[andreas-blattmann]] 在 CS 153 挑战"开源 vs 闭源"的伪二元——它们是**战术**，不是宗教。开源权重在某些场景下有极强的商业价值。

## 关键判断条件

当系统的**价值依赖于消费者的定制化偏好**时，开源权重商业价值高。

### 例子 1：视觉美学
- BFL 把权重给 Meta → Meta 为 20 亿用户定制
- 给另一个政府 → 它为本地文化偏好定制
- 不同受众有不同审美 → 没法中央化

### 例子 2：语言/方言
- 中文模型在普通话上会超过西方模型
- 不同行业/地区有不同优化需求

### 什么时候**不需要**开源
- 当偏好分布窄时（所有用户喜欢差不多的东西）
- 闭源 API 更合适

## Flux 的三包策略

[[andreas-blattmann]] 的 BFL 为 Flux 1 设计了三个变体：

### 1. Flux Schnell（德语"快"）
- **全开源 Apache 2.0**
- 蒸馏到 ~4 步
- 低质量但快
- 给开源社区做本地部署

### 2. Flux Dev
- **开源权重 + 商业许可**
- 看 weights，但商业使用要付费
- 给想定制的企业

### 3. Flux Pro
- **API only**
- 高质量（更多 diffusion 步数）
- 给不想处理定制的大企业

## 同样 size，不同 step

关键 insight：在 diffusion 模型中：
- **三个变体是同样大小的模型，只是步数不同**
- 这与 LLM 不同（LLM 通常 small/medium/large distillation）
- 利用 [[distillation]] 实现不同质量/速度档位

## 商业价值来源

### 1. 信任
- 企业能看到权重 = 可审计
- 主权客户有控制权（见 [[sovereign-ai]]）

### 2. 定制化护城河
- 客户在 BFL 权重上做 fine-tuning/LoRA
- 迁移成本高 → 客户粘性

### 3. 生态系统
- Meta 合作推动 20 亿用户
- 开源社区贡献 fine-tunes、优化
- Flux 在 GitHub 的一系列实现

### 4. 商业增长
- BFL 从 0 到 $300M+ ARR
- 估值 $30 亿
- 25 人团队

## 反模式：仅开源不闭环

> "A lot of projects open models up and then they just die. That's not stable infrastructure either." — Midha

开源必须与商业 API/定制服务结合，否则不可持续。

## 与 LLM 的对比

LLM 生态：
- Meta Llama 开源 → 通用基础设施
- 但 Anthropic、OpenAI 专注闭源 API

Image/Video 生态：
- 2022 前大量开源（Stable Diffusion）
- 2024+ 中国视频模型开始**从开源转向闭源**（如 Seedance）— 担忧趋势
- BFL 坚持"有选择地开源"

## Staniszewski 的担忧

> "I hope our open source (Western) models are at least at par or better than the ones coming from China. Which I think we have a chance to do."

- 中国在 distillation 攻击上活跃
- 西方开源生态的重要性：保护定制能力
- 如果中国主导开源，未来的本地定制能力会转向他们的生态

## DeepSeek：开源作为「克制战略」的必然要求

[[liang-wenfeng|梁文锋]]/[[deepseek|DeepSeek]]（[[liang-wenfeng-investor-meeting]]）把开源从「战术」升级为**[[restraint-as-strategy|克制战略]]的必然要求**，并给出一套与 BFL 不同的、纯经济学的「开源不冲突商业」论证：

- **市场太大不可独占**：传统软件市场就几十亿美金、开源即死；但 AI 可能占**人类 GDP 的 10%**，「一个人不可能独占，你一定得跟别人分享，否则活不下来」。
- **部署门槛即护城河**：「并不是我开源了，别人就能轻易做到跟我一样的部署成本。」按**十个月回本（≈6 倍利润）**定价，就能让第三方独立部署**无利可图**——所以「6 倍利润下开源毫无影响；100 倍利润才会被影响」。
- **不留一手**：开源模型 = 自部署模型（不会开源一个差的、自己用更好的）；去年 C 端全程开源，**没看到与自营的冲突**。

与 BFL「偏好异质时开源」是不同的判断轴：BFL 讲**定制化异质性**，DeepSeek 讲**市场规模 + 成本壁垒**。二者都反对「开源 vs 闭源」的宗教式二分。

## 关键引语

> "Open vs closed is a false trade-off. They're both tactics. Open makes sense where preferences are heterogeneous." — [[anjney-midha]]

> 「我看不到闭源什么好处……我按十个月回本，就能让独立部署的第三方无利可图。所以开源并不会影响我的收入。」— [[liang-wenfeng|梁文锋]]

> "The beauty of open models is if you give away the weights and they're good general weights, you can tell Meta 'customize for your users' and another government 'customize for your culture.'" — Midha

## NVIDIA / Nemotron：开源作为生态与 co-design 策略

[[jensen-huang|Jensen]]（[[nvidia]]）给出开源的三个理由，与本页「开源是战术不是宗教」一致：
1. **co-design**——自己做模型（如 Nemotron 3 Super，120B MoE，transformer+SSM）才能看清模型架构演进方向，反哺硬件设计；
2. **扩散**——让每个行业 / 国家 / 研究者 / 学生都能加入 AI 革命，纯闭源难以在其上创新；
3. **AI 不只是语言**——生物、化学、物理、physical AI 等模态都需要有人把前沿推到极限（"we don't build cars, but we want every car company to have great models"）。

NVIDIA 把 weights + data + 训练方法**一并开源**。这与中国（DeepSeek、MiniMax）的开源文化（见 [[nvidia]] 的 China 段）共同构成对照，呼应 [[mati-staniszewski]] 对「西方开源须至少与中国持平」的担忧。

## Microsoft MAI：licensed weights（授权而非全开源）

[[satya-nadella|Satya Nadella]]/[[microsoft]]（[[cs153-satya-nadella-frontier-ecosystem]]）把 MAI 模型作为**授权权重（licensed weights）**发布——并非完全开源：在 Base10 / Fireworks / Together 上广泛授权、可 fine-tune，但以许可形式附带**可审查/安全条款**与一套经济模型；目标是让每家公司都拿到一个能自行 post-train、并**保留 IP** 的模型（即 [[frontier-ecosystem]] 所说的「hill-climbing」）。[[sam-altman|Sam Altman]]（[[cs153-sam-altman-scale]]）则把更深的赌注点为**「民主化分叉」**（他给约 80% 的概率）：是把智能作为一种公用事业（[[intelligence-as-utility]]）向外推，还是让它集中于少数公司。

## 实测：同一编码任务的成本梯度（DHH，Lex #501）

[[dhh|DHH]] 把 Python 库 TTE 用 Rust 重写成无依赖的单个可执行文件，要求逐帧像素一致，并拿同一份计划测试了多个模型（均为口述，按 token 计费的估算）（[[dhh-lex-fridman|DHH × Lex #501]]）：

| 模型 | 结果 | 成本 / 耗时 |
|---|---|---|
| Fable（后半程由 Opus 5 接手） | 完成，计划由它制定 | 约 $550 / 约 45 分钟 |
| GPT Sol | 完成 | 约 $46 / 约 1.5 小时 |
| Grok 4.6 | 完成 | 约 $55 |
| DeepSeek V4 Pro | 完成 | 约 $23 / 2 小时 45 分 |
| Kimi K3 | 完成 | 耗时很长 |
| GPT Luna、DeepSeek V4 Flash | 失败 | — |

他的结论是：拿到计划之后，开源和低价模型能以 1/10～1/20 的成本完成同样的任务，前沿模型的溢价主要体现在**规划和速度**上。开放权重模型他通过 OpenCode 加 Fireworks（美国的推理服务）来跑；在他的测试里，这些模型对敏感政治问题的回答比部分闭源模型更直接，所以他认为开源模型也是对抗审查的保障（见 [[anthropic]]）。2026 年 2 月他还说过“有 Kimi K2.5 就够了”，后来又被前沿模型拉开了差距。

## 机器人数据路线不是开源立场

DYNA 讨论的是第一人称、仿真、真机等数据组合，不是模型权重是否开放。[[product-research]] 提醒：数据手段可以阶段性变化，真正需要长期押注的是最终数据形态和产品目标。

## 来源
- [[cs153-bfl-andreas-blattmann]]
- [[cs153-elevenlabs-mati-staniszewski]]
- [[dhh-lex-fridman]] — Lex Fridman #501 DHH 访谈（2026-08-26）
- [[lindon-gao-dyna-xiaojun]] — 张小珺对 DYNA 创始人 Lindon Gao 的访谈（2026-10-15）
