---
title: "AGI 路线图：阶梯与持续学习瓶颈"
tags: [agi, roadmap, continual-learning, agents, embodied-ai, deepseek]
date_created: 2026-07-23
date_modified: 2026-10-29
related: ["[[liang-wenfeng]]", "[[deepseek]]", "[[scaling-laws]]", "[[catastrophic-forgetting]]", "[[complementary-learning-systems]]", "[[ai-agent-memory]]", "[[tasks-vs-jobs]]", "[[agent-comfort-zone]]", "[[yu-su]]", "[[yu-su-xiaojun-agent-history]]", "[[haozhe-wang]]", "[[harry-wang-beyond-silicon-chips]]", "[[vitalik-buterin]]", "[[effective-altruism]]", "[[d-acc]]", "[[silicon-valley-101-vitalik-ea-ai-safety]]", "[[gpt-6-astra]]", "[[huazhe-xu]]", "[[zheqing-zhu]]", "[[sheng-wang]]", "[[wet-lab-verification-loop]]", "[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]"]
---

# AGI 路线图：阶梯与持续学习瓶颈

**[[liang-wenfeng|梁文锋]]** 在 [[liang-wenfeng-investor-meeting|投资者交流会]]给出的 AGI 技术路线——他称「其实 AGI 这条路线图是比较清晰的」，是一个**阶梯（每一步都建立在前一步上，「没有一步是白走的」）**：

```
语言模型 → CoT（去年）→ Agent（今年）→ 持续学习（下一个瓶颈）
        → 自我迭代的奇点（渐进/非线性）→ 具身智能
```

## 阶梯的每一级

| 阶梯 | 状态 | 说明 |
|---|---|---|
| **语言模型** | 已完成 | 一切的地基 |
| **CoT（思维链）** | 去年走完 | 自己思考抬高上限；已在奥数/编程上**超过最顶尖人类**——但仍不是 AGI，会停在那里 |
| **Agent** | 今年在走 | 能做更多事、能力范围更大；但**它也会走完**，走完后仍替代不了员工 |
| **持续学习** | 下一个瓶颈 | 必须跨过去的墙（见下） |
| **自我迭代奇点** | 之后 | 模型能自己开发下一版；**渐进非突变**、因 AI 加速 AI 研究而**非线性**、无临界点 |
| **具身智能** | 终点 | 走进现实世界做家务、养老；「对一个正常人，他需求的不是电脑」 |

## 为什么「持续学习」是当前的墙

梁的核心论证——**给它完整上下文 + 指令，当前 AI 已超过人类，但「给完整上下文」极难**：

> 招一个员工，他花**两个月**熟悉公司环境就能上手，你说「叫小王来」他就知道小王是谁。但 AI **前面没有这两个月的学习**——你得告诉它小王是谁、什么职务、在哪、怎么找。你不可能给它所有上下文，所以 **AI 替代不了你的员工**。

- 差的就是这一步：**像人一样做长时间的持续学习**（continual learning），而非一次性强训练。
- **「AI 现在不缺品味和直觉，它缺的是持续学习的能力。」**——把瓶颈从「智能」精确地移到「学习」。
- 全世界都还没找到 work 的方法（对应国外热词 **recursive self-improvement**）；「学习不是一项技术，是一个问题，会由很多东西组成」，既是算法也是工程问题。
- **顺序选择**：先持续学习 → 奇点 → 具身，是「最轻松、不用加班」的路径（后面能用前面的技术开发）；反过来先做具身会「很苦、数据密集、人力密集」。

## 苏煜视角：持续学习的内容是小世界的世界模型

