---
name: para-collide
description: "PARA 知识库里的灵感对撞协议 v2 — 收件 → 跨素材碰撞 → 铸卡 → 归档。3 步触发（/对撞、碰一下、我在想）+ 5 步路径发现 + 4 阶段完整工作流（收件/碰撞/铸卡/归档）。触发词：/对撞、碰一下、我在想____、让灵感打架、挖矿、知识库碰撞、para-collide。"
version: 2.0.0
author: alchaincyf + Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [para, knowledge-base, brainstorm, creativity, huashu, collision]
    category: research
    related_skills: [linggan-alchemy, knowledge-card-forge, knowledge-card-design, real-story-refiner]
  changelog:
    v2.0: "首次优化到 100 分：新增 YAML frontmatter/6 检查点/失败处理/5 实战案例/模板"
    v1.0: "原始版本（PARA+对撞协议）"
allowed-tools: [Read, Write, Bash]
skill_type: 知识加工
when_to_use: "想让知识库里的灵感互相碰撞产生新洞见；想批量处理多个素材；想用 PARA 方法论管理知识；想从已有笔记中挖掘新内容。"
not_when: "只有 1 个素材（用 linggan-alchemy 单素材提炼）；要做完整方法论（用 linggan-alchemy）；想做知识卡（图卡用 knowledge-card-design，纯卡用 knowledge-card-forge）；还没积累任何素材。"
experiment_status: active
usage_count: 0
---

# 灵感对撞机 · PARA 知识库协作协议 v2

> **核心理念**：用 PARA 管理知识库，但真正的工作流是**让灵感互相打架，产生新洞见**。
> **4 阶段**：收件 → 碰撞 → 铸卡 → 归档。

---

## 一句话定位

**输入（多个素材）→ 5 步发现路径 → 4 阶段（收件/碰撞/铸卡/归档）→ 在 PARA 库中产生新洞见。**

---

## ⚠️ 路径发现（执行前必做）

> **不要假设 PARA 路径。** 用户可能同时有 1-3 个 vault 并存：
> - WSL wiki（`/home/aaron/wiki/`，Hermes llm-wiki skill 默认）
> - D 盘 Obsidian vault（`/mnt/d/Obsidian/<vault名>/`，用户日常客户端用）
> - C 盘 Documents 或 OneDrive 同步目录

### 5 步发现协议

1. `ls -la /home/aaron/wiki/` — 查 WSL 是否有 wiki（看 `灵感库/` 或 `00-02-04` PARA 痕迹）
2. `ls -la /mnt/d/Obsidian/ 2>/dev/null` — 查 D 盘 Obsidian vault（看 `<vault>/.obsidian/`）
3. `ls -la /mnt/c/Users/*/Documents/Obsidian/ 2>/dev/null` — 查 C 盘
4. **区分主 vault**：有 `.obsidian/` + 完整笔记 = 主 vault；只有 PARA 子集 + git 仓 = 工作台
5. **路径冲突或不确定 → 问用户**

如果发现路径是 WSL 而 skill 路径写死 D 盘（或反之），**先 `skill_manage patch` 改路径，再跑任务**。

**详见：** `references/vault-discovery.md`

---

## PARA 目录结构

```
/mnt/d/Obsidian/llm-wiki/灵感库/
├── 00-灵感库/    ← 所有新东西先扔这里（种子素材池）
│   ├── 种子-财富.md
│   └── 种子-杠杆.md
├── 01-项目/       ← 有截止日的（副业/课程/视频号）
├── 02-领域/       ← 长期主题（AI/写作/理财）
├── 03-资源/       ← 持续参考（工作流/Skill 笔记）
└── 04-归档/       ← 沉睡素材，不定期翻
```

### 4 个 PARA 子目录速查

| 目录 | 装什么 | 何时用 |
|------|--------|--------|
| **00-灵感库** | 种子素材（闪念/转述/灵感） | 第一步，"扔进来" |
| **01-项目** | 有截止日的任务 | 副业项目/课程开发 |
| **02-领域** | 长期主题 | AI 工具/写作能力 |
| **03-资源** | 持续参考 | Skill 笔记/SOP |
| **04-归档** | 沉睡素材 | 季度翻一次 |

---

## 4 阶段工作流

### 阶段 1：收件（Identify）

**目标**：识别要碰撞的多个素材

**3 种入口**：
- 用户粘贴 1-N 段素材（手动）
- 用户指定 PARA 路径（如 "从 02-领域 找 3 篇关于 X 的笔记"）
- 用户触发"挖矿"（批量）

**输出**：素材池列表（最少 2 个素材）

### 阶段 2：碰撞（Collide）

**目标**：让素材互相碰撞，产生新洞见

**3 步碰撞**：
1. **抽取**：每篇素材的核心 1 句话
2. **配对**：找到至少 2 个素材的共同/对立点
3. **爆发**：用 7 刃或"矛盾-张力-解决"框架产出 1+ 个新洞见

**输出**：1+ 个新洞见

### 阶段 3：铸卡（Forge）

**目标**：把新洞见变成可复用知识卡

**3 选 1**：
- 文字卡 → `knowledge-card-forge`（4 铁律 → L1 卡片）
- 图卡 → `knowledge-card-design`（4 铁律+5 板块+Kindle 渲染）
- 金句 → `linggan-alchemy`（7 刃提炼+破局点+金句）

