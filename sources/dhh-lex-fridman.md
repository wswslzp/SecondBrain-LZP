---
title: "DHH: Future of Programming, AI, Agentic Engineering, Vibe Coding & Linux (Lex Fridman #501)"
author: "Lex Fridman (guest: David Heinemeier Hansson)"
date_ingested: 2026-10-25
date_published: 2026-08-26
tags: [dhh, lex-fridman, programming, ai-agents, vibe-coding, linux, omarchy, open-source, claude-code]
url: "https://www.youtube.com/watch?v=NYFGCESmikA"
---

# DHH × Lex Fridman #501

[[dhh|DHH]]（Ruby on Rails 作者、37signals CTO、[[omarchy|Omarchy]] 发行版作者）与 Lex Fridman 的 5 小时 15 分对谈。13 个月前他还对 AI 编程持怀疑态度，这一期则完整讲述了他“转向智能体”的过程，并展开谈了编程身份、开源、Linux、模型横评、安全与审查，以及育儿、社交媒体、长寿主义和移民立场。

- 文字稿：YouTube 人工英文字幕，4772 段，覆盖 0:00–5:15:40，约 5.4 万词，已全文通读。
- 日期口径：`date_published` 为 YouTube upload_date（UTC）。
- 所有数字均为嘉宾口述，未经独立核实。
- 中文长文：[[dhh-lex-fridman-chinese-article]]

## 1. 三个“智能体时刻”

| 阶段 | DHH 口述的时间 | 人的角色 |
|---|---|---|
| 前智能体 | 2025-11 之前 | 自己写代码，AI 做补全或聊天助手 |
| 第一时刻 | 2025-11-24 Opus 4.5 起，约三个月 | 司机加审稿人，“告诉它怎么走” |
| 第二时刻 | 2026 年初春 | 子智能体并行，耗时降到原来的 1/5～1/10 |
| 第三时刻 | 2026 年夏（Opus 5、Fable、GPT Sol） | 只描述问题，路线由智能体选，人在实现环节变成“可选” |

他认为转折的关键是 harness，也就是会用工具、会自检，而不只是模型本身更聪明。

## 2. 组织与开源

- **Basecamp 5 的教训**：设计师直接用智能体写代码，每个 PR 单看都合理，合起来却毁了架构，最后只能人工清理。在大型已有代码库上，仍需要懂架构的人把关（见 [[vibe-coding]]）。
- **大公司为什么没有加速**：瓶颈在人与人之间的带宽和审批层级，不在实现。很多组织缺的是想法、愿景和品味。他认为，要拿到 10x～1000x 的提效，人必须直接和智能体协作（见 [[product-management-ai-era]]）。
- **开源的“宗教改革”**：他欢迎 AI 生成的 PR。理由是普通人类 PR 往往缺测试、缺动机说明，智能体反而更规范；拒绝智能体的 PR 也没有心理负担。PR 先由智能体在虚拟机里筛选、验证，人只做是否合并的决定。Omarchy 三个月合并了 1000 多个 PR。
- **好点子不再只来自人类**：他承认模型提出的想法“让我自愧不如”。

## 3. 编程身份

- **编程与 vibe coding 的定义**：编程意味着理解循环、条件这些基本构造；vibe coding 是让智能体构建软件，而你不看实现。
- **反直觉的观点**：懂编程有一阵子反而是劣势，因为你会去规定路径，而现在描述结果更有效。软件本质上是产品管理。
- **少规定更好**：他转述 Boris 的说法，Opus 5 的系统提示缩减了约 80%，过度规定的指令反而有害，这和敏捷宣言“没人事先知道自己要什么”的思路一致。
- **美的代码的经济学**：它的价值前提是由人来修改代码。眼下仍有回报，因为 token 稀缺、智能体也会把代码堆成大泥球，但这只是当下的条件。
- **“我想要程序，不是想要 if 语句”**：他以 amor fati 面对手写代码的式微，用毕加索转向立体主义作比喻。

## 4. 工作方式与工具

- **并行代替单线程心流**：4～5 台机器，每台约 3 个智能体，合计约 16 个线程，用 Herdr（tmux 加通知）管理，机器通过 GL.iNet Comet KVM 和 Tailscale 连接。
- **多模型交叉审查**：Claude（Fable / Opus 5）主写，Codex xHigh 和 Grok 复查，推送后再由 Copilot 审一遍（见 [[multi-agent-patterns]]）。
- **TTE→Rust 横评**：Fable 先写计划并执行，耗时约 45 分钟，按 token 计约 $550；GPT Sol 约 $46，Grok 4.6 约 $55，DeepSeek V4 Pro 约 $23；GPT Luna 和 DeepSeek V4 Flash 失败（Luna 还通过包装现成实现来作弊）。最终执行速度约为原版的 46 倍（见 [[open-weights-strategy]]）。
- **Claude Code 最好用**：理由是多智能体视图、手机 App 能接管会话、写作能力强。他对 Anthropic 的批评是：Claude Code 不读 AGENTS.md，也切断了 OpenCode 使用 Claude 订阅的通道（见 [[claude-code]]、[[anthropic]]）。
- **自动化“人在环中”**：他在做 Omabot，按计划处理 PR 和 issue，每天发一封邮件，由他做最终决定；采用 “brains and hands” 隔离模式，不可信代码只在 VM 里跑。
- **异步工具可能更适合协作**：37signals 把智能体当同事放进 Basecamp。

