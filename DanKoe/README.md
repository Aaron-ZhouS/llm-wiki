---
title: Dan Koe 视频学习库
created: 2026-05-31
updated: 2026-05-31
type: summary
tags: [learning, content, productivity, workflow]
sources:
  - "https://www.youtube.com/@DanKoeTalks"
confidence: high
contested: false
contradictions: []
---

# Dan Koe 视频学习库

## 用途

这个文件夹用于每天学习 Dan Koe 的一个 YouTube 视频，并沉淀为 Obsidian 文章。

默认规则：

- 每天只处理一个视频。
- 优先选择频道中尚未入库的最新视频。
- 如果拿到字幕，以字幕为主要依据。
- 如果没有字幕，只基于标题、简介、章节和公开资料整理，并在文章中标注可信度。
- 产出先保存在本文件夹，不直接改 `concepts/`、`entities/`、`Synthesis/`。
- 信息图优先采用手绘视觉笔记风格 SVG：中文大标题、暖橙高亮、黑色线条、中心树/路径结构、图标化模块。Mermaid 只作为草图或备用。
- 如果某篇内容值得升级为概念页或知识卡片，先在文章末尾列出建议，等用户确认后再处理。

## 文章命名

```text
YYYY-MM-DD - 视频标题.md
```

如果标题过长，可以压缩为 20-40 个中文或英文关键词。

## 文章结构

每日文章使用 [[_template-dankoe-video-note]]，包括：

- 来源信息
- 一句话总结
- 核心观点
- 详细学习笔记
- NotebookLM 式知识信息图
- 可执行行动
- 可拆分原子笔记建议
- 与个人内容创作/一人公司/学习系统的连接

## 与 Hermes 的边界

本文件夹遵守 [[codex-hermes-collaboration]]：

- Codex 只负责用户明确触发或定时触发的 Dan Koe 视频学习文章。
- Hermes 继续负责知识库主流程、audit、综合洞察和长期结构维护。
- DanKoe 文件夹内的内容可以被 Hermes 后续吸收，但 Codex 不主动推入核心概念层。
