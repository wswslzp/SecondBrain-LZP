---
title: "NVIDIA"
tags: [nvidia, ai, compute, gpu, cuda, semiconductors, company, supply-chain]
date_created: 2026-07-19
date_modified: 2026-10-22
related: ["[[jensen-huang]]", "[[cuda]]", "[[extreme-co-design]]", "[[token-economics]]", "[[compute-infrastructure]]", "[[amin-vahdat]]", "[[value-per-gigawatt]]", "[[satya-nadella]]"]
---

# NVIDIA

全球市值最高的公司、AI 革命的引擎。由 [[jensen-huang|Jensen Huang]] 联合创办并执掌。NVIDIA 的自我定位不是「造芯片/造云」的公司，而是 **computing platform 公司**——垂直设计、垂直整合以做极致优化，然后把每一层开放出去，嵌入别人的产品、云、超算、OEM、车、机器人、卫星。本页汇总其核心资产、护城河、供应链、开源与太空布局。

## 核心资产

- **CUDA install base**（见 [[cuda]]）——公司「single most important property」。
- **GeForce**——「the house that GeForce built」。GeForce 至今仍是 NVIDIA **第一营销策略**：青少年玩 Call of Duty / Fortnite → 上大学认识 NVIDIA → 用 CUDA → 再用 Blender / Dassault / Autodesk。当年正是 GeForce 把 CUDA 带到每一个研究者、科学家、自己攒机的 gamer 手里，成为深度学习革命的地基。
- **[[extreme-co-design]]**——跨整条 stack 协同优化的招牌工程范式。
- **不断放大的「计算单元」**：GPU → computer → cluster → **AI factory** → **planetary scale**。Jensen 说他睡前脑中的「一台计算机」已不是芯片，而是「giant gigawatt thing」，需要上万人才能 power up；下一个 click 是行星尺度。

## Moat（护城河）

Jensen 明确给出两条，且有先后：

### #1 CUDA install base（最重要）

> "It wasn't three people that made CUDA successful. It was 43,000 people... and the several million developers that believed in us, that trusted that we were going to continue to make CUDA."

从开发者视角，target CUDA 同时拿到三重好处：**半年后自动快 ~10×**（execution velocity）；**触达数亿设备**——每个 cloud、每家电脑公司、每个行业、每个国家；以及 **trust**——「100% 相信 NVIDIA 会永远维护、优化 CUDA」。install base × velocity × trust 是别人（哪怕出现 GUDA/TUDA）无法复制的。详见 [[cuda]]。

### #2 Ecosystem

垂直整合这套极复杂系统，却又**横向嵌入每一家公司**：Google Cloud、AWS（正疯狂 ramp）、Azure、CoreWeave、Nscale、Lilly 的超算、企业机、无线基站边缘、车、机器人、卫星、太空。「One architecture is in all these different systems」——覆盖世界上几乎每个行业。