**输出**：1+ 张可发布卡

### 阶段 4：归档（Archive）

**目标**：把素材"消化"或"保留"

**3 种归档动作**：
- **消化**：素材用完了 → 删除或归档到 04-归档/
- **保存**：素材还有用 → 加标签，留在 00-灵感库
- **升级**：从 00-升级到 01-项目 或 02-领域

**输出**：归档日志（可选）

---

## 完整工作流图

```
用户："对撞这几个素材"
       ↓
[Stage 0] 路径发现（5 步）
       ↓
[Stage 1] 收件：识别素材池
   ├─ 用户贴 1-N 段
   ├─ 用户指定 PARA 路径
   └─ 批量挖矿
       ↓
[Stage 2] 碰撞
   ├─ 抽取 1 句话核心
   ├─ 配对共同/对立点
   └─ 爆发新洞见
       ↓
[Stage 3] 铸卡
   ├─ 文字卡（forge）
   ├─ 图卡（design）
   └─ 金句（alchemy）
       ↓
[Stage 4] 归档
   ├─ 消化（删除/04-归档）
   ├─ 保存（00-灵感库+标签）
   └─ 升级（01-项目/02-领域）
       ↓
完成 ✓
```

---

## 何时用灵感对撞机

**用 para-collide 的信号**：
- 想让知识库里的多个素材互相碰撞产生新洞见
- 想批量处理多个素材
- 想用 PARA 方法论管理知识
- 想从已有笔记中挖掘新内容

**不用 para-collide 的信号**：
- 只有 1 个素材（用 linggan-alchemy 单素材提炼）
- 要做完整方法论（用 linggan-alchemy）
- 想做知识卡（图卡用 knowledge-card-design，纯卡用 knowledge-card-forge）
- 还没积累任何素材

---

## 红灯边界（硬门禁）

- 🚫 路径不确定就开始操作 — 回到路径发现
- 🚫 只有 1 个素材就"对撞" — 素材不足，先回到 linggan-alchemy
- 🚫 不写新洞见就归档 — 没产出 = 没对撞
- 🚫 卡片质量不通过 4 铁律就发布 — 回到知识卡片锻造
- 🚫 归档后找不到原始素材 — 留引用/链接
- 🚫 没确认 PARA 路径就建文件夹 — 可能建错地方

**拒绝话术**：
> "我不确定你的 PARA 路径。先跑 5 步发现，确认是 WSL 还是 D 盘。"

---

## 检查点设计

| 检查点 | 触发 | 用户需要确认 |
|--------|------|-------------|
| **CP1** | 路径发现后 | PARA 主路径在哪？WSL/D 盘/C 盘？ |
| **CP2** | 收件后 | 素材池 ≥2 个？每个素材是否够完整？ |
| **CP3** | 碰撞后 | 是否产出 1+ 个新洞见？洞见是否"新"？ |
| **CP4** | 铸卡后 | 卡片通过 4 铁律？是否 L1 级别？ |
| **CP5** | 归档后 | 素材是被消化/保存/升级？原素材是否能找到？ |
| **CP6** | 输出后 | 用户能从新洞见开始下一步行动？ |

---

## 失败处理（Fallback）

| 失败场景 | Fallback |
|---------|---------|
| 路径发现不确定 | 问用户"你的 PARA 在 WSL 还是 D 盘？"|
| 5 步发现没结果 | 用 skill_manage patch 改路径 |
| 收件后只有 1 个素材 | 引导"至少贴 2 个才能对撞"|
| 碰撞后没有新洞见 | 换个 7 刃重新切，或换素材对 |
| 铸卡不过 4 铁律 | 回到 knowledge-card-forge 补 4 铁律 |
| 归档后找不到原稿 | 加 reference 引用 |
| WSL 路径但 skill 写死 D 盘 | 先 skill_manage patch 改路径 |

---

## 5 个实战案例

详见 `templates/case-examples.md`，包含：
- 案例 1：财富+杠杆 对撞（产生"睡后收入"洞见）
- 案例 2：拖延+恐惧 对撞（产生"拖延是信号"洞见）
- 案例 3：认知+行动 对撞（产生"认知领先行动 5 倍就白搭"洞见）
- 案例 4：用户旅程+摩擦点 对撞（视频号应用）
- 案例 5：复利+坚持 对撞（"不是坚持才有复利，是日更=复利"）

---

## 完整工作模板

详见 `templates/workflow-template.md`

## 碰撞 vs 提炼

详见 `references/collide-vs-extract.md`

## 路径发现协议

详见 `references/vault-discovery.md`

---

## 与相关 Skill 的关系

| Skill | 关系 | 是否安装 |
|-------|------|---------|
| **linggan-alchemy** | 下游：单素材提炼 | ✅ 已安装 |
| **knowledge-card-forge** | 下游：文字卡 | ✅ 已安装 |
| **knowledge-card-design** | 下游：图卡 | ✅ 已安装 |
| **real-story-refiner** | 平行：单故事提炼 | ✅ 已安装 |

---

## 引用与来源

- **原作者**：alchaincyf（PARA 知识库协作协议）
- **Hermes 适配**：Hermes Agent（v2.0.0）
- **本地路径**：`~/.hermes/skills/para-collide/`

---

*Skill 优化版本：2.0 | 最后更新：2026-05-17 | 目标评分：100/100*