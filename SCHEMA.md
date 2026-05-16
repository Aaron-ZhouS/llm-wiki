# Wiki Schema

## Domain
AI研究 / 一人公司 / 个人成长 — 三个领域交叉的知识库。
核心理念：知识复用而非重复发现，持续积累而非一次性查询。

---

## 多路径 Raw 配置

支持多个 raw 输入源，可在 frontmatter 或 `raw-config.yaml` 中配置：

```yaml
# 方式1：frontmatter 中配置
raw-paths:
  - raw/articles/      # 原始文章
  - raw/notes/         # 临时笔记
  - raw/tweets/        # 抓取的推文

# 方式2：单独配置文件 raw-config.yaml
# raw-paths:
#   - raw/articles/
#   - raw/notes/
```

规则：
- 多路径按顺序优先取第一个存在的文件
- 引用时用 `^[raw/articles/source-file.md]` 溯源标记

---

## Conventions
- 文件名：lowercase-hyphens，禁用空格（如 `transformer-architecture.md`）
- 每个页面顶部必须有 YAML frontmatter（见下方）
- 使用 `[[wikilinks]]` 链接其他页面，每页至少 2 个外链
- 更新页面时必须更新 `updated` 日期
- 每个新页面必须加入 `index.md` 对应板块
- 所有操作必须追加到 `log.md`
- 引用 3+ 来源的页面，在相关段落末尾加 `^[raw/articles/source-file.md]` 溯源标记
- 单来源页面：frontmatter 的 `sources:` 足够，无需溯源标记

### Mermaid 规范（强制）
- **所有架构图、流程图、状态图必须使用 mermaid 代码块**
- **禁止使用截图/图片替代图表**
- 示例：
  ```mermaid
  graph TD
    A[输入] --> B[处理]
    B --> C[输出]
  ```

---

## Frontmatter

```yaml
---
title: Page Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | comparison | query | summary
tags: [from taxonomy below]
sources: [raw/articles/source-name.md]

# 质量信号（每页必须填写）
confidence: high | medium | low   # 默认值：medium
contested: true | false           # 是否有争议/未形成共识
contradictions: [other-page-slug] # 与之矛盾的其他页面
---
```

### 质量信号说明

| 字段 | 必填 | 说明 |
|------|------|------|
| `confidence` | 是 | `high`=多方印证/权威来源；`medium`=单一来源或推测；`low`=存疑/争议内容 |
| `contested` | 否 | 设为 `true` 表示该内容存在广泛争议 |
| `contradictions` | 否 | 列出与之存在矛盾的其他页面 slug |

**注意**：`confidence` 每页必须填写，未填写时默认 `medium`。

---

## Tag Taxonomy
按领域分四大类，每类下定义具体标签：

**AI研究：**
- AI模型: model, architecture, benchmark, training, fine-tuning
- AI技术: inference, alignment, rag, agent, reasoning
- AI应用: tool, productivity, automation

**一人公司：**
- 商业: startup, monetization, client, product, pricing
- 内容: content, video, social-media, audience
- 工具: workflow, automation, stack

**个人成长：**
- 成长: habit, learning, goal, mindset, psychology
- 健康: health, energy, productivity
- 关系: network, relationship, communication

**通用：**
- Meta: comparison, timeline, controversy, prediction, meta

规则：使用标签前必须先在本 taxonomy 中定义，新增标签需先写到这里再使用。

---

## Page Thresholds
- **建页面**：某实体/概念出现在 2+ 来源中，或在一个核心来源中被重点讨论
- **合并到现有页**：某内容已被现有页面覆盖
- **不建页面**：仅一次性提及、细枝末节、或超出领域范围的内容

### 文件拆分规则
- **自动拆分**：单文件超过 200 行时，自动拆分为子主题页面
- **交叉链接**：拆分后的子页面需在原页面和相关子页面之间建立双向链接
- **超大文件**：超过 500 行的文件移至 `_raw/` 目录，页面只引用路径不复制内容
  ```markdown
  > 完整内容见 [[_raw/large-document]]
  ```

### 归档规则
- 内容完全过时时移至 `_archive/`，从 index.md 移除
- 归档页在 frontmatter 添加 `archived: true`

---

## index.md 结构

每个 domain 板块包含：页面计数、最近更新时间、页面列表

```markdown
## AI研究
页面数：XX | 最近更新：YYYY-MM-DD
- [[page-1]] - 更新于 YYYY-MM-DD
- [[page-2]] - 更新于 YYYY-MM-DD

## 一人公司
页面数：XX | 最近更新：YYYY-MM-DD
- [[page-3]] - 更新于 YYYY-MM-DD

## 个人成长
页面数：XX | 最近更新：YYYY-MM-DD
- [[page-4]] - 更新于 YYYY-MM-DD
```

---

## 日志轮换策略

### 主日志 log.md
- **格式**：`| date | action | subject | link |`
- **保留**：最新 30 天索引
- **最大条目**：500 条

### 历史日志
- 超过 500 条时，触发轮换
- 历史日志文件：`log-YYYY-MM-DD.md`（轮换时的日期）
- 轮换后创建新的空 log.md（保留表头）

### 轮换触发条件
1. 条目数 > 500
2. 时间跨度 > 30 天（取最新日期）

---

## Entity Pages
每个 notable 实体一页，含：
- 概述/是什么
- 关键事实和日期
- 与其他实体的关系 ([[wikilinks]])
- 来源引用

## Concept Pages
每个概念/主题一页，含：
- 定义/解释
- 当前认知状态
- 开放问题或争议
- 相关概念 ([[wikilinks]])

## Comparison Pages
对比分析页，含：
- 对比对象及原因
- 对比维度（建议表格格式）
- 结论或综合判断
- 来源

## Update Policy
新信息与现有内容冲突时：
1. 看日期 — 通常新来源覆盖旧来源
2. 真正矛盾时，两说并存，注明日期和来源
3. frontmatter 标记：`contradictions: [page-name]`
4. lint 时提出供用户 review

---

## Obsidian Integration
- `[[wikilinks]]` 自动渲染为可点击链接
- Graph View 可视化知识网络
- YAML frontmatter 支持 Dataview 查询
- 附件文件夹设为 `raw/assets/`
- 建议安装 Dataview 插件