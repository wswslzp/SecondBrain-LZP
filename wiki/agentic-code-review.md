---
title: "Agentic Code Review（智能体时代的代码审查体系）"
tags: [ai-agents, code-review, claude-code, software-engineering, evals, ci-cd, governance]
date_created: 2026-10-27
date_modified: 2026-10-27
related: ["[[claude-code]]", "[[anthropic]]", "[[addy-osmani]]", "[[claude-code-team-code-review]]", "[[agentic-engineering-primitives]]", "[[multi-agent-patterns]]", "[[multi-agent-research-loop]]", "[[ai-native-company]]", "[[context-management]]", "[[three-gate-evaluator]]", "[[accountability]]"]
---

# Agentic Code Review（智能体时代的代码审查体系）

当 Coding Agent 编写了代码库中绝大部分代码（如 [[claude-code|Claude Code]] 约 90% 代码由 Claude 编写，[[anthropic|Anthropic]] 主 monorepo 日均合并变更在 2026 年 5–9 月间从 ~2,500 增至 30,000+），传统的“事后人工逐行阅读 diff”模式在吞吐量上彻底失效。

**Agentic Code Review** 是将“读代码找常规错误”高度自动化、将审查前置为持续运行的“拼写检查”，并把人类注意力精准保留给**产品品味、架构、高危路径与最终责任**的多层防御工程体系。

---

## 核心哲学：双面成本与问题重构

### 1. 从“读没读过”到“由哪一层拦截”
传统问题：“有人读过这段代码了吗？”
重构后的问题：**“这次变更可能会出什么问题？用哪种检查方式——自动化还是人工——最适合捕捉到它？”**

### 2. 人类时间的双面成本（Dual-sided cost）
$$\text{人类总时间成本} = \text{花在代码审查上的时间} + \text{花在修复烂代码引入的 Bug 上的时间}$$
如果只压降前者而导致后者上升，只是把时间消耗转移到了别处。因此必须同时追踪两组指标：
- **效率目标**：绝大多数 PR 在**最多 1 名人类介入（可以是作者本人）**下合并；追踪每个 PR 的人类批准数（中位数与 P95）、人类评论数、等待人工时长。
- **护栏指标（Guardrails）**：**回滚率（revert rate）**与**线上事故率（incident rate）**绝不能上升。（据 Claude Code 团队统计，2026 年 6–9 月合并 PR 翻倍的同时，回滚比例下降超 40%。）

---

## 六层防御与快速回滚架构（Swiss Cheese Model）

没有任何单一关卡能拦住所有 Bug；系统依靠多层互补检查 + 最后的快速回滚兜底：

| 层级 | 阶段与机制 | 核心做法与纪律 |
|---|---|---|
| **Layer 1** | **Pre-PR 验证（最重要）** | 不接受口头“已完成”，要求 Agent 展示**可运行的证据（Proofs）**（跑测试、构建、截图对比 UI 设计稿）；随后派一个**全新上下文的 subagent**（见 [[context-management]]）审查 diff。Boris Cherny 估计验证流程能将产出质量提升 **2–3 倍**。 |
| **Layer 2** | **PR 级多 Agent 审查** | 每个 PR 在人工看之前必经 AI 审查（Quick / Standard / Deep 三档）。采用**多 Agent 并行猎捕 Bug → 独立投票筛除误报 → 过滤纯风格/清理项**。保留问题标为 `Important` / `Nit` / `Pre-existing`（历史遗留不罚作者），必须修复或附理由 resolve。 |
| **Layer 3** | **阻断式安全审查** | 自动运行 `/security-review` 或安全 Action；存在任何未关闭的代码或安全 finding 时禁止合并；后续 Commit 修复后自动关闭。 |
| **Layer 4** | **阻断式自动化 CI** | 格式化、lint、类型检查、全平台测试與构建；PR 模板强制包含“测试方式”、“风险评估”与“如何回滚”（Agent 可代填，人类作者负核实之责）。 |
| **Layer 5** | **按风险分级的人工审批** | 分类器按**变更内容（而非作者身份）**定级；敏感路径（计费、认证、自动更新、CI 工作流、安装器）强制人工审批。仅仓库受信任名单（Trusted list）享宽松路径；**Bot 批准绝不抵扣人类批准**；Agent 提 PR 时其人类操控者计为一名审查人；推送新不可信 Commit 即撤销原批准。 |
| **Layer 6** | **合并队列与灰度发布** | Merge queue 确保变更合入最新 `main` 后全量检查仍通过；新功能置入 Feature flags，按“内部员工 dogfooding → `latest` 渠道 → `stable` 渠道”分阶段推出。 |
| **兜底** | **秒级回滚与事故复盘** | Feature flags 支持免部署直接关停；每周轮值 on-call，事故复盘必查**“本该由哪一层防线拦住？”**，并将缺失上下文沉淀回文档、Skill 或新检查。 |

---

## 文档即治理：`CLAUDE.md` vs `REVIEW.md`

当自动化审查反复标记同一类问题时，不在单个 PR 里纠缠，而是直接从源头（Skill、Lint 规则或上下文文档）修复。两份核心文件职责分明（与 [[agentic-engineering-primitives]] 中的 Resolver 思想一致）：

