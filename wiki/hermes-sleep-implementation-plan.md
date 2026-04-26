---
title: "Hermes 睡眠巩固系统 — 完整实现方案"
tags: [ai-memory, hermes, implementation, sleep-consolidation, cron, skill]
date_created: 2026-04-26
date_modified: 2026-04-26
related: ["[[sleep-consolidated-memory]]", "[[hermes-vs-scm-analysis]]", "[[ai-agent-memory]]", "[[memory-compression]]", "[[memory-forgetting]]", "[[complementary-learning-systems]]", "[[hermes-agent]]"]
---

# Hermes 睡眠巩固系统 — 完整实现方案

基于 SCM 论文框架 + Awesome-AI-Memory 研究 + Hermes 架构分析，设计的**最小可行"睡眠"系统**。

## 〇、设计原则

1. **零侵入** — 不 Fork Hermes 源码，完全用现有工具实现（Cron + Skill + Memory + Hindsight）
2. **SCM 精神继承** — 不复刻 SCM 的代码，而是用 LLM 原生能力替代其数学模块
3. **渐进式** — 分三个阶段，每阶段独立可用，不依赖后续阶段

---

## 一、架构总览

```
          ┌─── 觉醒时（正常对话）───┐
          │                          │
          │  Context Window          │
          │  Memory (2.2KB)          │
          │  Hindsight (语义)        │
          │  Skills (程序)           │
          │  Sessions (情景)         │
          │                          │
          └──────────┬───────────────┘
                     │
              ┌──────┴──────┐
              │  触发条件    │
              │  ① 定时睡眠  │  ← Cron Job (每日凌晨 3:00)
              │  ② 疲劳触发  │  ← Cron Job (每30分钟检测 Memory>80%)
              └──────┬──────┘
                     │
          ┌──────────┴──────────────────┐
          │     🌙 睡眠周期 (Sleep Cycle) │
          │                              │
          │  Phase 1: NREM 巩固          │
          │    → session_search 近 24h   │
          │    → 提取高频模式            │
          │    → hindsight_retain        │
          │    → SecondBrain wiki 更新   │
          │                              │
          │  Phase 2: Memory 压缩        │
          │    → 读取当前 Memory         │
          │    → LLM 评估重要性          │
          │    → 合并/精简/遗忘          │
          │    → 程序知识 → Skill 迁移   │
          │                              │
          │  Phase 3: REM 联想           │
          │    → Hindsight 跨域检索      │
          │    → 发现新关联              │
          │    → 生成 insight            │
          │                              │
          │  Phase 4: 自我报告           │
          │    → 巩固/遗忘/发现统计      │
          │    → 送达用户                │
          └─────────────────────────────┘
```

### 与 SCM 的映射

| SCM 模块 | Hermes 实现 | 替代策略 |
|---|---|---|
| MeaningEncoder | LLM 原生语义理解 | 无需独立编码器，LLM 直接处理 |
| ValueTagger (4D) | LLM 评估 + 启发式规则 | 用"最近使用时间 × 引用频率 × 用户纠正"近似 |
| WorkingMemory (7项) | Memory (2.2KB) | 容量约束天然存在 |
| LongTermMemory (图) | Hindsight + SecondBrain wiki | wikilinks 近似图结构 |
| SleepCycle | **Cron Job + Skill** | 本方案核心 |
| Self-Model | 睡眠报告 + Memory 使用率追踪 | 基本可实现 |

---

## 二、Phase 1 实现 — 记忆压缩与遗忘（🔴 最急）

**目标**：解决 Memory 99% 满的燃眉之急，建立自动化压缩管线。

### 2.1 创建 `memory-management` Skill

这个 Skill 定义了压缩和遗忘的标准操作流程，供 Cron Job 和手动调用。

**核心逻辑**（LLM 替代 ValueTagger）：

```
对 Memory 中每条记忆评估保留分数：

保留分数 = w1 × 时效性 + w2 × 使用频率 + w3 × 不可替代性

  时效性 (0.30):
    - 用户偏好/身份 → 1.0（永久有效）
    - 环境配置 → 0.8（缓慢过期）
    - 项目细节 → 0.5（可能已完成）
    - 临时状态 → 0.1（应迁移或删除）

  使用频率 (0.35):
    - 每次对话都引用 → 1.0
    - 最近一周引用过 → 0.7
    - 超过两周未引用 → 0.3
    - 从未被引用 → 0.1

  不可替代性 (0.35):
    - 只存在于 Memory → 1.0
    - Hindsight 中有备份 → 0.5
    - 在配置文件/代码中已有 → 0.2
    - 网上可搜到 → 0.1
```

