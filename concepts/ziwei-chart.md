---
name: ziwei-chart
description: 紫微斗数排盘与解读 — 基于倪海厦《天纪》三合派体系的紫微斗数排盘引擎（14 主星 + 12 宫 + 四化 + 41 条格局 + 真太阳时校正 + 闰月四口径 + 晚子时换日），可 CLI 直接排盘出十二宫全量星曜、大限流年、格局吉凶，并基于倪师原话与古籍原文做解读。触发词：紫微斗数、命盘、排盘、算命、看命盘、十二宫、命宫、身宫、财帛宫、官禄宫、格局、合盘、大限、流年。
version: 1.0.0
author: Renhuai123/ziwei-doushu（引擎原作者）· 抽装为 Hermes Skill
license: MIT（代码）· CC BY 4.0（数据集）· 倪师原话非商用
metadata:
  hermes:
    tags: [紫微斗数, 命理, 排盘, 倪海厦, 天纪, 格局, 合盘]
    category: research
    related_skills: [nihaixia]
    source_repo: https://github.com/Renhuai123/ziwei-doushu
when_to_use: "想排一张紫微命盘（十二宫/主星/四化/大限）；问某格局的吉凶与条件；做合盘（两人关系）；查倪师《天纪》紫微原话或古籍原文（骨髓赋/斗数全书）；推大限流年运势。"
not_when: "只要一句话结论（先排盘再问细节）；精确到分钟的择时/风水/八字（另有其法）；问医疗、法律、投资决策（本 skill 是传统命理参考，不构成决策依据）。"
experiment_status: active
---

# 紫微斗数排盘与解读（Hermes 版）

