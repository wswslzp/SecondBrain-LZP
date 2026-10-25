---
title: "Tasks vs Jobs"
tags: [ai, job-loss, economics, labor, career, concept]
date_created: 2026-07-19
date_modified: 2026-10-25
related: ["[[ai-impact-on-industry]]", "[[ai-destroying-programmer-jobs]]", "[[context-farming]]", "[[dario-amodei]]", "[[jensen-huang]]", "[[product-management-ai-era]]", "[[sam-altman]]", "[[satya-nadella]]", "[[ai-native-company]]", "[[agi-roadmap-ladder]]", "[[liang-wenfeng]]", "[[dhh]]", "[[dhh-lex-fridman]]"]
---

# Tasks vs Jobs

[[dario-amodei|Dario Amodei]] 分析 AI 就业冲击时的**关键区分**：AI 先自动化的是**任务（tasks）**而非整份**工作（jobs）**，但两者的边界会随时间被抹平——这是理解「AI 到底会不会消灭岗位」的核心框架。

## the hump（那道坎）

> "You automate 90% of the job, great — people are 10 times more productive in the other 10% 'cause they're 10 times more leveraged. But eventually it gets close to a hundred percent. Now the sequel to that is, well then you have to find something else for them to do."

- 阶段一：自动化 90% → 人在剩下 10% 上 **10× leveraged**，生产力大涨（「the usual hump」）。
- 阶段二：逼近 **~100%** → 对某些人而言 AI「just do the thing」更好，此时**必须给他们找别的事做**。
- 软件工程正处于此过程早期：AI 已写「almost all the code」，多数工程师更高产，但「已开始看到」少数人 AI 不再能提升其产力。

## 技术前提：[[liang-wenfeng|梁文锋]] 的「持续学习」判据

Dario/Jensen 争的是**会不会**替代 jobs；[[liang-wenfeng|梁文锋]]（[[liang-wenfeng-investor-meeting]]）给出一个**技术性判据**——jobs 被替代的前提是**持续学习**被攻克：

> 招一个员工，他花两个月熟悉环境就能听懂「叫小王来」；AI 前面没有这两个月的学习，你得给它所有上下文——所以**当前 AI 替代不了你的员工**。

- 差的不是智能而是**持续学习**：「AI 现在不缺品味和直觉，缺的是持续学习。」在 Agent 这一级走完前，jobs 层面的替代不会真正发生（tasks 仍会被大量吃掉，对应上面的 the hump）。
- 这把「the hump 逼近 100%」的时点，锚定到 [[agi-roadmap-ladder|AGI 路线图]]里「持续学习 → 奇点」那一跃——为 tasks-vs-jobs 之争提供了一个可证伪的技术里程碑。

## 不寻常的宏观组合

> "we could have this very unusual combination of very fast GDP growth and high unemployment, or at least underemployment, low wage jobs, high inequality."

即「高 GDP 增长 + 高失业/underemployment + 高不平等」同时出现——这正是他想**防止的结果**（「is that not how revolutions start?」→「this is absolutely the outcome we want to prevent」）。

## 人往哪去（none guaranteed）

pie 会大幅扩张，所以「大概会有地方可去，问题是能否**足够快**地找到」。Dario 点名三个方向：

1. **物理世界** — 需要更多人去 make / build / manufacture。
2. **以人为中心 / 关系驱动的岗位** — 至少有些人想跟真人交流，human-to-human interaction「will never fully go away」。
3. **把 AI 对齐到人的价值与意图** — AI「at some level has to be in line with someone's values and someone's intentions」，人在其中扮演引导者（「how thin versus how thick it will be」尚不确定）。

### 医学例子（pivot to interpersonal）

> "AI is gonna soon be pretty good at telling you what the suite of options... and what tests to run. But an AI can't physically examine you and say, does it hurt when I press here. They can't have a bedside manner."

诊断工具会变强 → 医学 pivot 到 **interpersonal**（触诊、bedside manner、陪伴），而非诊断本身。

## 反驳「doom marketing」

Jensen Huang 称 Dario「conflating tasks with jobs」；有人指这是有利于 [[anthropic]] 的 doom marketing。Dario 强调他在**每次访谈**都谈应对之策（税收 / 宏观政策 / 新岗位），写过五页详述 tasks 与 jobs 之别、「why this time is different」，「the idea that this is cheap marketing is itself cheap marketing」。他的信息不是「doom is coming」，而是「this is something we should see coming... and that we need to respond to positively」。

## 对立视角：[[jensen-huang|Jensen Huang]] 的乐观论（purpose ≠ task）

有意思的是，Dario 点名反驳的正是 Jensen——而 Jensen 在 Lex Fridman 访谈里把这套论证完整讲了出来。他同样区分 tasks 与 jobs，但结论相反：**岗位会净增长**。

> "The purpose of your job and the tasks and tools that you use to do your job are related, not the same."

- **放射科医生的故事**（他反 alarmist 的核心案例）：computer vision 在 2019–20 就已 superhuman，「放射科医生会消失」的预言在技术上完全正确——**然而放射科医生数量反而增长，如今全球短缺**。因为其 purpose 是「诊断疾病、帮助病人」；能更快读片 → 读更多片、诊断更好、医院接更多病人、赚更多钱 → 需要更多放射科医生。他说 alarmist 警告「矫枉过正、吓退了这个重要职业的人，造成了 harm」。
- **软件工程师同理**：NVIDIA 的软件工程师数量会增长；「purpose of a software engineer」（解决问题、团队协作、发现新问题、创新、连点成线）不变，只是不再以代码行数衡量。
- **coding = specification**：编码的本质是「说明要造什么」，会写 specification 的人从 ~30M 增至 ~1B——「every carpenter in the future will be a coder，而且是带 AI 的 architect」，各职业被**抬升**而非替代。
- 建议：招聘时选「AI expert」的应届生；每个学生 / 木匠 / 电工 / 农民 / 药剂师都该用 AI 抬升自己。