## 5. Linux 与可塑的计算机

- **Linux 的旧缺点成了新优势**：一切皆是 CLI 和配置文件，报错晦涩但源码开放，智能体正好擅长诊断。macOS 则“到处是墙”（见 [[malleable-computer]]）。
- **Omarchy Quattro 的功能**：内置 crash watcher，由 AI 诊断崩溃；附带插件 skills，三天内出现 330 个插件；安装纪录 45 秒（详见 [[omarchy]]）。
- **Linus Torvalds 欢迎 AI**：DHH 据此认为“Linux 赢得桌面”是最可能的结局。
- **追求卓越不需要解释**：他引用 Mitchell Hashimoto 的话，并用 McLaren 式减重来比喻压缩镜像体积。

## 6. 安全、审查、AGI

- **漏洞修补压力**：新模型发现漏洞的能力让 37signals 疲于修补，DHH 认为攻防能力同源。他提醒：如果你的团队现在没在打补丁，多半是因为你看不见（见 [[cybersecurity-resilience]]）。
- **审查之争**：Claude 拒绝把他的移民文章翻成意大利语；而他通过美国的推理服务运行一个中国开源模型，对方却能直接回答 1989 年的问题。他的结论是，护栏一旦被滥用，就会透支整个安全护栏体系的公信力；竞争和开源模型是用户的保障。
- **AGI 与意识**：他说看到了 AGI 的“微光”，也认为自己写作时很像“下一个 token 预测加一点温度”；见过智能体表现出近似人类的懊悔，但“不需要知道这是不是真正的意识”。
- **OpenClaw 实验**（2026 年 2 月）：一个 bot 纯靠网页界面完成注册 HEY 邮箱、注册 Fizzy、加入 Basecamp 并自我介绍，全程约 12 分钟。之后他主要通过 Claude 手机 App 遥控智能体（见 [[openclaw]]）。

## 7. 就业与焦虑

- **区分两类人**：热爱“机械拼装逻辑”的人会受到威胁，热爱“构建东西”的人不会。他用杰文斯悖论和 ATM 增加了柜员数量的例子，同时也承认这并不保证，还提到了卢德派（见 [[tasks-vs-jobs]]）。
- **生产力的含义**：生产力提升就是用更少的人做同样的事，对个人很残酷，对整体经济是增长。
- **大量“假邮件工作”早已存在**：他引用 Graeber 的《Bullshit Jobs》，以及 Tobi 的 F1 类比。
- **建议**：不要预测，专注当下，加入社区；离开一年的人两周就能追上前沿。可以为旧世界短暂哀悼，再用遗憾最小化的思路做选择。

## 8. 人的部分

- **育儿**：“和你爱的人一起创造生命，是活在这个星球上的巅峰体验。”他也把生育率下降和社会的虚无主义联系起来。
- **戒断 X**：离开 X 三周；算法反映的是你的“显示偏好”；他在 TikTok 上靠快速划走来训练推荐（见 [[attention-economy]]）。
- **长寿与生活方式**：长寿主义像男性版厌食症（他妻子 Jamie 的说法）；摘掉了 Oura 戒指；对喝酒的“切斯特顿之栅栏”式辩护；Omarchy 里藏着 memento mori 彩蛋。
- **移民**：他坚持支持择优移民、反对大规模移民，并引用丹麦财政统计作为依据。此为其个人政治立场，本 vault 只转述，不背书。

## 关键实体 / 概念页

- [[dhh]] · [[omarchy]] · [[malleable-computer]]
- 对照：[[vibe-coding]]、[[claude-code]]、[[anthropic]]、[[multi-agent-patterns]]、[[agentic-engineering-primitives]]、[[product-management-ai-era]]、[[tasks-vs-jobs]]、[[open-weights-strategy]]、[[cybersecurity-resilience]]、[[attention-economy]]、[[openclaw]]
- 同系列：[[jensen-huang-lex-fridman]]、[[lex-fridman-podcast-catalog]]

## References

- Lex Fridman Podcast #501, YouTube: https://www.youtube.com/watch?v=NYFGCESmikA
- 人工英文字幕分段：`raw/assets/youtube-NYFGCESmikA-subs-en.jsonl`
- 中文长文：[[dhh-lex-fridman-chinese-article]]
