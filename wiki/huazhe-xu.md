---
title: "许华哲（Huazhe \"Harry\" Xu）"
tags: [person, robotics, embodied-ai, tsinghua, entrepreneurship]
date_created: 2026-10-29
date_modified: 2026-10-29
related: ["[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]", "[[gpt-6-astra]]", "[[physical-ai-computing]]", "[[humanoid-robot-hardware]]", "[[robot-workflow-loop]]", "[[embodied-ai-supply-chain]]", "[[zheqing-zhu]]", "[[sheng-wang]]"]
---

# 许华哲（Huazhe "Harry" Xu）

**许华哲（Huazhe "Harry" Xu，X: `@HarryXu12`）** 是清华大学交叉信息研究院（IIIS）助理教授、博导，具身智能初创公司**破壳机器人**创始人。研究方向为具身智能（Embodied AI）、机器人灵巧操作（含柔体/可变形物体操作，如包饺子、插花等）、强化学习与视觉控制。

在《硅谷101》E256 期（[[silicon-valley-101-gpt6-astra-agent-robotics-pharma]]，2026-09-29 录制）中，他系统拆解了 [[openai|OpenAI]] **[[gpt-6-astra|GPT-6 Astra]]** 对机器人行业的冲击、架构分层边界的移动、数据标注暗战以及通用机器人进入家庭的时间表。

## 核心观点与实测判断（硅谷101 E256）

### 1. 机器人的“GPT 时刻”竟是 GPT 自己
- **定性飞跃**：此前历代大模型（Opus 4.5/4.6、Fable 等）在机器人测试上几乎没有定性改善；而未在发布报告中提及机器人的 Astra 直接登顶 **RoboDojo** 等仿真 Benchmark 榜首，使不少旧评测基准失效。
- **CoT 转化为物理动作（CoT-to-Action）**：Astra 能快速感知陌生机器人本体的运动速度与空间边界，在撞到桌子后通过思维链反思“桌子较高，下次手抬高一点”；在“劈叉花茎插花”测试中，能理解三维几何尺寸，主动先用夹爪捏窄分叉的花茎再塞入花瓶。
- **控制分层下压与 TAMP 复兴**：传统 VLM 仅做高层任务规划（“拿西红柿、打鸡蛋”），Astra 则将指令下压至厘米级低层动作控制（“手往右伸两厘米”），并让传统的 **TAMP（任务与运动规划）** 在 Agentic 框架下重焕生机。

### 2. Astra 的四大短板与“快慢系统”架构
1. **极慢的加密长 CoT**：实机控制视频需 16–24 倍速播放；面对简单任务与复杂任务思考耗时几乎相同（“内耗型人格”），无法执行抖毛巾、倒水等高动态任务。
2. **缺乏直觉物理（Intuitive Physics）**：理解停留在 3D 尺寸，缺乏“碰水杯水会洒、碰玻璃会碎”的瞬间直觉反应。
3. **语言难描述的任务表现弱**：空间旋转插孔笨拙；在破壳机器人“筷子夹小球”任务上，自研小模型能高频连续试探，Astra 则每步停下归因、一旦算错即陷入僵局；**双臂任务（如叠衣服）完全无法完成**。
4. **45 分钟常数陷阱（无肌肉记忆）**：第 1 次做花 1 小时，第 2 次 45 分钟，第 3 次及以后永远卡在 45 分钟常数，无法像人或小模型那样越练越快直至几秒完成。
- **架构结论**：Real-to-Sim 仅改善了 3D 视觉渲染外观，未提升物理引擎精度；未来端侧理想模型尺寸应 **<10B**（云端 API 仅适合容忍 200ms+ 延迟的准静态任务），需将快决策模型（System 1）与 Astra 的推理及 3D 理解（System 2）结合。

### 3. 数据标注“生肉 vs. 熟肉”与普通人的被蒸馏价值
- **标注溢价 10 倍**：传闻 OpenAI 只买未标注原始数据（防泄密且嫌外部标错）。卖原始采集数据如同“卖生肉/石油”；只有标出成败背后的**物理因果与直觉物理**（“没抓住是因为位置偏上还是沾水太滑”）的“熟肉数据”，单价才能翻 10 倍以上。
- **人人皆生活专家**：不同于纯文本领域“普通人已无被蒸馏价值”的悲观论，在机器人领域每个普通人都是做饭、叠衣服的生活专家，未来 1–2 年内家常动作数据仍极具蒸馏价值。

### 4. 零样本泛化与 2028 年初进家庭预测
- 批评当前工业部署需“5 个博士驻厂睡 3 个月调夹爪与稳定性”是逆时代的；终局应是**零样本泛化（Zero-shot Generalization）**，由 5 个普通工人即可快速部署。
- **预测**：**2028 年初（距访谈约 18 个月）**，通用机器人将开始真正实用化，普通人在家里用自然语言指令即可让机器人完成 **90%** 的家务。

## 相关页面

- [[silicon-valley-101-gpt6-astra-agent-robotics-pharma]] — 播客 Source 摘要页
- [[silicon-valley-101-gpt6-astra-agent-robotics-pharma-chinese-article]] — 播客中文长文
- [[gpt-6-astra]] — GPT-6 Astra 模型页
- [[physical-ai-computing]] / [[humanoid-robot-hardware]] / [[robot-workflow-loop]] — 具身计算、硬件大小脑与工作流闭环

## References

- 《硅谷101》E256《Agent、机器人与制药，谁先被GPT-6 Astra改写？》（2026-10-20 发布，2026-09-29 录制）
- X (Twitter): `@HarryXu12`