> ⚠️ **反论（[[liang-wenfeng|梁文锋]]/[[deepseek]]）**：CUDA 护城河「在快速瓦解，英伟达在掘自己的坟墓」——AI 能写生态、自研 [[china-us-compute-gap#TileLang|TileLang]] 重写算子（DeepSeek V3 已「用英伟达卡但不用英伟达生态」）、计算卡与游戏卡解耦使专用芯片不再绑 CUDA。华为 950 超节点被判定可**平替** GB200/GB300（代价「4 张顶 1 张 + 落后 2 年」）。详见 [[china-us-compute-gap]] 与 [[cuda]] 的矛盾标注。

## 供应链

- 每个 rack **130–150 万个组件**、跨 Vera Rubin rack 有 **200 家供应商**。
- **NVLink-72 把「超算组装」从数据中心搬进供应链制造**：过去零件运到数据中心再组装，现在 NVLink-72 太密，只能在供应链里造好整台超算、每机架 2–3 吨整体发运。这也意味着供应链本身需要吉瓦级电力来 build & test（若要每周产出 50GW 超算，供应链每周就要 1GW 电）。
- 说服合作伙伴各投数十亿美元资本开支，靠的是「relationships + shared view of the future」+ first-principles 画图讲清楚，而非合同施压。
- **Memory 需求侧的推手**：三年前说服多家 45 年历史的 DRAM CEO 量产 **HBM**（当时仅超算少量使用），并把手机用的 **LPDDR** 搬进数据中心（「Cell phone memory for supercomputers?」）——结果 LPDDR5/HBM4 都创历史纪录。这正是 [[ai-storage-chip-super-cycle]] 需求侧的源头。

## China

- **50% 的世界 AI 研究者是华人**，多数仍在中国。
- 中国不是「一个经济体」，而是众多**省市互相竞争**（市长互卷）→ 所以 EV 公司多、AI 公司多、内卷极致 → 幸存者极强。
- 文化「**family first, friends second, company third**」+ 校友「brother for life」→ 天然 open source（「What are we protecting? 我工程师的兄弟/同学都在对家公司」），开源社区反过来放大、加速创新。
- 「a builder nation」，且「their leaders are mostly incredible engineers」（对照美国 leaders 多是 lawyers）。
- **中方自述**（[[liang-wenfeng|梁文锋]]/[[deepseek]]）印证并延伸：人才与美国「几乎没有差距，就是同一批人」，真正差距**只在算力资源**；中国大概率是全球 AI「三体之一」，扮演**产量最大 / 最便宜**的角色。见 [[china-us-compute-gap]]、[[sovereign-ai]]。

## Open source（Nemotron）

开源 **Nemotron 3 Super**：**120B open-weight MoE**，且不是纯 transformer 而是 **transformer + SSM**。NVIDIA 开源了 **weights + data + how we created it**（真·开源）。见 [[open-weights-strategy]]。三条动机：

1. **Co-design**——做基础研究以看清模型如何演进，反哺硬件设计（transformer→conditional/progressive GAN→diffusion 的经验让它预判未来算力形态）。
2. **Diffusion into everyone**——proprietary 会阻碍研究/创新；开源让每个行业、国家、研究者、学生都能加入 AI 革命。
3. **AI 不只是语言**——生物、化学、物理、天气、流体/热力学并非都是语言结构；NVIDIA「不造车但要让每家车企有好模型；不做药但要让 Lilly 有世界最好的 biology AI」。

## Space

**NVIDIA GPU 是首批上太空的 GPU**（卫星边缘 AI 成像）：卫星有厘米级高分辨率成像、连续扫地球，产出 PB 级数据不宜回传，必须**就地做 AI**——丢掉见过、没变化的，只留需要的。太空冷却难（无传导、无对流，只剩辐射 → 「put big giant radiators out there」）。但 Jensen 更务实：先吃地球上电网闲置容量这块 low-hanging fruit。

## OpenClaw / agents

Jensen 称 agents 是 **"the iPhone of tokens"**、**"the fastest-growing application in history"**（「went straight up」）。他认为 OpenClaw 对 agentic 系统的意义，等同 ChatGPT 对 generative 系统的意义——而且因为 consumers 能直接用，破圈程度超过 [[claude-code]]、Codex。他两年前的 GTC schematic 就已画出今日 OpenClaw 的形态（access files、do research、use tools、I/O subsystem = 「we've just reinvented the computer」）。

**安全（NemoClaw / OpenShell）**：核心是 **two-of-three rights**——agentic 系统可以（a）访问敏感信息、（b）执行代码、（c）对外通信，任意时刻**最多同时开两项**，绝不三项全开；再叠加基于企业授权的 access control + 接入企业既有 policy engine。

## CS153 补充：自研 foundation 域、内部用量与出口管制

来自 [[cs153-jensen-huang-compute|CS153 讲座]]：

### 五大自研 foundation model 域
除 Nemotron（语言）外，NVIDIA 亲自造「第一件 artifact」以**激活整条下游产业**（这些领域的科学家没有 scale/技术自建 foundation model）：**BioNemo**（生物）、**Alpamayo**（自动驾驶）、**Groot**（人形机器人 articulation）、**climate science**（mesoscale multiphysics）。其中 **Alpamayo = language model 融合 world model + human priors**，因而只需「a few million miles, not billions」的数据。cybersecurity 打法不是「7.0 对 8.0」的模型军备竞赛，而是用 **Nemotron Nano** 训出「swarms of cheap AIs」组成「a giant dome」围住威胁。理由之一是 **open = safety**：「you can't defend against a black box, and you can't secure a black box.」

### NVIDIA 自身重度用 frontier 模型
NVIDIA 用 **Anthropic + OpenAI 的 token 比几乎任何人都多**，**100% 工程师已 agentically supported**。Jensen 对学生说：「Claude is a product, and **Claude Code is a whole harness** around it」——不太可能去 GitHub 下个开源的就一样好（见 [[claude-code]]）。

### 芯片出口管制立场
Jensen 反对把 GPU 类比原子弹：GPU 用于 video games、送酱油、**medical imaging**（「in every single medical imaging system in the world」）；「a billion people have NVIDIA GPUs，我向家人推荐它们，**I don't advocate atomic bombs to anybody**」。他也反对「why compete abroad, you'll lose anyway」的失败主义，并以**电信业前车之鉴**（美国当年用同样论证把电信核心技术「policied out」，如今已无本土电信核心技术）作警示。总结句：**「Everybody should have AI. Nobody should have nuclear bombs.」**（与 [[sovereign-ai]] 的主权/国家安全视角互补。）

## CS153 补充：TPU/Maia vs GPU 并非零和

在 CS153 上，Google 的 [[amin-vahdat]]（[[value-per-gigawatt]]）强调 **TPU 与 GPU 不是零和**：Google 自己也**大量采购、使用 NVIDIA GPU**，整个市场在扩张，「no winners and losers」。同一逻辑也出现在 Microsoft 一侧——[[satya-nadella]] 正在 codesign 自研的 **Maia 200** 加速器（已在生产环境跑 **GPT-5.5**），却依然「love GPUs because they're general purpose」。也就是说，NVIDIA 招牌的 [[extreme-co-design]] 打法如今已被全行业各家（Google TPU、Microsoft Maia）复制到自研 silicon 上，而 NVIDIA GPU 的通用性仍是各家离不开的底座。

## GTC Berlin 2026：从模型计算到完整 Agent

[[nvidia-gtc-berlin-2026]]（2026-10-21 演讲转录）进一步把平台边界展开为模型、harness、sandbox、知识和工具五个构件：

- **安全**：OpenShell 被描述为 Agent 外部的权限执行层，凭证、网络与文件访问受独立监督；Sentry 是可选硬件隔离监控。见 [[agent-runtime-security]]，不要把产品宣讲视为安全完备性证明。
- **部署**：DSX Pod 把更多预集成和测试移到供应链，关注投产速度及闲置资本。见 [[ai-factory-deployment]]；不代表公用设施、许可和电网交期消失。
- **专业工具**：CUDA-X、仿真器和求解器使 Agent 能测试方案，工具公司也可提供擅用自己工具的 Agent。
- **具身计算**：训练、数字孪生、实机执行构成循环，见 [[physical-ai-computing]]；演示不替代实机验证。

演讲再次主张通用平台内部工作负载的可复用性。这不等于 [[compute-infrastructure]] 所讨论的跨供应商商品化已经实现，也不消除本页保留的 CUDA 护城河反论。新产品状态、倍数与路线图按演讲归属，不作为实时产品规格。

## 相关页面

- [[jensen-huang]]
- [[cuda]]
- [[extreme-co-design]]
- [[accelerated-computing]]
- [[token-economics]]
- [[compute-infrastructure]]
- [[ai-factory]]
- [[open-weights-strategy]]
- [[sovereign-ai]]
- [[claude-code]]

## References

- [[jensen-huang-lex-fridman]] — Lex Fridman Podcast #494（2026-03-24）
- [[nvidia-gtc-berlin-2026]] — GTC Berlin 主题演讲（2026-10-21）
