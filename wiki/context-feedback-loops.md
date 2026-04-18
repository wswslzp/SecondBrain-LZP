---
title: "Context Feedback Loops 与 Context Wars"
tags: [ai, rl, infrastructure, strategy]
date_created: 2026-04-18
date_modified: 2026-04-18
related: ["[[anjney-midha]]", "[[frontier-systems]]", "[[sovereign-ai]]"]
---

# Context Feedback Loops

AI 前沿进展的关键输入。[[anjney-midha]] 在 CS 153 中强调：**"Context is critical."**

## 基本循环

```
模型 → 部署到用户 → 观察成功/失败 → RL 反馈 → 更好的模型 → ...
```

### Anthropic 示例
1. 训练一个好到程序员愿意用的代码模型
2. 部署，收推理收入
3. 推理收入 → 买下一轮 compute
4. 观察 context（monorepo、git history、文件系统）→ RL 改进
5. 循环

**两个飞轮互相强化**。

## 可验证性决定进展速度

可验证的领域进展快（**narrow superintelligence** 或指数增长）：
- **代码**：单元测试通过/不通过
- **材料科学**：物理验证（PI Labs 的超导体发现）
- **物理/化学**：定律可检验

难以验证的领域进展慢：
- 美学、爱、创意、品味
- 长文写作、说服力
- Midha 的亲身例子：朋友 30 秒内就能识破 Claude 辅助的文档

Amp 内部规则：**不发送 AI 生成的文档给彼此**。

## Context Wars

**谁拥有独特 context，谁就获得价值。**

### 案例 1：OpenAI 收购 Windsurf
- OpenAI 宣布收购 Windsurf（IDE，很多学生在用）
- 几天后 Anthropic 切断 Windsurf 的 API 访问
- 理由：context 泄漏——竞争对手能观察你如何帮助用户

### 案例 2：Mistral 与 Sovereign AI
- Guillaume Lamp（llama 共同创建者）+ Arthur Mensch（Chinchilla 作者）
- 主权 context（政府、国防、国家记录）不能送到海外云
- 需要本地权重 → 开源模型
- 这打破了 15 年的云巨头集中化趋势

详见 [[sovereign-ai]]。

## 对学生/创业者的含义

Midha 的关键问题：

1. **哪里有可靠可验证的 context？** → 那里进展最快
2. **谁将独占这个 context？** → 那里价值聚集
3. **谁被锁在外面？** → 那些没有特权 context 的团队

## 关键引语

> "Wherever in life we have verifiability, you will see narrow superintelligence emerge. But in areas where progress is not easily verifiable—aesthetics, beauty, love—it's much harder."

> "Teams that get locked out of contexts essential to improve models will not have a chance."

## RL 的极限辩论

两派观点：
1. **哲学派**：足够 compute + context → 模型会自己构造新环境学习跨领域
2. **经验派（Midha 倾向）**：RL 不跨任务分布泛化；代码 → 材料科学不自动转移

"生活是凌乱的。"

## 来源
- [[cs153-frontier-systems]]
