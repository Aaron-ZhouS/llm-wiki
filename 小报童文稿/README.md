---
title: 小报童文稿库（README）
type: meta
status: active
created: 2026-08-06
tags: [meta, 小报童, 文稿库, 触发词, SOP]
audience: ai-agent + self
related: [[我的知识库怎么用]], [[知识周转率闭环系统]]
---

# 小报童文稿库

> 专门存放「大盛已发布 / 即将发布到小报童（xiaobaotong.com）的文稿」的地方。
> 每篇文稿独立成文件，便于 Obsidian 改稿、git 备份、二次复用（转视频号口播 / 公众号 / 知识卡片）。

---

## 触发词（AI agent 必读）

**用户说以下任何一句，立刻把内容写进本目录：**

| 触发词 | 动作 |
|--------|------|
| "放小报童文稿库" | 把当前草稿写到 `小报童文稿/` |
| "这篇发小报童" | 同上 |
| "写小报童文：主题 XXX" | 新建一篇文稿，文件名 `YYYY-MM-DD-主题-小报童.md` |
| "归档小报童" | 把已发布的文稿从草稿目录归档到本目录，添加 `status: published` |

**不要做的：**

- ❌ 不要写到 `Articles/`（那是杂文/读书笔记用）
- ❌ 不要写到 `Knowledge-Cards/`（那是单点知识卡）
- ❌ 不要写到 `/home/aaron/workspace/`（那是临时草稿）

---

## 文件命名规范

```
YYYY-MM-DD-主题关键词-小报童.md
```

示例：
- `2026-08-06-可运行的知识-小报童.md`
- `2026-08-13-一人公司最小闭环-小报童.md`

---

## 单篇文稿 frontmatter 标准

每篇文稿开头必须包含：

```yaml
---
title: 文章标题
type: xiaobaotong-draft  # 或 xiaobaotong-published
status: draft | published
created: YYYY-MM-DD
published: YYYY-MM-DD  # 发布后填
xiaobaotong_url: https://xiaobaotong.com/...  # 发布后填
tags: [主题1, 主题2]
audience: 一人公司新手IP读者
summary: 一句话简介（前100字露出用）
title_candidates:  # 备选标题
  - 标题A
  - 标题B
  - 标题C
video_tags: ["#xxx", "#yyy", "#zzz"]  # 视频号配套
source_materials:  # 基于哪些知识库素材写的
  - "[[audit/new/daily-review-2026-06-01]]"
  - "[[Knowledge-Cards/可以运行的知识卡片]]"
---
```

---

## 文件结构（每篇正文内）

```markdown
# 标题

[正文]

---

## 配套发布包（小报童编辑器直接复制）

### 标题（3 选 1）
- ...

### 简介（前 100 字）
> ...

### 视频号标签（3 个）
\`\`\`
#xxx #yyy #zzz
\`\`\`

---

## changelog
- 2026-08-06 初稿
- 2026-08-07 发布到小报童 + 填 published / xiaobaotong_url
```

---

## 工作流（写→发→回收）

```text
写稿（Hermes + 你口述）
   ↓
落到 D 盘 小报童文稿/YYYY-MM-DD-主题-小报童.md
   ↓
Obsidian 改稿、git 自动备份
   ↓
复制正文到小报童编辑器
   ↓
发布 → 把 status 改 published，填 xiaobaotong_url 和 published 日期
   ↓
配套：转视频号口播 / 知识卡片 / 公众号短版（可选）
```

---

## 与其他目录的关系

| 目录 | 用途 | 是否同步 |
|------|------|----------|
| `Articles/` | 杂文 / 读书笔记 / 翻译稿 | 不进 |
| `Knowledge-Cards/` | 单点洞见卡 | 不进 |
| `口播素材/` | 视频号 30-40 秒口播 | 不进 |
| `小报童文稿/`（本目录） | **小报童专属长文** | ✅ |

---

## 引用与维护

- 创建者：大盛 + Hermes Agent
- 创建时间：2026-08-06
- 维护原则：每周日浏览一次，已发布但还没归档的稿件改成 published