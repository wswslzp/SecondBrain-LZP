---
title: "Agent 运行时安全"
tags: [ai-agents, security, sandbox, permissions, runtime]
date_created: 2026-10-22
date_modified: 2026-10-22
related: ["[[gateway-architecture]]", "[[cybersecurity-resilience]]", "[[nvidia]]", "[[agent-comfort-zone]]"]
---

# Agent 运行时安全

Agent 一旦能访问文件、网络和工具，安全就不能只依赖提示词或模型自律。运行时安全把“它应该做什么”与“系统允许它实际做什么”分开：**模型提出动作，独立执行边界检查并约束动作**。

## 五个构件与执行边界

[[nvidia-gtc-berlin-2026]] 将 Agent 分为模型、harness、sandbox、知识和工具。模型负责推理，harness 编排工作；sandbox 及其外置监督器限制访问，不能让前两者自行扩大权限。

| 层面 | 演讲中的设计 | 解决的问题 |
|---|---|---|
| 文件与系统调用 | Agent 外部的访问策略与隔离 | 错误或被注入的指令不应获得任意执行能力 |
| 出站网络 | 请求经 sandbox 外 supervisor 检查 | 访问目标受控，而非仅要求模型别外泄 |
| 凭证 | 保留在 Agent 外，仅向获准端点注入 | 减少凭证进入模型上下文或执行环境 |
| 策略变更 | 权限上限及策略检查 | 避免借修改规则实现自我提权 |
| 监测与审计 | 可选硬件隔离监控、隔离响应和可核验记录 | 观察运行行为，支持调查与处置 |

这些是演讲对 OpenShell/Sentry 的描述，不是本 wiki 对其实现完备性或攻击抵抗力的认证。

## 与 Gateway 和模型审查的区别

[[gateway-architecture]] 中按用户意图判断动作的 auto mode 属于**决策层**；容器、操作系统权限和代理网络是**强制执行层**。两者可以组合，前者不能替代后者。加密保存凭证也不自动限制 Agent 如何使用它。

[[cybersecurity-resilience]] 强调“有权限以后做了什么”。这与最小权限不矛盾：先限制可达范围，再监测权限内的异常使用。被授权写文件不代表所有覆盖行为都合适；sandbox 也不自动证明业务动作正确。

## References

- [[nvidia-gtc-berlin-2026]] — 35:47–42:09，五构件与 OpenShell/Sentry
- [[silicon-valley-101-vincent-koc-openclaw]] — Gateway、凭证与 OS 级隔离
- [[cs153-joe-sullivan-resilience]] — 运行时异常检测视角
