---
title: "高通 AR1+ 芯片"
tags: [chip, qualcomm, smart-glasses, ar-platform, hardware]
date_created: 2026-05-17
date_modified: 2026-05-17
related: ["[[meta-ray-ban-glasses]]", "[[meta-ray-ban-scriber-blazer]]", "[[meta-display-hypernova]]"]
---

# 高通 AR1+ 芯片

智能眼镜专用 SoC，是 **AR1** 的迭代版本，首发于 **Meta Ray-Ban Scriber / Blayzer (2026)**。命名上是小版本号，但与 AR1 在基线（baseline）上有本质区别——足以让软件功能错位。

## 关键差异

| 维度 | AR1 | AR1+ |
|------|-----|------|
| 待机功耗 | 基线 | **更低**（核心改进） |
| 性能 | 基线 | 无显著提升 |
| 软件基线 | 成熟 | 与 AR1 有差别，需重新适配 |

## 功能缺失（截至 2026-05）

AR1+ 眼镜（Scriber / Blayzer）相比 AR1 眼镜（Wayfarer Gen 1/2 等）**暂时缺失**以下功能，App 设置里有开关但无实际效果：

### Conversation Focus（对话聚焦）
- AR1 全系支持
- AR1+ 暂缺
- 用于嘈杂环境中聚焦正前方人声

### 自动调音（Auto Volume / 风噪自动调节）
- AR1 全系支持，体感"特别好"
- AR1+ 暂缺
- 典型场景：开车时摇下车窗，AR1 眼镜会瞬间提高音量盖过风噪
- 当前 AR1+ 眼镜会被风噪盖住

## 为什么会出现软件代差

[[dianwan-keji-ak]] 从开发侧朋友打听到的解释：
- AR1 与 AR1+ 命名近似，但**底层基线（baseline）有差别**
- Meta 在新基线上需要重新做功能验证（QA / 灰度推送）
- 不是 Meta 不想做，是开发节奏跟不上硬件出货

预期：未来固件推送会陆续补齐，因为这些功能在 AR1 已经实现，"最新款眼镜不支持不是很奇怪吗"。

## 续航现实

即使 AR1+ 待机更省电：
- 实测一副仍**撑不到一天**（早上戴 → 下午 3-4 点没电）
- 包括正常听音乐 / 播客 / 偶尔 AI 调用，无密集拍摄
- 比 AR1 续航强，但还**没有结实到能取代双眼镜轮换**
- 详见 [[smart-glasses-form-factor]] 的双眼镜策略

## 灰度测试与 SKU 碎片化

Meta 在芯片之上又用账号灰度测试切分功能，造成同款眼镜不同账号体验不一致：
- 国内账号 Meta AI 接入：长期使用后会被"白名单"
- [[dianwan-keji-ak]] 反对折腾尾插 GPS / 海外节点 / 国外号码，主张"长期用就会轮到你"

## 行业意义

AR1+ 体现了一个普遍模式：**硬件迭代节奏 > 软件适配节奏**。
- 新芯片的"省电"是真实卖点
- 但被首发的型号会有 6-12 个月的功能空窗期
- 早期买家承担软件等待成本

对消费者建议（来自 [[dianwan-keji-ak]]）：
- 如果你重度依赖 Conversation Focus / 自动调音，**别买首发 AR1+ 眼镜**
- 如果只关心拍照 / 听歌 / 偶尔 AI，AR1+ 体验已经够好

## References

- 视频源：[[smart-glasses-2026-dianwan]] — 2026 年智能眼镜怎么选