**操作规则**：

| 保留分数 | 操作 |
|---|---|
| ≥ 0.7 | 保留（可压缩措辞） |
| 0.4–0.7 | 迁移到 Hindsight，从 Memory 移除 |
| 0.2–0.4 | 如果是程序知识 → 迁移到 Skill；否则直接遗忘 |
| < 0.2 | 直接遗忘 |

**压缩技术**（[[memory-compression]] 内容级压缩）：

- 合并同类：多条相关记忆 → 一条紧凑描述
- 去冗余：删除与其他系统重复的信息（如已在 config.yaml 中的配置）
- 缩写化：`数据存放规则：所有数据、软件、包都存放到 /data 目录下，不要保存在 /home/zliao 下` → `数据/软件/包存放于 /data（非 /home/zliao）`

### 2.2 Cron Job — 疲劳触发（Fatigue Trigger）

```yaml
名称: memory-fatigue-check
调度: 每 30 分钟 (*/30 * * * *)
触发条件: Memory 使用率 > 80% (>1760 chars)
动作: 执行 memory-management Skill 的压缩流程
送达: 本地保存 (local) — 静默执行，不打扰用户
```

**实现方式**：Cron Job 配合预处理脚本

```python
# ~/.hermes/scripts/memory_fatigue_check.py
# Cron 预处理脚本：检测 Memory 使用率，输出上下文供 Agent 决策
import os, yaml

memory_path = os.path.expanduser("~/.hermes/memory.md")
user_path = os.path.expanduser("~/.hermes/user_profile.md")

def get_usage(path, limit):
    try:
        with open(path) as f:
            content = f.read()
        return len(content), limit, len(content) / limit * 100
    except FileNotFoundError:
        return 0, limit, 0

mem_chars, mem_limit, mem_pct = get_usage(memory_path, 2200)
usr_chars, usr_limit, usr_pct = get_usage(user_path, 1375)

print(f"Memory: {mem_chars}/{mem_limit} chars ({mem_pct:.0f}%)")
print(f"User Profile: {usr_chars}/{usr_limit} chars ({usr_pct:.0f}%)")

if mem_pct > 80:
    print(f"⚠️ FATIGUE TRIGGER: Memory at {mem_pct:.0f}% — compression needed")
    # 输出当前 Memory 内容供 Agent 分析
    with open(memory_path) as f:
        print(f"\n--- Current Memory ---\n{f.read()}")
else:
    print(f"✅ Memory healthy at {mem_pct:.0f}% — no action needed")
```

**Cron Prompt**:

```
你是 Hermes 的记忆管理模块。根据预处理脚本输出判断是否需要压缩。

如果看到 "FATIGUE TRIGGER"：
1. 分析当前 Memory 内容
2. 用 session_search 检查每条记忆最近是否被引用
3. 对保留分数 < 0.4 的条目：
   - 程序知识 → 检查是否已有对应 Skill，没有则创建
   - 事实知识 → hindsight_retain 备份后从 Memory 移除
   - 过时信息 → 直接移除
4. 对保留的条目：尝试压缩措辞
5. 输出操作报告：压缩了什么、遗忘了什么、迁移了什么

如果看到 "no action needed"：不做任何操作，仅输出"记忆健康，无需处理"。
```

---

## 三、Phase 2 实现 — 睡眠巩固（🟡 高价值）

**目标**：每日凌晨执行"NREM 巩固"——将白天对话中的重要知识固化到长期记忆。

### 3.1 Cron Job — 定时睡眠

```yaml
名称: hermes-sleep-cycle
调度: 每天凌晨 3:00 (0 3 * * *)
送达: origin (发送到指定频道)
```

**预处理脚本**：

