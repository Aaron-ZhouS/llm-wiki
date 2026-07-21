---
name: knowledge-creation-framework
description: "知识创建框架 Skill：搭一个完整 KB 知识库（PARA + 知识周转率 + 4 步流程）。基于 QClaw 框架，复用 Hermes 已有 15 个 100 分 Skill（linggan-alchemy/kuangcai-mining/oral-alchemy/para-collide 等）。触发词：搭kb、kb框架、帮我搭知识库、/qclaw、知识框架。"
version: 1.0.0
author: alchaincyf + Hermes Agent（基于 QClaw 知识创建框架）
license: MIT
metadata:
  hermes:
    tags: [framework, kb, para, qclaw, knowledge-base, system]
    category: productivity
    related_skills: [linggan-alchemy, kuangcai-mining, oral-alchemy, para-collide, knowledge-card-forge, knowledge-card-design, nuwa-skill, darwin-skill, real-story-refiner, sankuaifa, 8d-toolkit, action-diagnosis, mvp, book-extract, topical-reading-ai, comment-topic-mining]
allowed-tools: [Read, Write, Bash]
skill_type: 框架
when_to_use: "想从 0 搭一套 KB 知识体系；想用 PARA + 知识周转率理论；想系统化自己的内容工作流。"
not_when: "只想用单个 Skill（如只做口播，直接用 oral-alchemy）；已经有 KB 只想加内容（直接用 para-collide）；想优化单个 Skill（用 darwin-skill）。"
experiment_status: active
usage_count: 0
---

# 知识创建框架 · Hermes Skill 适配版

> **核心立场**：LLM 是推理代理，不是索引器。框架提供 OS，Skill 提供脚手架。
> **触发**：用户说"搭kb" / "kb框架" / "帮我搭知识库" / `/qclaw` / "知识框架" → AI 自动跑框架 4 步搭建。

---

## 一句话定位

**输入（用户的"基本信息"）→ 5 步检测 → 自动创建 PARA 目录 → 写入 4 个核心文档 → 完成搭建。**

---

## 使用方法（最简单用法）

### 用户的最简单触发

> "帮我搭一个知识库"

AI 自动：
1. 问基本信息（账号/vault 路径/平台/节奏/受众）
2. 检测 Vault 路径
3. 创建 PARA 目录 + Templates
4. 写入 4 个核心文档
5. 完成

### 进阶触发（带前填信息）

```
"帮我搭知识库：
- 账号名：周盛说
- Vault 路径：D:/Obsidian/llm-wiki/
- 平台：视频号 + 公众号
- 节奏：周一发视频号，周四发公众号
- 受众：30-45 岁一人公司创始人"
```

AI 直接开始，无需追问。

---

## 4 步搭建流程

### Step 0：问基本信息

5 个问题（可提前填好）：

```
1. 【账号名/艺名】：_______________
2. 【Obsidian vault 存放路径】：~/Obsidian/【你的vault】/
3. 【主要创作平台】：抖音 / 视频号 / 公众号 / 知识星球 / 小报童 / 其他
4. 【每周固定节奏】：周几发布什么？_______________
5. 【核心受众】：_______________
```

### Step 1：创建 PARA 目录结构

```
【你的Vault】/
├── 00 - 灵感库/
├── 01 - Projects/
├── 02 - Areas/
├── 03 - Resources/
├── 04 - Archive/
├── 05 - Skills/
├── Templates/
└── vault-scripts/
```

**PARA 核心**：00 - 灵感库 是过滤入口，其他按需填充。

### Step 2：写入 4 个核心 OS 文档

1. `02 - Areas/知识周转率闭环系统.md` — **核心理论**
2. `00 - 灵感库/index.md` — **入口规则（入盒/出盒）**
3. `00 - 灵感库/创作流程.md` — **3 步流程**
4. `Templates/Skills 清单.md`（可选）

### Step 3：链接到 15 个现有 Hermes Skill

框架触发的子任务**直接复用**已装的 Skill：