- **`CLAUDE.md`（给写代码的 Agent 和审查员提供项目上下文）**：包含技术栈、编码规范、目标与非目标、可运行的自检清单。因为每次审查都会加载，在大型仓库中**必须保持简短**，通过链接引用其余文档。代码违背规范或更新导致文档过时都会被标记。
- **`REVIEW.md`（Code Owners 给审查员定的审查契约）**：明确在该模块中什么最重要，且团队会单独验证审查员是否遵守了 `REVIEW.md`。优秀的 `REVIEW.md` 简短且聚焦于：
  1. **定义项目级失败**（如：文档不能撒谎、配置不能错误路由）；
  2. **限制吹毛求疵（Nitpicking）**；
  3. **定义忽略路径（Ignored paths）**；
  4. **强制要求精确的 `文件名 + 行号` 引用**，严禁猜测文件名；
  5. **要求顶层总结**（包含问题总数，或明确声明 `"no issues"`）。

---

## 审查系统的评估与收敛（Eval & Convergence）

### 1. 线上事故即评估集（Our incidents are the eval）
- 团队收集历史上所有引发事故的 PR、向前修复（fix-forwards）与回滚记录，由熟悉代码库的工程师核实每个 Bug 的准确位置，构成黄金测试集。
- **每天**以及**每次修改审查工具的 Prompt、工具或底层模型时**，都在完整事故集上重跑打分（召回率 Recall）。
- **噪音约束（Noise regulation）**：追踪人类对每条评论的处理分类（修复 / 拒绝 / 澄清有意为之 / 无关紧要），并在已知干净的 PR 上测试系统报出“有害修改建议”的频率。

### 2. Agent-to-Agent 死循环与收敛机制
- **非对称成本**：人类忽略一条 Nit 只需 1 秒；但当作者是 Agent 时，它会为 Nit 提交新 Commit，进而触发新一轮完整审查。
- **50+ 次死循环案例**：Claude Code CLI 项目曾出现一个 PR 在一夜之间被 Agent 作者与 Agent 审查员来回拉锯循环 **50 多次**。`git blame` 分析显示，审查系统反复标记的内容中有 **~59%** 从第一轮审查时就已经存在——系统不是在抓新引入的 Bug，而是在每一轮翻出更多旧账。
- **五条收敛规则（Convergence rules）**：
  1. **限制最大轮数**：满 **3 轮**后，要求作者重新评估整体方案，不再盲目修补；
  2. **增量重审**：初始几轮过后，后续只审查**新增的 diff**；
  3. **按类别报错（Class of bugs）**：指出 Bug 所属类别，让作者一次性修完同类问题，而非一行一行挤牙膏；
  4. **去重记忆**：避免重复报告已经观察到的问题；
  5. **夜间全库扫描**：将查找历史遗留 Bug 的任务剥离出 PR 循环，改为夜间对代码库全量运行。

---

## 回路中的人类与组织文化

### 1. 人类不可外包的五件事
1. **Should we even build this?（到底该不该做）**：设定产品愿景、品味（[[ai-native-company|Taste]]）与目标；对跨团队/外部 PR 尤其需要人工确认方向；
2. **审计高危代码**：计费（billing）、身份认证（auth）、自动更新器、CI 工作流、安装器；
3. **架构审查**：确立其他人后续遵循的系统规范（呼应 [[vibe-coding]] 中 DHH 在 Basecamp 5 的架构教训）；
4. **核验证据（Verifying proofs）**：检查测试输出、命令记录、截图对比。**“如果你说不出自动化检查会漏掉什么，就别随便求一个 👍，你需要的是真正的人工审查！”**
5. **承担责任（Taking responsibility）**：无论代码是谁敲出来的，每一个上线的变更背后都必须有一个具体的人类负责（工程版的 [[accountability|Skin in the Game]]），践行 **“You land it, you own it（谁合入，谁负责）”**。

### 2. 当机器读了大部分代码，人类如何理解代码库？
代码审查的第二功能是“建立团队对代码库的共同理解”。当逐行读 diff 被机器接管后：
- 团队承认**没有任何人脑子里有（也不需要有）整个代码库的完整心智模型**；
- 当需要了解或修改某个模块时，直接让 Claude 针对该切片实时生成一份**最新讲解文档（Explainer）**，甚至生成**可视化微型交互组件（Mini artifact）**来按个人偏好教学——这比逐行阅读琐碎の一行文案修改能学到多得多的东西；
- 配合**默认公开的 Slack 频道**协作，加上写代码成本极低带来的**“早期及时转向（Changing course，直接关掉方向不对的 PR 而不心疼沉没成本）”**，在无需逐行设卡的前提下维持高工程质量。

---

## References

- [[claude-code-team-code-review]] — Addy Osmani：How the Claude Code team does code review（2026-10-26）
- [[agentic-engineering-primitives]] — Garry Tan 的 Skill / Resolver / Skillify 与 OpenClaw 的“软件工厂”验证设施
- [[multi-agent-patterns]] · [[multi-agent-research-loop]] — 多 Agent 并行验证与死循环防坑
- [[ai-native-company]] — Closed-loop 组织、Taste & Evals
