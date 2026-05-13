# Wiki Schema

## Domain
AI研究 / 一人公司 / 个人成长 — 三个领域交叉的知识库。
核心理念：知识复用而非重复发现，持续积累而非一次性查询。

## Conventions
- 文件名：lowercase-hyphens，禁用空格（如 `transformer-architecture.md`）
- 每个页面顶部必须有 YAML frontmatter（见下方）
- 使用 `[[wikilinks]]` 链接其他页面，每页至少 2 个外链
- 更新页面时必须更新 `updated` 日期
- 每个新页面必须加入 `index.md` 对应板块
- 所有操作必须追加到 `log.md`
- 引用 3+ 来源的页面，在相关段落末尾加 `^[raw/articles/source-file.md]` 溯源标记
- 单来源页面：frontmatter 的 `sources:` 足够，无需溯源标记

## Frontmatter
```yaml
---
title: Page Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | comparison | query | summary
tags: [from taxonomy below]
sources: [raw/articles/source-name.md]
# 可选质量信号：
confidence: high | medium | low
contested: true
contradictions: [other-page-slug]
---
```

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

## Page Thresholds
- **建页面**：某实体/概念出现在 2+ 来源中，或在一个核心来源中被重点讨论
- **合并到现有页**：某内容已被现有页面覆盖
- **不建页面**：仅一次性提及、细枝末节、或超出领域范围的内容
- **拆分页面**：页面超过 ~200 行时，拆分为子主题并交叉链接
- **归档**：内容完全过时时移至 `_archive/`，从 index.md 移除

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

## Obsidian Integration
- `[[wikilinks]]` 自动渲染为可点击链接
- Graph View 可视化知识网络
- YAML frontmatter 支持 Dataview 查询
- 附件文件夹设为 `raw/assets/`
- 建议安装 Dataview 插件