```python
# ~/.hermes/scripts/sleep_cycle_prep.py
# 收集"白天"的活动摘要，供 Agent 巩固
import os, json, sqlite3
from datetime import datetime, timedelta
from pathlib import Path

hermes_home = Path.home() / ".hermes"

# 1. 统计过去 24h 的 session 数量
sessions_dir = hermes_home / "sessions"
cutoff = datetime.now() - timedelta(hours=24)
recent_sessions = []

if sessions_dir.exists():
    for f in sessions_dir.glob("*.jsonl"):
        mtime = datetime.fromtimestamp(f.stat().st_mtime)
        if mtime > cutoff:
            recent_sessions.append(f.stem)

# 2. Memory 当前状态
memory_path = hermes_home / "memory.md"
user_path = hermes_home / "user_profile.md"

def read_size(p, limit):
    try:
        return len(p.read_text()), limit
    except:
        return 0, limit

mem_chars, mem_limit = read_size(memory_path, 2200)
usr_chars, usr_limit = read_size(user_path, 1375)

# 3. Skills 统计
skills_dir = hermes_home / "skills"
skill_count = sum(1 for _ in skills_dir.rglob("SKILL.md")) if skills_dir.exists() else 0

# 输出上下文
print(f"=== 睡眠周期上下文 ===")
print(f"时间: {datetime.now().strftime('%Y-%m-%d %H:%M')}")
print(f"过去24h Sessions: {len(recent_sessions)} 个")
print(f"Memory 使用: {mem_chars}/{mem_limit} ({mem_chars/mem_limit*100:.0f}%)")
print(f"User Profile 使用: {usr_chars}/{usr_limit} ({usr_chars/usr_limit*100:.0f}%)")
print(f"Skills 总数: {skill_count}")
print(f"\n最近 Sessions IDs:")
for sid in recent_sessions[:10]:
    print(f"  - {sid}")
```

**Cron Prompt**（自包含，无需外部上下文）：

```
你是 Hermes 的睡眠巩固模块。现在是凌晨，执行每日记忆巩固周期。

## Phase 1: NREM 巩固（重播与强化）

1. 用 session_search 搜索过去 24 小时的对话（按预处理输出的 session IDs）
2. 从每个 session 摘要中提取：
   - 新发现的事实/知识
   - 用户表达的新偏好或纠正
   - 反复出现的模式（如连续多次涉及同一主题）
   - 解决的困难问题（可能需要存为 Skill）
3. 对提取的知识进行分类：
   - 用户偏好 → memory(target='user') 更新
   - 环境事实 → memory(target='memory') 更新
   - 领域知识 → hindsight_retain 存入长期记忆
   - 工作流程 → 检查是否需要新建或更新 Skill
   - 百科知识 → SecondBrain wiki（如果涉及研究主题）

## Phase 2: Memory 压缩与遗忘

1. 读取当前 Memory 和 User Profile 的全部内容
2. 对每条记忆评估保留分数（时效性 × 使用频率 × 不可替代性）
3. 执行压缩：
   - 合并同类条目
   - 精简措辞（保留信息密度，减少字符数）
   - 迁移低价值条目到 Hindsight
   - 直接删除过时/冗余条目
4. 目标：Memory 使用率降至 70% 以下

## Phase 3: REM 联想（跨域发现）

1. 从今日 sessions 中取 3 个最重要的主题
2. 用 hindsight_recall 搜索这些主题
3. 用 hindsight_reflect 思考："这些主题之间有什么新的联系？"
4. 如果发现有价值的跨域联想 → hindsight_retain 保存

## Phase 4: 生成睡眠报告

输出格式：
---
🌙 睡眠周期报告 | {日期}

📥 巩固：{N} 条新知识存入长期记忆
  - [列出关键项]
  
🗜️ 压缩：Memory {之前}% → {之后}%
  - [列出压缩/合并操作]

🗑️ 遗忘：移除 {N} 条低价值记忆
  - [列出被移除的项及原因]

🔄 迁移：{N} 条知识迁移
  - [程序知识 → Skill]
  - [事实知识 → Hindsight]

💡 新发现：
  - [跨域联想结果]

📊 记忆状态：
  Memory: {X}/{2200} chars ({Y}%)
  User Profile: {X}/{1375} chars ({Y}%)
  Skills: {N} 个
  最近 Sessions: {N} 个
---
```

### 3.2 SCM 触发条件的 Hermes 近似

| SCM 触发 | Hermes 近似 | 实现 |
|---|---|---|
| 熵 > 0.9 | Memory 使用率 > 80% | 预处理脚本检测 |
| 冲突 > 0.3 | 近期 session 中有用户纠正 | Cron 内 LLM 检测 |
| 超时 1h | 每日 3:00 定时 | Cron 调度 |
| 手动触发 | 用户对话中说"整理记忆" | Skill 加载后执行 |

---

## 四、Phase 3 实现 — REM 联想与元认知（🟢 有趣但不急）

### 4.1 跨域联想（REM Dreaming）

SCM 用随机游走产生新联想。Hermes 用 **LLM 创意推理** 替代：

```
# 在睡眠周期 Phase 3 中执行

1. 取今日 top-3 主题（从 sessions 提取）
2. 对每个主题：
   a. hindsight_recall(主题A)
   b. hindsight_recall(主题B)  
   c. hindsight_reflect("主题A 和主题B 之间有什么隐含联系？")
3. 如果 reflect 结果有实质性洞察：
   a. hindsight_retain(洞察内容, context="REM联想")
   b. 写入睡眠报告的"新发现"部分
```

