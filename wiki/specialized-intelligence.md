---
title: "专门化智能（Specialized Intelligence）"
tags: [ai-agents, continual-learning, world-model, concept, reliability]
date_created: 2026-10-25
date_modified: 2026-10-25
related: ["[[yu-su]]", "[[neocognition]]", "[[language-agent]]", "[[agi-roadmap-ladder]]", "[[ai-agent-memory]]"]
---

# 专门化智能（Specialized Intelligence）

[[yu-su|苏煜]] 用来对抗“再做一个更通用的 agent”的概念。通用智能变便宜、变成标配之后，差别来自专门化：在一个具体的小世界里变得可靠、快、便宜。

## 小世界

世界不是一个世界，是几百万个小世界。每个职业、公司、软件、网站都是一个。这些世界的熵加起来几乎无限，没有任何单一模型能装下。所以一定存在适应和专门化，不可能靠一个 general agent 覆盖。

他用实习生说明什么叫学会一个小世界：组织架构谁说了算、做什么要找谁批、软件操作的后果、工作流、同事的心智模型。这不是视频模型。视觉只是一部分，其余是符号的，还有一些既非符号也非视觉。从 intern 到 expert，就是建起这个微世界的模型。

## 为什么现在的 agent 手感是“六成对、三成莫名其妙失败”

因为没有这段专门化。人一旦成为某件事的专家，基本上百分百做对，而且更快、更稳、更省。现在的 agent 不可靠、不高效，还在消耗前沿模型的大量 token。可靠性、速度、成本因此是同一缺口的三个症状，不是三张独立的路线图。

## 学什么，以及现有路线为什么不够

持续学习如果只是“别忘掉旧任务”，范围太窄。在他的用法里，学习目标应该是广义世界模型。现有两条都不够：

- 模型厂的 RL 后训练和合成环境：速度、准确性和范围都和人的在岗学习差很远。
- skills、markdown、harness 这类非参数学习：有空间，只靠它上限有限。

产出某一个垂直 agent 不是目标。目标是一套方法：给定任何领域，都能学出专家。[[neocognition]] 押的是方法，不是某一个岗位。

## 和已有页面的关系

[[agi-roadmap-ladder|梁文锋]] 把持续学习定义为“像员工一样花两个月熟悉环境”。苏煜把这段学习的内容明确写成小世界的世界模型，并把结果定义成可靠性、速度和成本。两边互补，不是同一套术语。

## References

- [[yu-su-xiaojun-agent-history]]
- [[yu-su-xiaojun-chinese-article]]
