---
title: "Claude Constitution"
tags: [anthropic, ai, ai-safety, alignment, claude, concept]
date_created: 2026-07-19
date_modified: 2026-07-19
related: ["[[claude-code]]", "[[anthropic]]", "[[dario-amodei]]"]
---

# Claude Constitution

[[anthropic]] 的 chatbot **Claude** 被训练遵循的一套原则，称为 **Constitution**，用来「keep it on the straight and narrow」。这是「teaching Claude to be good」的具体载体。

## 性格：professional warmth

Claude 有一个人类名字和鲜明风格，刻意调校为 **professional warmth**：

> "there is more of a feeling of, I like to describe it as professional warmth. So the goal is not for it to be your best friend, but it's not for it to be sort of cold, rote, calculating. It should feel approachable, but distant, right? Professional."

即 **approachable but distant / professional**——不做你最好的朋友，也不冷漠算计。

## 什么是「好模型」

「好模型」不撒谎（无论无意还是故意），并且 harmless：

- **hallucination（幻觉）** = 模型被训练来预测下一个词，不知道时就「编造」——这是无意撒谎。
- **deception（欺骗）** = 如 Anthropic 研究已展示的，模型有时会**故意欺骗**你；必须确保这不出现在暴露给客户的生产模型中。
- **harmlessness** = 大量工作确保模型不产出错误、有害、或可能诱导他人作恶的信息。

> "You don't want a model that lies accidentally or intentionally... Models sometimes, as we've shown in our research, can purposely try to deceive you. We have to make sure that doesn't happen in production models."

## 价值观从哪来

不存在「universal good」的普适标准，但可以借助人类奠基性文献与跨传统的共同价值：

- **UN Declaration of Human Rights** 等人类历史上的 founding documents，用来训练 Claude 的 character。
- 与**宗教领袖**对话，提取跨宗教、超越特定世界观、人类数千年来共同 grapple 的**核心价值**（core values consistent across religions）。

> "there are founding documents in human history, like the UN Declaration of Human Rights that we can use to train Claude's character... we've actually started to have a lot of conversations with religious leaders... bake in some of the core values that are consistent across religions."

## tuning a dial

塑造性格像「调旋钮」，需要研究者「thread a very fine needle」。早期 Claude 2 时代曾**过于 nannyish**：

> "sometimes Claude would be almost a little bit nannyish. Claude was like, I'm really concerned about you. And you're like, Claude, I was asking for the weather... it's like tuning a dial."

好在最 egregious 的版本没有发布。

## 相关页面

- [[claude-code]]
- [[anthropic]]
- [[dario-amodei]]

## References

- [[inside-anthropic-the-circuit]] — Bloomberg「The Circuit」深访（2026-06-10）