**与 SCM 的对比**：

| | SCM REM | Hermes REM |
|---|---|---|
| 机制 | 数学随机游走（长度5, k=3 seeds） | LLM 语义推理 |
| 可复现性 | ✅ 确定性（给定seed） | ❌ 每次不同 |
| 创造力 | 受限于图结构 | 不受限，可能更灵活 |
| 成本 | 几乎为零（图操作） | 几次 LLM 调用 |

### 4.2 Self-Model（元认知层）

在 Memory 中维护一条"自我状态"记忆：

```
§
自我记忆状态：Memory {X}%满，User Profile {Y}%满，{N}个Skills，上次睡眠巩固 {日期}，已遗忘 {M} 条。
```

每次睡眠周期更新。让 Agent 在对话中能说出："我的记忆空间还剩 30%，可能需要整理了。"

---

## 五、实施步骤

### Step 1: 创建预处理脚本 ⏱️ 5分钟

```bash
~/.hermes/scripts/memory_fatigue_check.py   # 疲劳检测
~/.hermes/scripts/sleep_cycle_prep.py        # 睡眠预处理
```

### Step 2: 创建 `memory-management` Skill ⏱️ 10分钟

包含：
- 压缩规则和保留分数公式
- 迁移操作的标准流程
- 触发条件说明

### Step 3: 创建 Fatigue Trigger Cron Job ⏱️ 2分钟

```
schedule: */30 * * * *
script: ~/.hermes/scripts/memory_fatigue_check.py
prompt: [疲劳触发 prompt]
deliver: local
skills: [memory-management]
```

### Step 4: 创建 Sleep Cycle Cron Job ⏱️ 2分钟

```
schedule: 0 3 * * *
script: ~/.hermes/scripts/sleep_cycle_prep.py
prompt: [睡眠周期 prompt]
deliver: origin (或指定频道)
skills: [memory-management]
```

### Step 5: 首次手动执行 ⏱️ 5分钟

手动跑一次睡眠周期，验证效果：
- Memory 是否成功压缩
- Hindsight 迁移是否正常
- 报告格式是否清晰

### Step 6: 观察与迭代

运行一周后评估：
- Memory 使用率趋势
- 巩固内容质量
- 是否有误删/误遗忘
- 调整保留分数权重

---

## 六、成本估算

| 操作 | 频率 | Token 消耗 | 月成本 (估) |
|---|---|---|---|
| 疲劳检测 | 48次/天 | ~500/次（大部分"无需操作"） | ~$0.50 |
| 睡眠周期 | 1次/天 | ~5000-10000/次 | ~$3-5 |
| **总计** | | | **~$4-6/月** |

注：如果疲劳检测脚本判断 Memory < 80%，Cron Job prompt 可以设为极短的"无操作"回复，几乎不消耗 token。

---

## 七、风险与缓解

| 风险 | 缓解 |
|---|---|
| 误删重要记忆 | 删除前先 hindsight_retain 备份；睡眠报告列出所有操作 |
| LLM 评估偏差 | 保留分数用启发式规则兜底（如"用户纠正"永远 1.0） |
| Cron Job 失败 | 使用 notify_on_complete，失败时通知用户 |
| 压缩丢失关键信息 | 只做措辞精简，不改变语义；重要条目标记"pin" |
| 成本失控 | 疲劳检测脚本做前置过滤，无需压缩时不触发 LLM |

---

## 八、未来扩展

### 中期（1-3月后）
- **访问追踪**：记录每条 Memory 被引用的频率（需修改 Hermes 源码或用 Hook）
- **冲突检测**：睡眠周期中检查 Memory 内条目之间是否矛盾
- **Skill 自动过时检测**：扫描 Skills 中引用的命令/API 是否仍有效

### 长期（3-6月后）
- **Hindsight 遗忘**：为 Hindsight 也实现衰减机制（目前无限增长）
- **图结构化**：基于 SecondBrain wiki 的 wikilinks 构建真正的知识图谱
- **多 Agent 记忆同步**：如果部署多个 Hermes Profile，跨 Profile 巩固共享知识

---

## References

- [[sleep-consolidated-memory]] — SCM 论文详解
- [[hermes-vs-scm-analysis]] — Hermes 与 SCM 全方位对比
- [[memory-compression]] — 压缩技术四层次
- [[memory-forgetting]] — 遗忘机制分类
- [[ai-agent-memory]] — 当前 Hermes 记忆映射与差距
- [[complementary-learning-systems]] — CLS 理论基础
- [[ai-memory-open-source-landscape]] — 可参考的开源实现
