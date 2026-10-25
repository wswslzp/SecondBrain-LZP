---
title: "AGI 路线图：阶梯与持续学习瓶颈"
tags: [agi, roadmap, continual-learning, agents, embodied-ai, deepseek]
date_created: 2026-07-23
date_modified: 2026-07-23
related: ["[[liang-wenfeng]]", "[[deepseek]]", "[[scaling-laws]]", "[[catastrophic-forgetting]]", "[[complementary-learning-systems]]", "[[ai-agent-memory]]", "[[tasks-vs-jobs]]", "[[agent-comfort-zone]]"]
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

## 与 vault 的关联

- **桥接整套记忆研究**：梁的「持续学习」正是 [[ai-agent-memory]] 里缺失的「自动巩固 / 再巩固」、[[catastrophic-forgetting|灾难性遗忘]] 与 [[complementary-learning-systems|CLS 互补学习系统]] 想解决的问题——人类记忆的**海马体快学 + 新皮层慢固**恰是「持续学习」的生物版本。DeepSeek 的路线图给这条学术线提供了「为什么它是 AGI 关键路径」的产业注脚。
- **[[tasks-vs-jobs]]**：梁的「AI 替代不了员工是因为缺两个月持续学习」为 [[dario-amodei|Dario]]/[[jensen-huang|Jensen]] 的 tasks-vs-jobs 之争提供了一个**技术性判据**——jobs 被替代的前提正是持续学习被攻克。
- **[[agent-comfort-zone]]**：Agent 这一级「能做很多但会走完、仍替代不了人」与立党「agent 舒适区=封闭可验证环境」互证。
- **[[scaling-laws]]**：阶梯是在 scaling「没看到墙」的前提下叠加的新范式（CoT/Agent/持续学习），与 Jensen 的「四条 scaling laws」（含 agentic scaling）可对读。
- **[[deepseek]]**：DeepSeek「下一代模型必须具备持续学习能力才算下一代」「模型首先服务自己的研发」都是这条路线图的直接推论。

## References

- [[liang-wenfeng-investor-meeting]] — 投资者交流会完整版全文（2026-07-23）
