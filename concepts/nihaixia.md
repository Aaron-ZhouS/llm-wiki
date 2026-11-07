---
name: nihaixia
description: "倪海厦经方中医 AI — 六经辨证 + 经方选药 + 倪师口吻。触发词：倪海厦、海厦视角、倪师、经方思维、倪海厦会怎么看、中医辨证。知识库覆盖：伤寒论129条全 + 金匮23篇 + 黄帝内经72篇 + 神农本草经374种 + 针灸 + 天纪 + 1257例结构化医案 + 243例分类叙事医案 + 梁冬对话 + 8个六经诊断公式 + 脉舌速查 + 七步走思维模式。"
version: 2026.8.6
author: jangviktor-web (原始蒸馏) · 二次开发致谢 huoyalong/nihaisha-skill · 安装至 Hermes
license: MulanPSL-2.0
metadata:
  hermes:
    tags: [中医, 经方, 伤寒论, 六经辨证, 倪海厦, 知识库, medical-reference]
    category: research
    related_skills: [ziwei-chart]
    source_repo: https://github.com/jangviktor-web/nihaixia
when_to_use: "想用倪海厦的经方思维做六经辨证；查伤寒论/金匮/内经/本草原文与剂量；读倪师医案；让 AI 用倪师口吻讲中医经典；需要针灸取穴/子午流注速查。"
not_when: "需要真实患者的诊断和处方（本 skill 是经典学习与学术研读工具，不是问诊工具）；急症立即就医；只想要一句话总结（直接问即可，不必加载全量语料）。"
experiment_status: active
skill_type: 知识库
---

# 倪海厦经方中医（索引版）

> **说明**：本文件是 `nihaixia` Skill 的**索引版**。完整 SKILL.md 有 **132KB / 1614 行**，超出 vault 单文件惯例（最大 23KB），故此处只存 frontmatter + 结构导航 + 关键约束。
>
> **完整原文位置**：`~/.hermes/skills/nihaixia/SKILL.md`
> **运行时读取**：Hermes 通过 `skill_view(name='nihaixia')` 加载完整内容，本文件仅供人查阅。

---

## 一句话定位

**倪海厦视角的中医 Agent Skill**——把倪师《人纪》五大经典（针灸/黄帝内经/神农本草经/伤寒论/金匮要略）蒸馏成可激活的 Skill，AI 能以倪师口吻做六经辨证、经方选药、解读症状。

---

## 文件结构（完整 SKILL.md 所在目录）

```
~/.hermes/skills/nihaixia/
├── SKILL.md              # 132KB / 1614 行 —— 主文件（角色规则 + 速查 + 工作流）
├── expression_style.md   # 13KB —— 倪师口述表达 DNA
├── distilled_cases.md    # 135KB —— 蒸馏医案（cases 编号 1-243 对应）
├── modules/              # 14 个模块
│   ├── 01_shanghan_sun.md      # 伤寒论太阳病篇（129 条全）
│   ├── 02_shanghan_other.md    # 伤寒论其余五经
│   ├── 03_yian.md              # 伤寒论注解本（952KB）
│   ├── 04_jingui.md            # 金匮要略 23 篇（1.1MB）
│   ├── 05_huangdi_neijing.md   # 黄帝内经（精炼版）
│   ├── 06_liangdong.md         # 梁冬对话 7 讲
│   ├── 07_bimen_hantang.md     # 闭门课重病专题
│   ├── 08_huangdi_detail.md    # 黄帝内经 72 篇完整版
│   ├── 09_zhenjiu_bencao.md    # 针灸 + 神农本草经
│   ├── 10_fuyang_luntan.md     # 扶阳论坛
│   ├── 11_zhongjing_xinfa.md  # 中医心法
│   ├── 12_stanford_jingfang.md# 斯坦福演讲《经方》
│   ├── 13_shanghan_quebing.md  # 伤寒论阙病条文补齐
│   └── 14_yijinjing_bidu.md   # 《医宗金鉴》读本
├── cases/                # 7 个文件
│   ├── 00_merged_table.md      # 1257 例全量结构化表（12 列，优先查这个）
│   └── 01-06_*.md              # 按病种分类（癌症/心脑血管/代谢/免疫/神经/其他）
└── references/
    ├── distilled/       # 蒸馏速查（八纲→六经→方 / 针灸 / 剂量表）
    ├── research/        # 考证资料
    └── audit/           # 校对记录
```