> 引擎来自 [Renhuai123/ziwei-doushu](https://github.com/Renhuai123/ziwei-doushu)（MIT），本 Skill 抽出排盘内核脱离 Next.js，独立以 CLI 提供给 Hermes 调用。

---

## When to Use · 怎么用

**核心：先排盘，再解读。** 命盘数据由引擎算，解读由你（LLM）基于引擎知识库 + 命盘数据现推。

### 第 1 步：排盘

```bash
cd ~/.hermes/skills/ziwei-chart
./node_modules/.bin/tsx scripts/chart.ts \
  --year 1988 --month 10 --day 8 --hour 未时 --gender male \
  --city 上海 --patterns
```

**参数**：

| 参数 | 必填 | 说明 |
|---|---|---|
| `--year` | ✅ | 公历年 |
| `--month` | ✅ | 公历月 1-12 |
| `--day` | ✅ | 公历日（非法日期会报错，不会静默排错盘） |
| `--hour` | ✅ | 时辰：`0`=子 … `11`=亥；或中文 `子/丑/寅/卯/辰/巳/午/未/申/酉/戌/亥`；或 12-23 钟点 |
| `--clock` | — | 显式按钟点推时辰（如 `--clock 15` → 申时），避免 0-11 与钟点歧义 |
| `--gender` | ✅ | `male` / `female` |
| `--city` | — | 出生城市，用于真太阳时校正（34 省 / 484 城市，未收录则跳过并告警） |
| `--school` | — | 星曜亮度流派：`QS`（默认，斗数全书）/ `XD1` / `XD2` / `ZZ` |
| `--leap` | — | 闰月口径：`split`（默认）/ `next-month`（倪师派）/ `prev-month` / `origin-month` |
| `--target-year` | — | 运限目标年（1900-2100），输出该年大限定位、虚岁、覆盖年份 |
| `--patterns` | — | 附加格局检测结果 |
| `--json` | — | 输出完整 JSON（十二宫全量星曜 + 大限 + 运限 + 格局） |

**完整参数、口径差异、排错手册见 `references/使用说明书.md`。**

### 第 2 步：解读

排盘后读知识库：

| 想知道 | 读哪 |
|---|---|
| **完整参数/口径/排错手册** | **`references/使用说明书.md`**（10 章，最全） |
| 这个格局什么意思 | `references/patterns.md`（41 条格局速查） |
| 倪师怎么讲紫微 | `references/quotes.md`（29 条原话 + 24 集大纲） |
| 古籍原文 | `references/classics.md`（骨髓赋/斗数全集/斗数全书 75 段） |
| 两人关系合盘 | `references/heming.md`（倪师双宫联参法 + 评分标准） |

> ⚠️ **三个最容易踩的坑**（详见说明书第 5 节）：
> 1. **闰月口径**：现代年份闰月最长仅 10 天，`split` 与 `prev-month` 结果完全相同；**倪师派要显式 `--leap next-month`**。
> 2. **亮度流派**：同星不同派差 3 档（太阴旺/不/陷/闲），不可混用。默认 `QS`。
> 3. **大限无四化**：引擎按倪师「四化永远固定，大限只看宫位移动」下线了飞星派字段，**解读时不要编大限四化**。

---

## 核心定位

| Skill | 干什么 | 关系 |
|---|---|---|
| `nihaixia` | 倪师口吻答**中医**问题（伤寒论/金匮/内经/本草/医案） | 互补 |
| **`ziwei-chart`（本 Skill）** | 排**紫微斗数**命盘 + 解读 | 同源《天纪》 |

`nihaixia` 里的《天纪》紫微部分只是条目级介绍，本 Skill 是能真正排盘的完整引擎。

---

## 解读要领（引擎算盘，你来断）

### 一、读盘顺序（倪师体系）

1. **命宫** — 主星定基本格局与天生性格
2. **三方四正** — 命宫 + 财帛 + 官禄 + 迁移，决定「用武之地」
3. **身宫** — 定晚景与依归（身宫在财帛宫 = 职业妇女；七杀临身 = 一辈子多败少成）
4. **大限流年** — 十年一步的运势节拍
5. **四化** — 禄（财性守）、权（官印）、科（名声）、忌（劫杀）

> 倪师原话：「命宫为本，三方为用」「大道至简——飞星飞来飞去太复杂，不搞这个」

### 二、格局怎么看

`--patterns` 输出分三档：

- `excellent` 上格 / `good` 吉格 → 主写它的格局与适合的路
- `neutral` 中平 → 平铺直叙，不夸大
- `caution` 慎之 → 重点写破格条件，说明「哪一点要注意」

**加分项（bonus）** 让格局更强，**破格条件（breaking）** 让它打折。两者都要在解读中提到——只说好话是算命馆的做派，不是倪师的做法。

### 三、亮度要一起看

主星带庙/旺/得/利/平/不/陷七档。同是紫微，庙旺与陷的格局完全不同，不可只报星名。

### 四、古籍引证

有格局出处就引（如《紫微斗数全书·紫府同宫格》），有倪师原话就引（`references/quotes.md`）。**不确定的不要编**——知识库里没有的，就说「倪师讲义未直接讨论」。

### 五、边界

- 紫微斗数是传统命理，**不构成医疗/法律/投资建议**
- 六亲（父母/兄弟/子女）判断局限大（倪师原话：「斗数批六亲本来就比较差一点」），涉及要加保留
- 晚子时（23:00-23:59）换日规则、闰月归属、流派差异都会导致盘不同——排出来就按排出来的讲，不要擅自改口径

---

## 引擎能力清单

| 能力 | 说明 |
|---|---|
| 真太阳时校正 | 按出生地经度算时差 + 均时差 |
| 中国夏令时 | 1986-1991 年区间自动判定 |
| 闰月四口径 | 归前月 / 归后月 / 按日切分 / 按本月（默认 split） |
| 晚子时换日 | 23:00-23:59 归次日，00:00-00:59 归本日 |
| 星曜亮度 7 档 | 庙旺得利平不陷 + 3 档粗分类降级显示 |
| 亮度流派可切 | QS / XD1 / XD2 / ZZ 四派亮度表 |
| 四化与飞星 | 生年四化、大限/流年四化、飞星自化 |
| 十二神煞 | 本命层按生年支起、流年层改按流年支起 |
| 格局判定 | 41 条规则（紫府同宫、日月并明、七杀朝斗等），带吉凶分级与古籍出处 |
| 古籍原文 | 骨髓赋 / 紫微斗数全集 / 紫微斗数全书 |

---

## 目录结构

```
ziwei-chart/
├── SKILL.md
├── package.json          # 依赖 iztro + lunar-javascript
├── tsconfig.json
├── engine/               # 抽出的排盘内核（来自上游仓库）
│   ├── algorithm.ts      # 完整排盘流程
│   ├── patterns.ts       # 格局知识库
│   ├── heming-knowledge.ts
│   ├── sihua.ts          # 四化飞星
│   ├── true-solar-time.ts / dst-cn.ts / clock-adjust.ts
│   ├── school-data.ts    # 星曜亮度流派
│   ├── cities.ts         # 城市经纬度
│   ├── tianji.ts         # 倪师《天纪》原话与课程
│   └── data/             # 古籍原文
├── scripts/
│   ├── chart.ts          # 排盘 CLI（主入口）
│   ├── selftest.ts       # 引擎自检（26 项）
│   ├── export-knowledge.ts
│   └── export-patterns.ts
├── references/           # 知识库（Markdown，Hermes 直接读）
│   ├── 使用说明书.md     # 完整手册（10 章：参数/口径/解读/排错/维护）
│   ├── patterns.md       # 41 条格局速查
│   ├── quotes.md         # 倪师原话 + 24 集大纲
│   ├── classics.md       # 古籍原文
│   └── heming.md         # 合盘方法论
└── vendor/server-only/   # Next.js 标记包的空 shim
```

---

## 维护

```bash
cd ~/.hermes/skills/ziwei-chart

./node_modules/.bin/tsx scripts/selftest.ts          # 引擎自检（改动后必跑）
./node_modules/.bin/tsx scripts/export-knowledge.ts   # 重新生成知识库
./node_modules/.bin/tsx scripts/export-patterns.ts   # 重新生成格局表
```

**引擎代码是上游快照**。要更新引擎，从上游仓库同步 `engine/` 目录后重跑上面三条。

---

## 跟现有 skill 的接力关系

| 场景 | 接力 |
|---|---|
| 问中医（伤寒论/经方/针灸） | `nihaixia` skill |
| 问命理（紫微斗数排盘/解读） | 本 Skill |
| 问「倪海厦天纪讲的紫微斗数原话是什么」 | 本 Skill `references/quotes.md` |
| 问「倪海厦讲的什么中医方子」 | `nihaixia` skill |
| 两者都要（人纪+天纪合问） | 先本 Skill 排盘 → 再 `nihaixia` 断病 |
