# bandz-indicators fork

Fork 自 [samuelharting/bandz-indicators](https://github.com/samuelharting/bandz-indicators)。

## 这是什么

**9 个完整 ICT 交易指标，19,868 行 Pine v6 源码。**

| 指标 | 行数 | 内容 |
|---|---|---|
| `Bandz-All-in-One.pine` | **4,091** | ICT 交易工具全集 |
| `HTF_Statistical_Zones.pine` | 2,382 | 高低周期统计区、价格目标 |
| `Bandz_Po3_Profiler.pine` | 2,263 | PO3 剖析 |
| `Bandz-SMT.pine` | 2,255 | 多周期背离（SMT/SSMT） |
| `Bandz-STDV-Flow.pine` | 2,238 | PO3、标准差投影、CISD |
| `Bandz-Sessions.pine` | 1,953 | Killzones、开盘区间、ORG |
| `Bandz-HTF.pine` | 1,712 | 高周期 K 线、PSP、SMT |
| `Bandz-Intraday.pine` | 1,516 | Macros、FVG、时间周期 |
| `Bandz-Levels.pine` | 1,458 | NWOG、NDOG、ADR 关键位 |

平均 **2,207 行/脚本**——不是单行指标，是完整交易系统。

## 许可

**MPL-2.0**。可以用、可以改、可以商用，修改后的文件需保持 MPL-2.0。

## 同步

| 项 | 值 |
|---|---|
| 上游 | `samuelharting/bandz-indicators` (main) |
| 频率 | 每周一 **02:45 UTC** = 北京时间 **10:45** |
| 冲突 | 自动回滚 + 开 issue |

手动触发：
```bash
gh workflow run sync-upstream.yml --repo gansx/bandz-indicators
```

## ICT 概念速查

| 缩写 | 全称 | 含义 |
|---|---|---|
| FVG | Fair Value Gap | 公平价值缺口（三根 K 线中间的空档） |
| PO3 | Power of 3 | 积累-操纵-派发三阶段 |
| SMT | Smart Money Technique | 多品种/多周期背离 |
| CISD | Change in State of Delivery | 交付状态改变 |
| NWOG | New Week Opening Gap | 周开盘缺口 |
| NDOG | New Day Opening Gap | 日开盘缺口 |
| ADR | Average Daily Range | 日均波幅 |
| ORG | Opening Range Gap | 开盘区间缺口 |
| Killzone | — | 特定交易时段（伦敦/纽约开盘） |

## 和缠论的关系

**理论不同，工程互补**：

- 缠论：结构（分型→笔→线段→中枢）
- ICT：订单流（缺口→流动性→时间窗）

**可迁移的工程手段**：
- 多周期数据同步（`Bandz-HTF` 的 PSP 机制）
- 会话/时间窗划分（`Bandz-Sessions` 的 Killzones）
- 关键价位计算（`Bandz-Levels` 的 ADR/NWOG/NDOG）
- 缺口识别（`Bandz-Intraday` 的 FVG）