[[yu-su|苏煜]]（[[yu-su-xiaojun-agent-history|张小珺 #139]]，2026-05）把梁文锋说的「两个月熟悉环境」写成可操作的学习目标：不是再堆通用智能，而是学会一个微世界的模型——谁说了算、工作流、软件操作的后果、他人心智。结果是可靠性、速度和成本，不是又一个基准分数。

⚠️ 张力：梁把自我迭代奇点放在持续学习之后，并说它渐进、无临界点。苏煜看不到可预见的未来里 AI 会因原生目标和生存压力去取代人类；他担心的是岗位置换快过新岗位和再分配。两边都把持续学习当成墙，对墙后面是什么判断不同。并列保留。

## 与 vault 的关联

- **桥接整套记忆研究**：梁的「持续学习」正是 [[ai-agent-memory]] 里缺失的「自动巩固 / 再巩固」、[[catastrophic-forgetting|灾难性遗忘]] 与 [[complementary-learning-systems|CLS 互补学习系统]] 想解决的问题——人类记忆的**海马体快学 + 新皮层慢固**恰是「持续学习」的生物版本。DeepSeek 的路线图给这条学术线提供了「为什么它是 AGI 关键路径」的产业注脚。
- **[[tasks-vs-jobs]]**：梁的「AI 替代不了员工是因为缺两个月持续学习」为 [[dario-amodei|Dario]]/[[jensen-huang|Jensen]] 的 tasks-vs-jobs 之争提供了一个**技术性判据**——jobs 被替代的前提正是持续学习被攻克。
- **[[agent-comfort-zone]]**：Agent 这一级「能做很多但会走完、仍替代不了人」与立党「agent 舒适区=封闭可验证环境」互证。
- **[[scaling-laws]]**：阶梯是在 scaling「没看到墙」的前提下叠加的新范式（CoT/Agent/持续学习），与 Jensen 的「四条 scaling laws」（含 agentic scaling）可对读。
- **[[deepseek]]**：DeepSeek「下一代模型必须具备持续学习能力才算下一代」「模型首先服务自己的研发」都是这条路线图的直接推论。

## 嘉宾视角：RSI 缺的一环是硬件自造（2026-10-27）

[[haozhe-wang|Harry Wang]]（杜克大学）在硅谷101 Alignment 2026 上提出 [[autogenic-intelligence|自生成智能]]：RSI/超级智能叙事缺了"让 AI 制造自己的大脑（芯片）"这一环——AI 设计芯片→AI 造芯片→芯片训练 AI，构成模型与硬件互造的飞轮。⚠️ 张力：本页强调的墙是**软件侧**（持续学习），而 Harry 把瓶颈引向**制造侧**（材料、良率）——两个视角对"下一堵墙在哪"给出不同答案，可并列保留。

## 嘉宾视角：RSI 带来的“认知论幼儿园危机”与 Neuralese 转向（Vitalik & Afra，2026-10-29）

在《硅谷101》E257 期（[[silicon-valley-101-vitalik-ea-ai-safety]]）中，科技记者 Afra 与 [[vitalik-buterin|Vitalik Buterin]] 对阶梯上的 **CoT（思维链）** 与 **自我迭代（RSI）** 给出了来自硅谷安全圈的一线补充：

- **RSI 加速与“没有大人的幼儿园”**（Afra）：在参加完伯克利 The Curve 与 Progress Conference 并访谈十余位 OpenAI、Anthropic 研究员后，多位研究员表示过去一年 AI 的进步速度**超出了他们原本的预期**；随着数据中心大规模建设，低垂的果实仿佛无穷无尽，使她对 RSI（递归自我改进）进化曲线深感忧虑。最大的困境是**认知论危机**——连造出模型的研究员自己也无法用日常语言或数学方法解释清楚模型到底有多强、想干什么，“就像一间满是哇哇大哭小孩的幼儿园里没有一个大人”。
- **从英文 CoT 到 Neuralese（神经语言）的不可解释风险**（Vitalik）：四年前人们并未预料到 AI 下一阶段会通过思维链（Chain of Thought）突破；目前 CoT 仍用英文思考，人类尚能阅读和审计（尤其在开源模型上）。但下一个巨大不确定性是 **Neuralese（神经语言）**——如果模型不再用自然语言推理，而是直接用数百万个数字在潜空间思考，人类理解其内部意图的能力将大幅下降。详见 [[rationalism-and-ai-safety]]。

## 嘉宾视角：从“场景过拟合”到“一个月学成医生”，以及具身落地的 2028 时间表（硅谷101 E256，2026-10-20）

《硅谷101》E256 期（[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]）的三位嘉宾针对本页阶梯中的 **CoT → Agent → 持续学习 → 具身智能** 提供了 2026 年 9 月底的一线进展校准：

- **持续学习的定量化表述**（[[zheqing-zhu|朱哲清]]）：完全呼应梁文锋“员工花两个月熟悉环境”的判据——朱哲清指出，当前号称逼近 AGI 的大模型只是在固定场景上做 **Overfitting（过拟合）**，真正的通用智能应能模拟人类从零学习：**让一个欠拟合的基础模型通过 1 个月的环境交互达到人类基础医生水平，3 个月交互达到某领域教授水平**。目前模型离这种自主迭代学习还差得很远。
- **CoT 在具身控制上的“45 分钟常数”瓶颈**（[[huazhe-xu|许华哲]]）：[[gpt-6-astra|GPT-6 Astra]] 的加密长 CoT 虽首次打通了低层机器人动作反思，但缺少持续学习向快系统（System 1）的巩固——重复做同一件事，第 3 次以后耗时永远卡在 **45 分钟常数**，无法越练越快。
- ⚠️ **张力：具身智能是“终点”还是“18 个月内进家庭”？** 梁文锋将具身智能放在持续学习与奇点之后的终点；而许华哲在实测 Astra 的跨本体泛化与自研快系统后给出激进预测：**2028 年初（约 18 个月后）** 通用机器人即可进入家庭，通过语言指令完成 90% 的家务。

## References

- [[liang-wenfeng-investor-meeting]] — 投资者交流会完整版全文（2026-07-23）
- [[yu-su-xiaojun-agent-history]] — 张小珺 #139 苏煜（2026-05-01，本地 ASR，未校对）
- [[harry-wang-beyond-silicon-chips]] — 硅谷101 Alignment 2026 Keynote：Harry Wang 谈超越硅的下一代芯片与自生成智能（2026-10-27）
- [[silicon-valley-101-vitalik-ea-ai-safety]] — 《硅谷101》E257 对话 Vitalik Buterin 与 Afra：AI安全背后的哲学思想与有效利他主义（2026-10-29）
- [[silicon-valley-101-gpt6-astra-agent-robotics-pharma]] — 《硅谷101》E256 Agent、机器人与制药，谁先被GPT-6 Astra改写？（2026-10-20）