**分歧的精确位置**：Jensen 也承认「**if your job IS the task, you'll be highly disrupted**」——在「tasks 会被自动化」这一点上二人一致。真正的分歧是：Jensen 相信 pie 变大 + purpose≠task ⇒ 人总能找到新 purpose、岗位净增长；Dario 担心 the hump 最终逼近 ~100%、人未必能**足够快**地找到新去处。另可参见 Jensen 的哲学锚点「intelligence is a commodity，真正该抬高的词是 humanity」（[[jensen-huang]]），与「人往哪去」的人本方向一致。

第三个声音：[[ben-horowitz|Ben Horowitz]] 在 CS153（[[cs153-ben-horowitz]]）站 Jensen 一侧——「software engineering jobs are growing very fast **despite what Dario says**，而且在 Anthropic 内部也增长很快」；他认为流传的 tweet 扭曲了 Dario 关于「转型期低技能岗位」的真实说法。

## 产品/职业层的实证：[[nikhyl-singhal|Nikhyl Singhal]] 的分布结论

[[product-management-ai-era]] 给这场辩论补上了「谁被冲击」的具体分布：被自动化的正是 **information mover（搬信息的官僚）** 这类「job = task」的岗位，而 **有 judgment 的 builder** 需求与薪资齐升（top 1% 产品人薪资 18 个月翻倍）。最惨的不是学生、也不是高管，而是 **8–15 年、被 ZIRP 提拔去「管人」、只会搬信息的中层经理**——这为 Dario 的「task=job 者被冲击」提供了现实画像，也为 Jensen 的「purpose≠task 者受益」提供了正面证据。二者在这里并不矛盾，而是同一分布的两端。

## 与其他视角对照

- 程序员侧的具体版本见 [[ai-destroying-programmer-jobs]]（立党：价值在「定义问题」而非写代码）与 [[ai-impact-on-industry]]。
- 「人引导 AI」的落地形态之一是 [[context-farming]]——人类把 context/意图喂给 agent、承担剩余 10% 的高杠杆判断。

## CS153 新增声音：Altman 与 Nadella

这场辩论在 CS153 又添两个声音。[[sam-altman|Sam Altman]]（[[openai]]，[[cs153-sam-altman-scale]]）自称已「much less of a short-term jobs doomer」——总有新事物涌现，短期冲击「may not even be as disruptive as I originally thought in the short term」；他更大的忧虑是**算力的公平分配**（当杠杆从劳动转向资本，需要类似「公民财富基金」/ 所有权份额来对冲）。[[satya-nadella|Satya Nadella]]（[[microsoft]]，[[cs153-satya-nadella-frontier-ecosystem]]）承认「any disruptive technology will have real displacement」，**但**当下的智能被 commoditize 后，人类作为「the most adaptive species」会在其上创造新价值 →**带来有能动性、有工资的新经济活动**（与 Jensen 的 purpose≠task 乐观论同调）。YC 的 [[diana-hu]]/[[garry-tan]]（[[ai-native-company]]，[[cs153-garry-tan-diana-hu-ai-native]]）则从组织结构上印证了 Nikhyl 的中层挤压：AI-native 公司更扁平、更少中层管理，中层原本承担的「lossy info routing」被削去。

## DHH：区分“热爱拼装”与“热爱构建”（Lex #501）

- **两类人**：如果你热爱的只是把正确的逻辑构造拼在一起、实现别人要求的东西，这个机械过程确实受到威胁；如果你热爱构建东西，就不会受到威胁（[[dhh-lex-fridman|DHH × Lex #501]]）。
- **乐观与保留**：他用杰文斯悖论和 ATM 增加了柜员数量的例子说明需求可能扩张，但也明确说“这并不保证”。他认为卢德派比农业机械化更贴切，因为那是一群在不错条件下做着喜欢的工作的高技能工匠。
- **生产力的定义**：生产力提升就是用更少的人做同样的事，对被裁员的个人很残酷，对整体经济是增长。他还认为，当前的裁员很多是疫情期间过度招聘的结果，AI 只是方便的借口。他引用 Graeber 的《Bullshit Jobs》，以及 Tobi 的 F1 类比（F1 雇了数万人做一件“轻浮的事”）来说明新工作会被发明出来。
- **建议**：不要预测两次模型迭代之后的世界，专注当下、加入社区；离开一年的人两周就能追上前沿。
- **与 Jensen 的异同**：两人都持乐观立场，但 DHH 更直白地承认短期痛苦是真的，也是进步的必要代价。

## 相关页面

- [[ai-impact-on-industry]]
- [[ai-destroying-programmer-jobs]]
- [[context-farming]]
- [[dario-amodei]]

## References

- [[inside-anthropic-the-circuit]] — Bloomberg「The Circuit」深访（2026-06-10）
- [[dhh-lex-fridman]] — Lex Fridman #501 DHH 访谈（2026-08-26）