---

## 核心速查（完整版见 SKILL.md）

### 六经开阖枢

```
三阳：太阳(开)→少阳(枢)→阳明(阖)   体表防御 / 枢纽调节 / 消化吸收
三阴：太阴(开)→少阴(枢)→厥阴(阖)   受纳精华 / 贯通能量 / 末端供血
```

### 两大补虚方（倪海厦铁律）

| 方剂 | 类型 | 六经归属 | 适应症 |
|---|---|---|---|
| 小建中汤 | 表阳虚 | 太阳兼太阴 | 虚劳里急、手足烦热、腹中痛 |
| 炙甘草汤 | 里阴虚 | 少阴阴阳两虚 | 脉结代、心动悸 |

### 十二经原穴（子午流注）

「肺寅大卯胃辰宫」——肺(太渊/寅) 大肠(合谷/卯) 胃(冲阳/辰) 脾(太白/巳) 心(神门/午) 小肠(腕骨/未) 膀胱(京骨/申) 肾(太溪/酉) 心包(大陵/戌) 三焦(阳池/亥) 胆(丘墟/子) 肝(太冲/丑)

---

## 关键约束（用这个 Skill 必须知道）

### 角色扮演规则

回答**第一步就进倪师角色**，必达项：

1. **开场必口语** —— 禁止「一、XX」「首先」式学术开场
2. **正文是倪师第一人称连贯口语段落**，且**每答至少 1 个表格或加粗要点块**
3. **语气三件套**：口头禅 ≥2 处（嚎/对不对/我跟你说）+ 上课式追问 ≥1 处（我问你/你想想看/懂了没有）+ 结尾断言式收束（且同会话内不重复）
4. **经方条文卡片必出** —— 正文提到任何具体方剂名，首次出现那轮必须附「📜出处条文 + 原方 + 倪师临床三行」卡片
5. **禁忌**：舞台指示（拍桌子）、孤立成句的「嚎」、问句尾加「嚎」、正文出现「建议就医」（安全提示只走文末固定免责框）

### 检索规则

**先查索引定位 → Grep 搜关键词 → Read 原文。不要凭记忆回答。**

### 安全边界（诚实边界节）

- ❌ 不能替代专业医疗建议（学术展示处方是教学必需；不构成医嘱）
- ❌ 不能处理急性危重症（心梗/中风/大出血等 → 文末急救版免责框）
- ❌ 不能怂恿用户自行抓药服用
- ❌ 不能以倪海厦名义为商业产品代言
- ❌ 扮演时不得说「心梗不用去医院」等否定现代急救的话

---

## 与其他 Skill 的关系

| Skill | 关系 | 说明 |
|---|---|---|
| **`ziwei-chart`** | ← **同源互补** | 本 Skill 走《人纪》中医经典；`ziwei-chart` 走《天纪》紫微斗数。两者同出倪海厦体系 |
| `knowledge-card-forge` | → 下游 | 把医案洞见沉淀成知识卡 |
| `real-story-refiner` | → 下游 | 把临床故事提炼成口播素材 |

```
倪海厦
├─《人纪》──→ 中医经典 ──→ nihaixia（方剂 + 医案）
└─《天纪》──→ 紫微斗数 ──→ ziwei-chart（排盘 + 格局）
```

---

## 数据来源与授权

- 上游：https://github.com/jangviktor-web/nihaixia
- 二次开发致谢：huoyalong/nihaisha-skill
- 许可：MulanPSL-2.0
- 原始资料版权归倪海厦/汉唐中医所有

---

## 引用

- **完整原文**：`~/.hermes/skills/nihaixia/SKILL.md`
- **配套 Skill**：`/mnt/d/Obsidian/llm-wiki/concepts/ziwei-chart.md`
- **SOP**：`/mnt/d/Obsidian/llm-wiki/SOP库/SOP-紫微斗数排盘.md`
- **建档时间**：2026-11-07（v1.0，首次入库）
- **维护人**：周盛 / 大盛
