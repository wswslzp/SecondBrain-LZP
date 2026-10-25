---
title: "Gateway 架构（always-on / heartbeat）"
tags: [ai-agents, architecture, openclaw, security, always-on, heartbeat]
date_created: 2026-07-21
date_modified: 2026-10-22
related: ["[[openclaw]]", "[[context-management]]", "[[multi-agent-patterns]]", "[[cybersecurity-resilience]]", "[[ai-agent-memory]]"]
---

# Gateway 架构（always-on / heartbeat）

**Gateway** 是 [[openclaw|OpenClaw]] 设计的**中枢神经系统（central nerve system）**，把消息通道、模型、记忆、工具连在一起，让 agent 去完成任务。它是 OpenClaw 区别于传统 coding agent 的核心，也是它「magic」的来源。设计出自 Peter Steinberger（或他的 agent，来回打磨而成）。来源：[[silicon-valley-101-vincent-koc-openclaw|硅谷101 对 Vincent Koc 的访谈]]。

## always-on vs turn-based

| | 传统 coding agent | OpenClaw Gateway |
|---|---|---|
| 运行 | **turn-based**：一个线程、一问一答 | **always-on**：像机器上的一个 **service** 常驻 |
| 触发 | 用户发起 | **heartbeat** 主动触发 |
| 连接 | harness 内部工具 | 消息通道 + 模型 + 记忆 + 工具（中枢） |

## Heartbeat：类人的后台代理

Gateway 每 **10–30 分钟**触发一次**对话链（conversation chain）**：检查「需不需要做点什么」，需要就去做。于是 agent 有了「我在后台替你办事、还能调度任务」的**类人**特质——这正是 OpenClaw「magic」的一部分。

> 对照：[[microsoft|微软 Scout]] 的 long-running agent 同样有 **heartbeat** 且会「dreaming」，被明确描述为「对标 Claw」。

## 存储重构：文件 → 数据库

早期「一切写文件」（会话对话全落盘）→ 现在写进**数据库**（装在一个小文件里）。意义：企业可把该文件替换成数据库系统、做备份 → 更易规模化部署，也让大厂更容易在 OpenClaw 上二次开发。

## 安全边界（OpenClaw 最大的攻击面）

Gateway **持有凭证 + 跨用户系统执行动作** = OpenClaw 最大的安全边界。防护做法：

- **凭证不明文**：存进类 **vault** 的机制。
- **容器化**：可把 OpenClaw 跑在容器里，限定「只能碰这些文件、这条网络连接」。更进一步在和产业伙伴做 **OS 级原生隔离**——让操作系统 + OpenClaw **100% 确知**它在访问什么，越界就回来向用户请求许可。
- **「只是拼图的一块」**：模型、操作系统、产业需协同——这不是 OpenClaw 独有难题；任何拿到 admin 权限的 coding agent 都能删文件/上网。

### Auto mode：不是开/关，而是「按意图判断」

不像传统「approval on/off」二选一，OpenClaw 在 OpenClaw 层实现 **auto mode**：让 **LLM 读对话、按用户意图**判断某动作安全与否，再决定是否请求批准（同一个动作——删文件——在生产机 vs 一次性测试机上意图完全不同）。

- 在 **OpenClaw 层**实现 → 即使用开源模型也能享受该能力。
- **Hybrid**：可付费用一个**前沿实验室模型**做「安全审查/guardrail」，同时把**推理**跑在**本地开源模型**上——两全其美。

### 意图判断与强制执行不是同一层

[[nvidia-gtc-berlin-2026]] 描述的 OpenShell 把系统调用、文件、出站网络和凭证约束放在 Agent 外部。它补充了本页 auto mode 的边界：LLM 判断“用户是否想这样做”是决策，OS/sandbox/proxy 限制“实际可以做什么”是强制执行。前者可能判断错误，后者也不能证明业务行为正确，两者需要结合。见 [[agent-runtime-security]]。

## 与其它模块的接口

- **模型 × harness**：表现是二者组合；部分模型（尤其中国开源模型）在 OpenClaw 上 post-train 后更好用（模型「知道自己在 OpenClaw 里」）。
- **记忆**：Gateway 挂接记忆，但记忆本身「远未解决」（换模型/多租户），见 [[ai-agent-memory]]。
- **多智能体**：瓶颈是 context 而非成本——多数情况单 agent + 一个 always-on Gateway 足矣，见 [[multi-agent-patterns]]。
- **小核心**：OpenClaw 保持 small core，plugin 架构随产业演进（例：skill 依赖 skill 目前 spec 尚不支持）。

## 与 vault 的关联

- [[cybersecurity-resilience]] — [[joe-sullivan|Joe Sullivan]] 的「agents-as-toddlers 运行时异常检测」正对应 Gateway 这类持有凭证的执行边界。
- [[context-management]] — heartbeat 的对话链本质是一次次 context 的组织与触发。

## References

- [[silicon-valley-101-vincent-koc-openclaw]] — 硅谷101 对话 Vincent Koc（WAIC 2026）
- [[nvidia-gtc-berlin-2026]] — 运行时隔离与外置策略执行