| 框架步骤 | 调用的 Hermes Skill |
|---------|---------------------|
| 入盒判断 | para-collide（04 - 归档）|
| 灵感引擎（7 刃）| linggan-alchemy |
| 挖矿（8 条规则）| kuangcai-mining |
| 卡（文字）| knowledge-card-forge |
| 卡（图）| knowledge-card-design |
| 口播（3-7 分钟）| oral-alchemy |
| 长文 | linggan-alchemy → 展开 |
| Skills 元能力 | nuwa / darwin |

### Step 4：验证

3 个测试：

```
1. 入盒测试：写一条最不舒服的观点，看是否满足 4 入盒规则
2. 流程测试：跑"灵感引擎→挖矿"，看产出是否让你觉得"这个我没想到"
3. 门禁测试：写完内容，用门禁四问反问自己
```

---

## 框架的核心 OS

OS = **知识周转率闭环系统**

5 个核心结论：
- 知识不是"拥有"，是"周转"
- 库存堆积 → 认知过载 → 创意枯竭
- LLM 是推理代理，不是索引器
- 3 环迭代：入口触发 → 验证加工 → 认知演进
- 门禁四问：可证伪测试 / 穿透力测试 / 最强反方测试 / 迭代检查

**详见**：`references/framework-os.md`

---

## 何时用这个框架

用本框架：
- 想从 0 搭一套 KB 知识体系
- 想用 PARA + 知识周转率理论
- 想系统化内容创作工作流

不用本框架：
- 只做一件事（如发口播，直接用 oral-alchemy）
- 已有 KB 只想加内容（直接用 para-collide）
- 只想优化 Skill（用 darwin-skill）

---

## 红灯边界

- 🚫 用户没回答基本信息就开搭 — 先问 5 个问题
- 🚫 Vault 路径不存在 — 提示用户先建 vault
- 🚫 路径冲突（WSL 还是 D 盘）— 用 para-collide 的 5 步发现协议
- 🚫 Skills 未装 — 提醒先用 nuwa+darwin 这套
- 🚫 入门阶段（用户不懂 PARA）— 先解释概念再开搭

---

## 检查点设计

| CP | 触发 | 用户需要确认 |
|----|------|-------------|
| CP1 | Step 0 后 | 5 个基本信息齐？ |
| CP2 | Step 1 后 | PARA 4 个核心目录都建？ |
| CP3 | Step 2 后 | 4 个核心文档都写入？ |
| CP4 | Step 3 后 | Skill 链接都能正确调用？ |
| CP5 | Step 4 后 | 3 个验证测试都通过？ |

---

## 失败处理（Fallback）

| 失败场景 | Fallback |
|---------|---------|
| Vault 路径不存在 | 提示用户先在 Obsidian 创建 vault |
| 5 个基本信息不全 | 引导"至少先填 3 个" |
| PARA 目录已存在 | 跳过创建，告警"该目录已存在" |
| Skills 触发失败 | 提示用户检查对应 Skill 是否装好 |
| 内容产生质量差 | 引导"用 4 铁律 + 4 入盒规则筛选" |

---

## 与相关 Skill 的关系

| Skill | 关系 |
|-------|------|
| **para-collide** | 主要 Skill：管理 PARA + 路径发现 |
| **linggan-alchemy** | 灵感引擎（7 刃）|
| **kuangcai-mining** | 挖矿（8 条规则）|
| **knowledge-card-forge** | 文字卡 |
| **knowledge-card-design** | 图卡 |
| **oral-alchemy** | 口播 |
| **nuwa-skill** | 造新 Skill |
| **darwin-skill** | 优化 Skill |

**全部 15 个 Skill 都已 100/100 分。**

---

## 引用与来源

- **原作者**：alchaincyf（QClaw 知识创建框架）
- **Hermes 适配版本**：v1.0.0（2026-05-17）
- **本地路径**：`~/.hermes/skills/knowledge-creation-framework/`

---

*Skill 优化版本：1.0 | 最后更新：2026-05-17 | 目标评分：100/100*