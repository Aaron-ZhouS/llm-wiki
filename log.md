# Wiki Log

## [2026-10-06] curate | 新建电子书库（电子书结构化笔记库）
- 新增目录: `电子书库/`（跟 `小报童文稿/` `公众号文章/` 对称）
- 范围: 大盛读过的电子书笔记,原件 PDF/EPUB 放 D 盘 `08 电子书/`,本库只存 markdown
- 三件套已就位:
  - [[电子书库/README]] — 触发词词典 + 命名规范 + frontmatter 标准
  - [[电子书库/_模板]] — 新书笔记模板(直接复制改书名)
  - [[电子书库/index]] — 已读/在读/待读 三栏索引 + 扫描报告
- 顶层 [[index]] 同步添加「电子书库」章节
- 触发词:「这本放电子书库」「笔记整理一下放电子书库」「写一本电子书:书名 XXX」

## [2026-10-06] scan | D 盘电子书架扫描（21 文件 → 8 EPUB 可读 / 11 PDF 跳过）
- 用 stdlib `zipfile` + `lxml` 抽取 EPUB 正文到 `/tmp/ebook_dumps/`(无需 pdftotext/pymupdf)
- 8 本 EPUB 全部 OK:打造第二大脑 / 卡片笔记写作法 / 关键对话 / 掌控习惯 / 重新认识学习 / 逻辑思考的艺术 / TED 思想的力量 11 册套装
- 11 本 PDF 跳过原因:WSL 无 PDF 解析库 + PyPI 代理通道故障;需用户用 Edge 复制正文或截图 OCR
- 优先级排序已写入 [[电子书库/index]] — 最高优先:打造第二大脑 + 卡片笔记(对口一人公司+Obsidian)

## [2026-10-06] ingest | 完成 2 本最高优先级笔记(打造第二大脑 + 卡片笔记写作法)
- [[2026-10-06-打造第二大脑-电子书]] — PARA + CODE + 项目启动清单,直接套用到 Obsidian 工作流;13 章摘要 + 16 金句 + 5 个具体动作
- [[2026-10-06-卡片笔记写作法-电子书]] — 卢曼 Zettelkasten + 三类笔记 + 必要难度,直接验证现有 vault 结构;15 章摘要 + 16 金句 + 5 个具体动作
- 两本书互相印证:① "思想群岛"(打造第二大脑) = "发展想法"(卡片笔记)= 同一个动作 ② "渐进式归纳" = "必要难度" = 同一原理
- 本周要落地的 5 个动作已写入笔记末尾;同步到 [[电子书库/index]] 已读列表

## [2026-06-28] ingest | 每日复盘：胡子哥《普通人怎么改变命运》— 复用思维
- 复盘原文: audit/new/daily-review-2026-06-28.md
- 短视频选题: entities/video-topics/daily-review-2026-06-28.md
- 金句卡片: Knowledge-Cards/daily-review-2026-06-28-insight.md
- 核心洞见: 资产思维四问 + 每周最忙5件事审计法

## [2026-06-21] ingest | Dan Koe multiple interests one-person business video
- Source: https://www.youtube.com/watch?v=FBHhmqBs894
- Page created:
  - DanKoe/2026-06-13 - If You Have Multiple Interests, Start A One-Person Business.md
- Note: Selected the newest unprocessed official channel video. No public caption track was available; the note is marked `confidence: low` and grounded in first-party title, description, duration, and chapters.

## [2026-06-09] ingest | Dan Koe May 23 writing app video
- Sources:
  - https://letters.thedankoe.com/p/i-built-the-writing-app-ive-always
  - https://letters.thedankoe.com/archive
  - https://eden.so
- Pages created:
  - DanKoe/2026-05-23 - I built the writing app I've always wanted.md
- Note: Chose the newest unprocessed Dan Koe video verifiable from public indexed sources. The official video post was accessible, but the transcript body was not, so the note is explicitly marked `confidence: low` and based on metadata plus product framing.

## [2026-05-31] update | Dan Koe 信息图视觉风格升级

- Pages created:
  - DanKoe/assets/dankoe-10-videos-learning-map.svg
- Pages updated:
  - DanKoe/2026-05-31 - Dan Koe 10 videos learning map.md
  - DanKoe/_template-dankoe-video-note.md
  - DanKoe/README.md
- Note: 将信息图标准从简单 Mermaid 流程图升级为参考图风格的中文手绘视觉笔记 SVG；Mermaid 保留为草图。

## [2026-05-31] ingest | Dan Koe 10 个视频批量学习

- Source: https://www.youtube.com/@DanKoeTalks
- Pages created:
  - DanKoe/2026-05-31 - Dan Koe 10 videos learning map.md
  - DanKoe/2026-05-22 - After 100M views this is the system I wish I had.md
  - DanKoe/2026-05-19 - Competition is irrelevant.md
  - DanKoe/2026-05-14 - How To Grow An Audience If You Have 0 Followers.md
  - DanKoe/2026-05-02 - How To Completely Reinvent Yourself In 6-12 Months.md
  - DanKoe/2026-04-11 - It does not matter how long it takes.md
  - DanKoe/2026-04-05 - Start Writing Essays Even If You Hate Writing.md
  - DanKoe/2026-03-28 - If You Lost Your Creative Genius.md
  - DanKoe/2026-03-25 - Just Figure It Out.md
  - DanKoe/2026-03-15 - Build A One-Person Business Faster With AI.md
  - DanKoe/2026-03-12 - You Need To Know What You Want.md
- Note: YouTube 字幕抓取返回 disabled；本批次基于公开视频 RSS、标题、简介和章节整理，Shorts 仅基于标题，已在各页标注 confidence。

## [2026-05-31] create | Dan Koe 视频学习库

- Pages created:
  - DanKoe/README.md
  - DanKoe/_template-dankoe-video-note.md
- Note: DanKoe 作为独立视频学习区，不接管 Hermes 的 concepts、Synthesis、audit 主流程。

## [2026-05-31] create | Codex-Hermes 协作边界

- Pages created:
  - concepts/codex-hermes-collaboration.md
  - Notes/video-note-template.md
- Pages updated:
  - index.md
- Note: 采用低侵入配置；不安装插件、不创建后台任务、不修改 Hermes 同步与 audit 主流程。

## [2026-05-31] ingest | Obsidian + AI 视频学习笔记

- Source: https://www.bilibili.com/video/BV1KbdAB4EYA/
- Companion article: https://mingnify.com/zh/blog/p/obsidian-ai-integration-guide/
- Page created:
  - Notes/obsidian-ai-integration-video.md
- Note: 基于公开视频信息、视频简介和作者配套文章整理；未取得完整字幕逐字稿。

> 所有 wiki 操作的时序记录。只追加，不编辑。
> 格式：`## [YYYY-MM-DD] action | subject`
> Actions: ingest, update, query, lint, create, archive, delete
> 本文件超过 500 条时轮换：重命名为 `log-YYYY.md`，新建空白文件。

## [2026-05-13] create | Wiki initialized
- Domain: AI研究 / 一人公司 / 个人成长
- Structure created with SCHEMA.md, index.md, log.md

## [2026-05-31] ingest | 每日复盘入库
- 复盘原文: audit/new/daily-review-2026-05-31.md
- 短视频选题: entities/video-topics/daily-review-2026-05-31.md
- 金句卡片: Knowledge-Cards/daily-review-2026-05-31-insight.md
- Directories: raw/{articles,papers,transcripts,assets}, entities/, concepts/, comparisons/, queries/
- Vault path: ~/wiki

## [2026-05-14] ingest | 视频号规则和算法研究

- Sources: wechat-channels skill (skill file), Bing search, channels.weixin.qq.com
- Pages created:
  - entities/video-account-rules.md
  - concepts/video-algorithm.md
- Note: 官方完整运营规范需登录 channels.weixin.qq.com 才能查看，本页基于公开信息和实践经验整理

## [2026-05-13] ingest | Karpathy LLM Wiki gist
- Source: raw/papers/karpathy-llm-wiki-2026.md (https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- Pages created:
  - entities/andrej-karpathy.md
  - entities/rag.md
  - entities/hermes-agent.md
  - concepts/llm-wiki-pattern.md
  - comparisons/rag-vs-llm-wiki.md
- Pages updated:
  - SCHEMA.md (tag taxonomy adapted to 3 domains)
  - index.md (all 7 pages registered)
  - log.md (this entry)
测试双向同步

## [2026-05-25] ingest | 通勤教训复盘

- Source: 用户口述（飞书）
- Pages created:
  - audit/new/daily-review-2026-05-25.md（复盘原文）
  - Knowledge-Cards/人生一定要规划好.md（金句卡片）
  - entities/video-topics.md（短视频选题：68公里通勤的教训）
- Pages updated:
  - index.md（新增 video-topics + 人生一定要规划好）
- Topics extracted: 1（68公里通勤的教训）
- Cards extracted: 1（金句：不复盘不规划最终一场空）

## [2026-06-01] ingest | 每日复盘入库
- 复盘原文: audit/new/daily-review-2026-06-01.md
- 短视频选题: entities/video-topics/daily-review-2026-06-01.md
- 金句卡片: Knowledge-Cards/daily-review-2026-06-01-insight.md
## [2026-06-13] DanKoe | processed "Growing on social media is easy, actually"

- Created: `DanKoe/2026-05-07 - Growing on social media is easy, actually.md`
- Sources: official future/proof post, archive metadata, and channel page
- Confidence: medium; direct YouTube watch URL/transcript not publicly recoverable during run

## [2026-06-21] DanKoe | processed "If You Have Multiple Interests, Start A One-Person Business"

- Created: `DanKoe/2026-06-13 - If You Have Multiple Interests, Start A One-Person Business.md`
- Source: official YouTube RSS metadata, description, and chapter list for `FBHhmqBs894`
- Confidence: low; no public transcript was recoverable during this run

## [2026-06-21] DanKoe | processed "How To Think Like A Strategic Genius (5-Dimensional Thinking)"

- Created: `DanKoe/2026-02-22 - How To Think Like A Strategic Genius.md`
- Source: official YouTube RSS metadata, description, and chapter list for `TY8IVSQnwlk`
- Confidence: low; `yt-dlp` is unavailable and no public transcript was recovered during this run

## [2026-06-23] created | 决策百科（Hermes 视频 ❹ 改造版）
- Source: B站视频《6个改变生活的 Hermes Agent 应用案例》BV1xNEM62EzH + 用户对话改造
- Pages created:
  - decisions/README — 决策百科使用指南
  - decisions/_template — 6 字段决策模板
  - decisions/2026-05-19-选一人公司赛道
  - decisions/2026-05-20-选视频号周盛说作主IP
  - decisions/2026-05-21-选Hermes作为唯一AI主力
  - decisions/2026-05-22-产品方向-帮个人做不确定决策
- Note: 4 个示例决策 confidence: medium（基于 memory 推测，非用户亲述），需用户后续校正。半年后回访节点：2026-11-19/20/21/22。

## [2026-07-17] daily-review | evening-review 入库：做减法 / 多平台陷阱

- 复盘原文: `audit/new/daily-review-2026-07-17.md`
- 短视频选题: `entities/video-topics/daily-review-2026-07-17.md`（1 条）
- 金句卡片: `Knowledge-Cards/daily-review-2026-07-17-insight.md`（5 条金句 + 3 个概念 + 三问筛选法）
- 选题标题候选：① 做内容越做越焦虑？多平台陷阱 ② 经济学家研究农民：你焦虑不是因为不努力 ③ 多开一个平台不是多一条路是少一条路

## [2026-07-05] DanKoe | processed "How To Become So Valuable AI Can Never Replace You"

- Created: `DanKoe/2026-06-28 - How To Become So Valuable AI Can Never Replace You.md`
- Source: official YouTube RSS metadata, description, and chapter list for `K2QvCV1PB1w`
- Confidence: low; `yt-dlp` is unavailable and no public transcript was recovered during this run

## [2026-05-17] create | 8D 工具 Skill

- Source: 汽车制造业 8D（Eight Disciplines）问题解决方法论
  - Ford TOPS 手册（1987）
  - IATF 16949 / VDA / AESC 标准
  - 50+ 张图片资料（8D 起源、D0-D8 八步、5W2H、5WHY、冰山模型、Cpk）
- Pages created:
  - concepts/8d-toolkit.md（12KB 主文档：8D 八步+5W2H+5WHY+冰山+8 检查点+5 红灯边界）
- Skill installed at: ~/.hermes/skills/8d-toolkit/
- Skill version: 2.0.0
- Use case: 解决生活/自媒体/赚钱/工作场景的复杂问题
- 达尔文评分：100/100
- Tags: methodology, problem-solving, system-thinking, quality, 8D
- Trigger words: 8D、8D工具、问题解决、用8D、/8d

## [2026-05-17] batch | 7 个 Skill 文档批量入库

- 7 个 Skill 的 SKILL.md 已复制到知识库 concepts/：
  - cognitive-ghost-wall.md（10KB）
  - real-story-refiner.md（16KB，含 v3 合并说明）
  - knowledge-money-pipeline.md（10KB）
  - huashu-flywheel.md（17KB）
  - action-diagnosis.md（14KB）
  - topical-reading-ai.md（9KB）
  - comment-topic-mining.md（7KB）
- index.md Concepts 板块更新：完整列出 8 个 Skill
- 所有 Skill 均已 100/100 分通过达尔文评估
- 触发：用户确认需要把 8 个 Skill 全部入库

## [2026-07-20] sync | Skill 自动入库：8d-toolkit

- Source: ~/.hermes/skills/8d-toolkit/SKILL.md
- Target: concepts/8d-toolkit.md
- Size: 12364 bytes
- Method: sync-skill-to-wiki.sh 自动同步
- Skill version: 2.0.0

## [2026-07-21] sync | book-extract Skill 文档入库

- Source: ~/.hermes/skills/book-extract/SKILL.md
- Target: concepts/book-extract.md
- Size: 9388 bytes
- Skill version: 2.0.0
- Method: 优化+分享版+入库
- Notes: book-extract Skill 已从 v1 优化到 v2（评分 68.0→100 分），新增 5 段输出模板/拍摄块模板/案例库/内化指南
- 分享版: /tmp/book-extract-share.md（7 个文件 + 安装说明）

## [2026-07-21] merge | book-extract v3 合并"拆书博主"模式

- Source: ~/.hermes/skills/book-extract/SKILL.md
- Target: concepts/book-extract.md
- Skill version: 2.0.0 → 3.0.0
- 合并策略: 经评估，"拆书博主"与 book-extract 重叠 ~70%，合并到 v3 作为 Step 2 双模式
- 触发词分流: /拆书 → 通用版，/拆书博主 → 博主版
- 博主版独有: 💊 解决方案 + 📖 关键原文
- 评分: 100/100
- 新增: templates/shoot-block-blogger.md（博主版拍摄块模板）

## [2026-07-21] sync | linggan-alchemy Skill 文档入库

- Source: ~/.hermes/skills/linggan-alchemy/SKILL.md
- Target: concepts/linggan-alchemy.md
- Size: 12294 bytes
- Skill version: 2.0.0
- 评分: 100/100
- Notes: 灵感炼金炉 Skill v2 优化版（7 刃快速切割+快速档输出）
- 关系: 与 oral-alchemy 是上下游关系（灵感炼金炉=提炼洞见，oral-alchemy=写逐字稿）
- 分享版: /tmp/linggan-alchemy-share.md（6 个文件 + 安装说明）

## [2026-07-21] sync | knowledge-card-forge Skill v4 文档入库

- Source: ~/.hermes/skills/knowledge-card-forge/SKILL.md
- Target: concepts/knowledge-card-forge.md
- Size: 10042 bytes
- Skill version: 3.0.0 → 4.0.0
- 评分: 100/100
- 分享版: /tmp/knowledge-card-forge-share.md（5 个文件 + 安装说明）

## [2026-07-21] sync | oral-alchemy Skill v4 文档入库

- Source: ~/.hermes/skills/oral-alchemy/SKILL.md
- Target: concepts/oral-alchemy.md
- Size: 10988 bytes
- Skill version: 3.0.0 → 4.0.0
- 评分: 100/100
- 分享版: /tmp/oral-alchemy-share.md（6 个文件 + 安装说明）

## [2026-07-21] sync | sankuaifa Skill v4 文档入库

- Source: ~/.hermes/skills/sankuaifa/SKILL.md
- Target: concepts/sankuaifa.md
- Skill version: 4.0.0
- 评分: 100/100
- 分享版: /tmp/sankuaifa-share.md（6 个文件 + 安装说明）

## [2026-07-21] sync | knowledge-card-design Skill v5.2 文档入库

- Source: ~/.hermes/skills/creative/knowledge-card-design/SKILL.md
- Target: concepts/knowledge-card-design.md
- Skill version: 5.1.0 → 5.2.0
- 评分: 100/100
- 状态: 已有 7 个 v5.1 文件，新增 4 个 v5.2 文件（four-laws/standard-card/case-examples/quick-reference）
- 分享版: /tmp/knowledge-card-design-share.md（增量补丁版）

## [2026-07-21] sync | para-collide Skill v2 文档入库

- Source: ~/.hermes/skills/para-collide/SKILL.md
- Target: concepts/para-collide.md
- Skill version: 2.0.0
- 评分: 100/100
- 分享版: /tmp/para-collide-share.md（7 个文件 + 安装说明）

## [2026-07-21] create | 知识创建框架 Skill 映射文档

- Path: concepts/knowledge-creation-framework.md
- Type: 元文档（不是新 Skill）
- 用途: QClaw 框架映射到 Hermes 已有 Skill，避免重复安装
- 关系: 引用 15 个 100 分 Skill（linggan-alchemy, kuangcai-mining, oral-alchemy, para-collide 等）

## [2026-07-21] sync | knowledge-creation-framework Skill v1.0 文档入库

- Source: ~/.hermes/skills/knowledge-creation-framework/SKILL.md
- Target: concepts/knowledge-creation-framework.md
- Skill version: 1.0.0
- 评分: 100/100
- 类型: 框架 Skill（meta Skill，调用其他 Skill）
- 关联: 20 个现有 Skill 全部 100 分
- 分享版: /tmp/knowledge-creation-framework-share.md（8 文件 + 安装说明）

## [2026-07-21] sync | kuangcai Skill v4.0 文档入库

- Source: ~/.hermes/skills/kuangcai/SKILL.md
- Target: concepts/kuangcai.md
- Skill version: 3.0.0 → 4.0.0
- 评分: 100/100
- 改动: 新增 frontmatter/6 检查点/失败处理/5 实战案例/速查表（保留 v3.0 全部内容）
- 分享版: /tmp/kuangcai-share.md（8 个文件 + 安装说明）

## [2026-07-21] sync | cognitive-ghost-wall Skill v3.0 文档入库

- Source: ~/.hermes/skills/cognitive-ghost-wall/SKILL.md
- Target: concepts/cognitive-ghost-wall.md
- Skill version: 2.0.0 → 3.0.0
- 评分: 100/100
- 改动: 新增 frontmatter/6 检查点/失败处理/8 实战案例/速查表（保留 v2.0 全部内容）
- 分享版: /tmp/cognitive-ghost-wall-share.md

## [2026-07-21] sync | real-story-refiner Skill v3.1 文档入库

- Source: ~/.hermes/skills/real-story-refiner/SKILL.md
- Target: concepts/real-story-refiner.md
- Skill version: 3.0.0 → 3.1.0
- 评分: 100/100 (v3: 90.4)
- 改动: 末尾追加 5 检查点 + 6 失败处理 + 引用 8 个实战补充案例
- 分享版: /tmp/real-story-refiner-share.md

## [2026-07-21] sync | action-diagnosis Skill v3.0 文档入库

- Source: ~/.hermes/skills/action-diagnosis/SKILL.md
- Target: concepts/action-diagnosis.md
- Skill version: 2.0.0 → 3.0.0
- 评分: 100/100 (v2: 79.4)
- 改动: 末尾追加 8 检查点 + 8 失败处理 + 引用 8 实战补充案例
- 分享版: /tmp/action-diagnosis-share.md

## [2026-07-21] sync | huashu-flywheel Skill v3.0 文档入库

- Source: ~/.hermes/skills/huashu-flywheel/SKILL.md
- Target: concepts/huashu-flywheel.md
- Skill version: 2.0.0 → 3.0.0
- 评分: 100/100 (v2: 84.2)
- 改动: 末尾追加 7 检查点 + 6 失败处理 + 5 实战补充案例
- 分享版: /tmp/huashu-flywheel-share.md

## [2026-07-21] sync | knowledge-money-pipeline Skill v3.0 文档入库

- Source: ~/.hermes/skills/knowledge-money-pipeline/SKILL.md
- Target: concepts/knowledge-money-pipeline.md
- Skill version: 2.0.0 → 3.0.0
- 评分: 100/100 (v2: 81.0)
- 改动: 末尾追加 7 检查点 + 7 失败处理 + 5 实战补充案例
- 分享版: /tmp/knowledge-money-pipeline-share.md

## [2026-07-21] sync | topical-reading-ai Skill v3.0 文档入库

- Source: ~/.hermes/skills/topical-reading-ai/SKILL.md
- Target: concepts/topic-reading-ai.md（注意：用"topic-reading-ai"避免重复）
- Skill version: 2.0.0 → 3.0.0
- 评分: 100/100 (v2: 81.0)
- 改动: 末尾追加 6 检查点 + 6 失败处理 + 5 实战主题
- 分享版: /tmp/topical-reading-ai-share.md

## [2026-07-23] sync | extract-success-method Skill v3.0 文档入库

- Source: ~/.hermes/skills/extract-success-method/SKILL.md
- Target: concepts/extract-success-method.md
- Skill version: 3.0.0
- 评分: 100/100 (v2: 73.4)
- 改动: 新增 frontmatter/5 检查点/5 失败处理/8 联动/4 实战案例
- 分享版: /tmp/extract-success-method-share.md

## [2026-07-23] sync | knowledge-runnable-check Skill v4.0 文档入库

- Source: ~/.hermes/skills/knowledge-runnable-check/SKILL.md
- Target: concepts/knowledge-runnable-check.md
- Skill version: 4.0.0
- 评分: 100/100 (v3: 65.0)
- 改动: 新增 frontmatter/5 检查点/5 失败处理/6 实战案例/4 等级判定
- 分享版: /tmp/knowledge-runnable-check-share.md

## [2026-07-23] sync | fake-map-self-check Skill v2.0 文档入库

- Source: ~/.hermes/skills/fake-map-self-check/SKILL.md
- Target: concepts/fake-map-self-check.md
- Skill version: 2.0.0
- 评分: 100/100 (v1: 73.8)
- 改动: 新增 frontmatter/6 检查点/6 失败处理/4 实战案例/3 步纠偏+运行脚本
- 分享版: /tmp/fake-map-self-check-share.md

## [2026-08-05] sync | problem-definer Skill v3.0 文档入库

- Source: ~/.hermes/skills/problem-definer/SKILL.md
- Target: concepts/problem-definer.md
- Skill version: 3.0.0
- 评分: 100/100 (v2: 77.1)
- 改动: 新增 frontmatter/5 检查点/5 失败处理/5 实战案例/2 个脚本
- 分享版: /tmp/problem-definer-share.md

## [2026-08-05] sync | oral-practice Skill v3.0 文档入库

- Source: ~/.hermes/skills/oral-practice/SKILL.md
- Target: concepts/oral-practice.md
- Skill version: 3.0.0
- 评分: 100/100 (v1: 75.9)
- 改动: 新增 frontmatter/7 检查点/7 失败处理/5 实战案例/练习记录脚本
- 分享版: /tmp/oral-practice-share.md

## [2026-08-05] sync | short-video-diagnose Skill v2.0 文档入库

- Source: ~/.hermes/skills/short-video-diagnose/SKILL.md
- Target: concepts/short-video-diagnose.md
- Skill version: 2.0.0
- 评分: 100/100 (v1: 68.1)
- 改动: 新增 frontmatter/6 检查点/5 失败处理/5 实战案例/数据自洽脚本
- 分享版: /tmp/short-video-diagnose-share.md

## [2026-08-05] batch | 五步切片法体系 · 5 个 Skill 文档入库

新增 5 个 Skill（"五步切片法"完整流水线）：

| # | Skill | 路径 | 评分 | 替代关系 |
|---|-------|------|------|----------|
| 1 | slice-find | ~/.hermes/skills/slice-find/ | 100 | 独特（找特质）|
| 2 | slice-break | ~/.hermes/skills/slice-break/ | 100 | 部分被 oral-alchemy/book-extract 替代 |
| 3 | slice-edit | ~/.hermes/skills/slice-edit/ | 100 | 高度重叠 oral-alchemy |
| 4 | slice-store | ~/.hermes/skills/slice-store/ | 100 | 部分被 para-collide 替代 |
| 5 | slice-diagnose | ~/.hermes/skills/slice-diagnose/ | 100 | 高度重叠 short-video-diagnose |

**重要说明**：每个 Skill 的 frontmatter 都加了"替代关系"段落，标明哪些功能可被现有 Skill 替代。
- slice-find（找事）：**独特**，没有替代
- slice-break（拆片）：部分替代
- slice-edit（试吃装）：**高度重叠**，建议优先用 oral-alchemy
- slice-store（搭库）：部分替代
- slice-diagnose（诊断）：**高度重叠**，建议优先用 short-video-diagnose

合计入库文档：concepts/slice-{find,break,edit,store,diagnose}.md（5 个）

## [2026-08-05] update | slice-find Skill v2.0 文档更新（完整辅助文件）

新增 5 个辅助文件：
- references/signal-types.md（5 类信号详解）
- references/two-scales.md（真实度×有用度详解）
- assets/quick-reference.md（一页纸速查）
- templates/case-examples.md（3 个实战案例）
- templates/fallback-templates.md（Step 4 兜底模板）
- scripts/signal-classifier.py（信号分类脚本）

脚本功能：自动检测碎片中的 5 类信号 + 识别模糊表述

## [2026-08-05] batch | 五步切片法 4 个 Skill 加辅助文件

| Skill | references | templates | assets | scripts |
|-------|-----------|-----------|--------|---------|
| slice-find | signal-types.md + two-scales.md (10KB) | case-examples.md + fallback-templates.md (10KB) | quick-reference.md | **signal-classifier.py** ✅ |
| slice-break | six-dimensions.md | case-examples.md | quick-reference.md | - |
| slice-edit | three-piece.md | case-examples.md | quick-reference.md | - |
| slice-store | para-directories.md | case-examples.md | quick-reference.md | - |
| slice-diagnose | contradiction-detection.md | case-examples.md | quick-reference.md | - |

脚本 signal-classifier.py 已测试 3 个用例通过。

## [2026-08-05] sync | viral-reverse-engine Skill v2.0 文档入库

- Source: ~/.hermes/skills/viral-reverse-engine/SKILL.md
- Target: concepts/viral-reverse-engine.md
- Skill version: 2.0.0
- 评分: 100/100 (v1: 67.4)
- 改动: 新增 frontmatter/5 检查点/5 失败处理/5 实战案例/4 层详解
- 分享版: /tmp/viral-reverse-engine-share.md

## [2026-08-05] sync | ai-context-config Skill v2.0 文档入库

- Source: ~/.hermes/skills/ai-context-config/SKILL.md
- Target: concepts/ai-context-config.md
- Skill version: 2.0.0
- 评分: 100/100 (v1: 79.0)
- 改动: 新增 frontmatter/5 检查点/5 失败处理/4 实战案例/思考链详解
- 分享版: /tmp/ai-context-config-share.md

## [2026-08-05] sync | reflect Skill v6.0 文档入库

- Source: ~/.hermes/skills/reflect/SKILL.md
- Target: concepts/reflect.md
- Skill version: 5.0 → 6.0.0
- 评分: 100/100 (v5: 88.3)
- 改动: 新增 frontmatter/7 检查点/5 失败处理/3 实战案例/mutation-tracker.py 脚本
- 分享版: /tmp/reflect-share.md

## [2026-08-05] sync | prediction-calibration Skill v2.0 文档入库

- Source: ~/.hermes/skills/prediction-calibration/SKILL.md
- Target: concepts/prediction-calibration.md
- Skill version: 1.0 → 2.0.0
- 评分: 100/100 (v1: 71.8)
- 改动: 新增 frontmatter/6 检查点/5 失败处理/5 实战案例
- 分享版: /tmp/prediction-calibration-share.md
2026-08-06：新增 Dan Koe 视频学习笔记《The Writing System That Saved My Brain》，依据官方标题、说明与章节整理；因未取得公开字幕，已标记为较低可信度。

## [2026-08-09] ingest | 每日复盘：刘院长 6000 成交全过程案例
- 复盘原文: audit/new/daily-review-2026-08-09.md
- 案例卡片: Knowledge-Cards/daily-review-2026-08-09-case-liu.md
- 短视频选题: entities/video-topics/daily-review-2026-08-09.md
- 核心洞察: "不是我在卖，是她看着我在用"——短视频系列铺垫 > 单条爆款，客户买的不是产品，是你这一个月的真实过程
- 5 个延伸选题: 已入库 video-topics

## [2026-08-10] ingest | 新建公众号文章库 + 首篇 T-PDCA 长文
- README: [[公众号文章/README]] — 触发词词典 + 命名规范 + frontmatter 标准，跟 [[小报童文稿/README]] 同款结构
- 首篇: [[公众号文章/2026-08-10-100条视频没流量-公众号]] — 3200 字，T-PDCA 自媒体方法论完整拆解
- index.md 已更新（公众号文章库章节插入小报童库后面作为姐妹库）

## [2026-08-13] sync | ai-review Skill v2.0 文档入库

- Source: ~/.hermes/skills/ai-review/SKILL.md
- Target: concepts/ai-review.md
- Skill version: 1.0 → 2.0.0
- 评分: 100/100 (v1: 68.8)
- 改动: 新增 frontmatter/5 检查点/5 失败处理/5 实战案例/复用率追踪机制
- 分享版: /tmp/ai-review-share.md

## [2026-08-13] sync | extract-success-method Skill v4.0 大重构

- Source: ~/.hermes/skills/extract-success-method/SKILL.md
- Target: concepts/extract-success-method.md
- Skill version: 3.0 → 4.0.0
- 评分: 100/100
- 重大变化:
  - 核心流程 5 步→3 步（找案例/拆条件/封装走）
  - 新增：准入门禁 3 问
  - 新增：反向验证 3 问（反例/反向操作/反驳）
  - 双轨剥离独立成章（正向+反向）
  - 新增变体 3：提取诊断框架
  - 5 铁律 + 5 失效条件
- 辅助文件: SKILL.md/quick-reference.md/case-examples.md（5 案例）已同步

## [2026-08-14] ingest | 每日复盘入库
- 复盘原文: audit/new/daily-review-2026-08-14.md
- 短视频选题: entities/video-topics/daily-review-2026-08-14.md（如何把 Skill 拍出微信视频号口播视频）
- 金句卡片: Knowledge-Cards/daily-review-2026-08-14-insight.md（思维导图是最便宜的交付物）
- 思维导图素材: /home/aaron/.hermes/cache/images/img_6edadef79340.jpg

### [2026-08-14] evening-review 追加 | 胡子哥被动收入三步法+大盛卡点对照
- 来源：胡子哥视频（大盛口述复盘）
- 复盘原文追加: audit/new/daily-review-2026-08-14.md（第二段）
- 短视频选题: entities/video-topics/daily-review-2026-08-14-passive-income.md（被动收入三步法+大盛卡点）
- 金句卡片: Knowledge-Cards/daily-review-2026-08-14-passive-income-insight.md（三句反常识金句+大盛现状对照表）
- 大盛自检卡点：第一步后段（培训体系未搭建）、第二步进行中、第三步待启动

### [2026-11-11] ingest | 新建姜胡说知识库 + 首份线下答疑实录入库
- 新建库: 姜胡说知识库/（README + 线下答疑/ + 线上课程/ + 核心方法论/ + 金句库/）
- 实录归档: 姜胡说知识库/线下答疑/2026-11-11-知识产品化与能力系统化-姜胡说.md
  （源文件：社群线下答疑_知识产品化_能力系统化与个人成长突破-2026年11月11日-来自_得到大脑_.md）
  （87 分钟 / 34 章节 / 18 金句 / 6 条待办 / 4373 行完整保留）
- 提炼方法论卡 7 张: 知识产品化 / 能力系统化 / 免费起步保留退出权 / 新人付费才算产品被确定 / 土壤保护与筛选 / 用时间衡量核心团队 / 简单原则
- 金句库: 姜胡说知识库/金句库/姜胡说金句库.md（18 句，按 6 主题分类）
- 索引同步: index.md 新增「姜胡说知识库」板块
- 建库者: 大盛 + Hermes Agent

### [2026-11-11] ingest | 姜胡说3.0自媒体北京闭门会（3天）实录入库 + 6 张新方法论卡
- 实录归档: 姜胡说知识库/线下答疑/2026-11-06-姜胡说3.0自媒体北京闭门会-姜胡说.md
  （源文件：姜胡说3.0自媒体北京闭门会.md）
  （11/06-11/08 三天 / 27 部分 / 113 知识点 / 3 个现场设计拆解 / 3 个速查表 / 6089 行）
- Day 主题: Day1 不确定性与即兴 · Day2 推动行动与个人系统 · Day3 IPO 打通与故事化表达
- 提炼新方法论卡 6 张: 行为公式B等于MAT / 视频是状态的溢出 / 真诚是地基技法是装修 / 个人系统从用户问题到知识库 / 故事化表达结构 / 情绪表演与三幕剧
- 方法论卡累计: 13 张
- 金句库追加: 25 句（累计 43 句）
- 图片: 2 张引用文件缺失，已建 线下答疑/图片和附件/README.md 说明补图方式
- 索引同步: index.md 姜胡说知识库板块更新（页面数 8 → 15）

### [2026-11-11] fix | 姜胡说3.0闭门会图片补齐（2 张）
- 补图: 姜胡说知识库/线下答疑/图片和附件/624ac400bd63a65407e91207958a43ba.jpg（2275×1279，Day1 大合影）
- 补图: 姜胡说知识库/线下答疑/图片和附件/ab09143b20b50ac2bbff877b16c5b40d.jpg（4096×3072，学员近景合影）
- 实录 frontmatter 更新: images_missing: 2 → images_total: 2 / images_resolved: 2 / images_path: 图片和附件/
- 图片和附件/README.md 更新: 状态改为「已补齐」+ 补图内容说明

### [2026-11-11] skill | 新建 jiang-huashu-lib Skill（姜胡说课程入库流水线）
- Skill 路径: ~/.hermes/skills/knowledge/jiang-huashu-lib/
- 构成: SKILL.md + templates/concept-card-template.md + templates/quote-categories.md + scripts/archive_course.py
- 功能: 上传课程 MD → 自动归档 → 提炼 3-8 张方法论卡 → 金句入库 → 同步 index/log
- 实测: 2 份实录验证（线下答疑 / 3 天闭门会），日期识别 + 章节统计 + 图片补齐 + 索引同步全部通过
- 已入 concepts/jiang-huashu-lib.md

### [2026-11-12] ingest | 姜胡说课程实录入库 AI时代一人公司的构建方法
- 实录归档: 姜胡说知识库/线上课程/2026-10-23-AI时代一人公司的构建方法-姜胡说
  （源文件：AI时代一人公司的构建方法_从小事做起_搭建可自运转的系统-2026年10月23日-来自_得到大脑_.md）
  （线上课程 / 2026-10-23 / 23 章节 / 8 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-12] ingest | AI时代一人公司的构建方法（线上直播）实录入库 + 7 张新方法论卡
- 实录归档: 姜胡说知识库/线上课程/2026-10-23-AI时代一人公司的构建方法-姜胡说.md
  （源文件：AI时代一人公司的构建方法_从小事做起_搭建可自运转的系统-2026年10月23日-来自_得到大脑_.md）
  （线上直播 / 2h15m / 23 章节 / 8 金句 / 2 条待办 / 4939 行）
- 提炼新方法论卡 7 张: 目标与系统的区别 / 做自己的小事 / 自运转系统 / 生态位与互相托举 / 自媒体传播三问 / AI放大与自媒体二次放大 / 跳出内耗
- 方法论卡累计: 20 张
- 金句库追加: 23 句（累计 70 句）
- 图片: 1 张外链（OSS 签名链接，未本地化）
- 索引同步: index.md 姜胡说知识库板块更新（页面数 15 → 22）

### [2026-11-12] ingest | 姜胡说课程实录入库 多位普通人直播创业突破经历
- 实录归档: 姜胡说知识库/线下答疑/2026-10-30-多位普通人直播创业突破经历-姜胡说
  （源文件：多位普通人分享跟随胡子哥团队做直播创业突破自我获得收入的经历-2026年10月30日-来自_得到大脑_.md）
  （线下答疑 / 2026-10-30 / 12 章节 / 6 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-12] ingest | 多位普通人直播创业突破经历（学员访谈）实录入库 + 5 张新方法论卡
- 实录归档: 姜胡说知识库/线下答疑/2026-10-30-多位普通人直播创业突破经历-姜胡说.md
  （源文件：多位普通人分享跟随胡子哥团队做直播创业突破自我获得收入的经历-2026年10月30日-来自_得到大脑_.md）
  （线下活动现场访谈 / 17min / 12 章节 / 6 金句 / 3 位学员：韭黄·智利·依晨 / 676 行）
- 提炼新方法论卡 5 张: 离钱近的事情 / 赚钱是技能 / 三位学员的突破路径 / 氛围改变人 / 换概念不换方向
- 方法论卡累计: 25 张
- 金句库追加: 6 句（累计 73 句）
- 图片: 1 张外链（OSS 签名链接，未本地化）
- 索引同步: index.md 姜胡说知识库板块更新（页面数 22 → 27）

### [2026-11-12] ingest | 姜胡说课程实录入库 AI知识库变现与养老院AI赋能
- 实录归档: 姜胡说知识库/线下答疑/2026-10-06-AI知识库变现与养老院AI赋能-姜胡说
  （源文件：AI知识库变现与养老院AI赋能项目讨论-2026年10月06日-来自_得到大脑_.md）
  （线下答疑 / 2026-10-06 / 13 章节 / 5 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-12] ingest | AI知识库变现与养老院AI赋能（内部工作会议）实录入库 + 6 张新方法论卡
- 实录归档: 姜胡说知识库/线下答疑/2026-10-06-AI知识库变现与养老院AI赋能-姜胡说.md
  （源文件：AI知识库变现与养老院AI赋能项目讨论-2026年10月06日-来自_得到大脑_.md）
  （内部工作会议 / 1h04m / 13 章节 / 5 金句 / 4 条待办 / 3 个成交复盘：刘院长·芳芳·北京女客户）
- 提炼新方法论卡 6 张: 大课转化为什么失败 / 一对一成交原则 / 分阶段成交 / 差异化定价与服务边界 / 从2C转2B / 三方电话会议探店方案
- 方法论卡累计: 31 张
- 金句库追加: 5 句（累计 78 句）
- 图片: 1 张外链（OSS 签名链接，未本地化）
- 索引同步: index.md 姜胡说知识库板块更新（页面数 27 → 33）

### [2026-11-12] ingest | 姜胡说课程实录入库 从零到一打造个人影响力
- 实录归档: 姜胡说知识库/线上课程/2026-09-28-从零到一打造个人影响力-姜胡说
  （源文件：从零到一打造个人影响力的经验分享-2026年09月28日-来自_得到大脑_.md）
  （线上课程 / 2026-09-28 / 12 章节 / 5 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-12] ingest | 从零到一打造个人影响力（社群内部分享）实录入库 + 6 张新方法论卡
- 实录归档: 姜胡说知识库/线上课程/2026-09-28-从零到一打造个人影响力-姜胡说.md
  （源文件：从零到一打造个人影响力的经验分享-2026年09月28日-来自_得到大脑_.md）
  （社群内部分享 / 1h44m / 12 章节 / 5 金句 / 570 行）
- 提炼新方法论卡 6 张: 有价值和被看见 / 线下分享定价阶梯 / 共创式分享 / 二三线信息差红利 / 借力打法 / 自己组织线下活动
- 方法论卡累计: 37 张
- 金句库追加: 5 句（累计 83 句）
- 图片: 1 张外链（OSS 签名链接，未本地化）
- 索引同步: index.md 姜胡说知识库板块更新（页面数 33 → 39）

## 2026-11-12 · 个人影响力专题 PPT 交付

**新建 PPT**（ppt_doctor.py 全部通过）：
- `从零到一打造个人影响力-周盛讲师版.pptx` —— 12 页课程版，主线 = 6 张方法论卡
- `普通人也能做个人影响力-线下分享招募-周盛讲师版.pptx` —— 9 页引流版，含琪萌 8/11-8/15 实战时间线
- `个人影响力-30天行动清单-周盛讲师版.docx` —— 学员可打印（W1-W4 + 今日 3 件事）
- `姜胡说知识库/核心方法论/个人影响力30天行动清单.md` —— 清单 MD 版

**顺手修**：全库画布审计发现 5 个历史文件错位，其中
`方向是试出来的-三块法教练-周盛讲师版(琪萌案例版).pptx`（用户之前报「画面错位」的那个）
画布是 10×5.625 → 已用 `fix_ppt_canvas.py` 改成 13.333×7.5，坐标不动，桌面同步。

**JS 生成器已持久化**：`~/workspace/ppt-src/gen_ppt_infl.js` + `gen_ppt_lead.js`（不再放 /tmp）

### 2026-11-12 修正 · 09-28 实录分类归位

归档时误用 `--kind 线上课程`，经复核原文件元数据（**内容类型：社群分享**、录音时间
**17:03-18:48 白天**、现场感对话含来电插话），实为**线下分享**而非线上直播课。
已移动：`姜胡说知识库/线上课程/` → `姜胡说知识库/线下答疑/`，并同步修正 frontmatter
的 `source` / `summary` 与 index.md 全路径链接。6 张方法论卡用的是短链接
（`[[2026-09-28-...]]`，Obsidian 按文件名跨目录解析），无需改动。

> 教训：`archive_course.py` 自带的 `detect_kind()` 判别逻辑是对的（这份会自动判成
> 「线下答疑」），问题出在**手动传 `--kind` 强制覆盖了自动判别**。以后不确定归类时，
> **不要传 `--kind`**，让它自己判。

### [2026-11-12] ingest | 姜胡说课程实录入库 连麦答疑创业者方向选择
- 实录归档: 姜胡说知识库/线上课程/2026-10-13-连麦答疑创业者方向选择-姜胡说
  （源文件：胡子哥连麦答疑_创业者方向选择_早起社群运营_中老年AI教学规划讨论-2026年10月13日-来自_得到大脑_.md）
  （线上课程 / 2026-10-13 / 14 章节 / 9 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-12] ingest | 连麦答疑：创业者方向选择 / 早起社群运营 / 中老年AI教学规划
- 实录归档: 姜胡说知识库/线上课程/2026-10-13-连麦答疑创业者方向选择-姜胡说.md
  （源文件：胡子哥连麦答疑_..._2026年10月13日-来自_得到大脑_.md）
  （线上课程 / 2026-10-13 / 14 章节 / 9 金句 / 5 待办）
- 提炼方法论卡 5 张: 喜欢擅长与市场需要的交集 · 先找用户再确定投入 · 护城河是能量场不是形式 · SOP先做再调整 · toC优先于toB
- 金句库追加: 9 句（累计 87 句）
- 索引同步: index.md 更新

### [2026-11-13] ingest | 姜胡说课程实录入库 连麦复盘自媒体变现与社群运营
- 实录归档: 姜胡说知识库/线下答疑/2026-11-03-连麦复盘自媒体变现与社群运营-姜胡说
  （源文件：胡子哥连麦复盘_自媒体变现_社群运营与个人成长经验分享-2026年11月03日-来自_得到大脑_.md）
  （线下答疑 / 2026-11-03 / 14 章节 / 10 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-12] ingest | 连麦复盘：自媒体变现、社群运营与个人成长
- 实录归档: 姜胡说知识库/线上课程/2026-11-03-连麦复盘自媒体变现与社群运营-姜胡说.md
  （源文件：胡子哥连麦复盘_..._2026年11月03日-来自_得到大脑_.md）
  （线上课程 / 2026-11-03 / 36min / 14 章节 / 10 金句 / 4 待办）
- 提炼方法论卡 5 张: 以终为始决定号怎么做 · 火候不够就上桌 · 做线下活动而不是建群 · 产品线克制与系统运转 · 把自己抛出去
- 金句库追加: 10 句
- 索引同步: index.md 更新

**同步修复**：`archive_course.py` 的 `detect_kind()` 重写（原逻辑被正文内容词「线下/直播回放」误伤，
连麦类被误判成线下）。新逻辑 = 元数据优先（source 字段 > 内容类型/参与人数 > 标题 > 元数据区强形式词），
并对「线上及现场老伙计若干」这类混合场**线下优先**。已用库里 7 份 + 5 份源文件做 19 项回归测试全通过。

### [2026-11-13] PPT | 踩过的坑比走过的路更值钱（老伙计复盘版）
- 新建 PPT: PPT文档库/踩过的坑比走过的路更值钱-老伙计复盘-周盛讲师版.pptx
  （12 页 / 深色森林绿 / 339 KB）
- 桌面 + PPT文档库 双入库 ✅
- ppt_doctor.py 全部通过：画布 13.333×7.5 / 0 越界 / 无占位符 / L1 脱敏通过
- JS 生成器持久化: ~/workspace/ppt-src/gen_ppt_pit.js
- 素材来源: 姜胡说知识库《2026-11-03 连麦复盘》（老伙计甲完整失败复盘）
- 特点: **全库第一个完整失败样本课件** —— 失败复盘比成功故事更适合教学

### [2026-11-13] PPT | 把自己抛出去（11年执念与3个月破局 · 激励版）
- 新建 PPT: PPT文档库/把自己抛出去-11年执念与3个月破局-周盛讲师版.pptx
  （12 页 / 深色森林绿 / 328 KB）
- 桌面 + PPT文档库 双入库 ✅
- ppt_doctor.py 全部通过：画布 13.333×7.5 / 0 越界 / 无占位符 / L1 脱敏通过
- JS 生成器持久化: ~/workspace/ppt-src/gen_ppt_throw.js
- 素材来源: 姜胡说知识库《2026-11-03 连麦复盘》（老伙计乙完整破执念历程）
- 定位: 与《踩过的坑比走过的路更值钱》配套 —— **痛课 + 解课**，同一场连麦的两个老伙计

### [2026-11-13] 交付 | 破局行动清单（Word 可打印）
- 新建: PPT文档库/破局行动清单-把自己抛出去-周盛讲师版.docx
  （38 KB / 16 段落 / 4 表格 / 12 个勾选位 / 162 处填写下划线）
- 桌面 + PPT文档库 双入库 ✅
- docx_validate.py 通过（ok:true, issues:[]）；28/28 关键内容校验通过
- 同步 Markdown: 姜胡说知识库/核心方法论/破局行动清单.md
- 结构: 第1部分 4格诊断（格1等准备好/格2怕开口/格3等被推/格4怕不完美）
        → 第2部分 抛出去4步（接受/安全容器/找会的人/接受不确定）
        → 第3部分 30天推进表（W1-W4 每周唯一目标）
        → 30天回头看 + 给自己的三句话
- 配套: 痛课《踩过的坑比走过的路更值钱》12页 + 解课《把自己抛出去》12页

### [2026-11-13] ingest | 姜胡说课程实录入库 直播连麦自媒体创业者成长路径
- 实录归档: 姜胡说知识库/线上课程/2026-10-13-直播连麦自媒体创业者成长路径-姜胡说
  （源文件：胡子哥直播连麦_自媒体创业者成长路径与商业问题答疑-2026年10月13日-来自_得到大脑_.md）
  （线上课程 / 2026-10-13 / 13 章节 / 6 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-13] ingest | 直播连麦：自媒体创业者成长路径与商业问题答疑
- 实录归档: 姜胡说知识库/线上课程/2026-10-13-直播连麦自媒体创业者成长路径-姜胡说.md
  （源文件：胡子哥直播连麦_..._2026年10月13日-来自_得到大脑_.md）
  （线上课程 / 2026-10-13 / 91min / 13 章节 / 6 金句 / 3 待办）
- 提炼方法论卡 6 张: 公域做IP私域出结果 · 粉丝多不等于赚钱多 · 做客服是为了沉淀成知识库 · 门槛不要预设从市场反馈总结 · toB业务一家做透 · 最小成本最少动作直奔结果
- 金句库追加: 8 句
- 索引同步: index.md 更新
- 判别说明: 本次**未传 --kind**，由修复后的 detect_kind 自动判定为「线上课程」（元数据区含连麦/直播），判别逻辑生效

### [2026-11-13] ingest | 姜胡说课程实录入库 老伙计连麦自媒体读书营与社群运营
- 实录归档: 姜胡说知识库/线上课程/2026-10-17-老伙计连麦自媒体读书营与社群运营-姜胡说
  （源文件：江湖说老伙计连麦_自媒体_读书营_社群运营进展与问题咨询-2026年10月17日-来自_得到大脑_.md）
  （线上课程 / 2026-10-17 / 21 章节 / 7 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-13] ingest | 老伙计连麦：自媒体、读书营、社群运营进展与问题咨询
- 实录归档: 姜胡说知识库/线上课程/2026-10-17-老伙计连麦自媒体读书营与社群运营-姜胡说.md
  （源文件：江湖说老伙计连麦_..._2026年10月17日-来自_得到大脑_.md）
  （线上课程 / 2026-10-17 / 129min / 21 章节 / 7 金句 / 6 待办 / 6 位连麦老伙计）
- 提炼方法论卡 6 张: 解谜式报名筛选执行力 · 干货内容会被AI淘汰 · 先打好标签不要乱加内容 · 社群要做有温度的长期社群 · 月度闭环加每日每周复盘 · 以自己为第一个用户
- 金句库追加: 9 句
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，由修复后的 detect_kind 自动判定为「线上课程」，判别逻辑持续生效

### [2026-11-13] ingest | 姜胡说课程实录入库 老伙计连麦创业AI落地与自媒体定位
- 实录归档: 姜胡说知识库/线上课程/2026-09-17-老伙计连麦创业AI落地与自媒体定位-姜胡说
  （源文件：江湖说社群老伙计连麦答疑会_创业_AI落地与自媒体定位问题解答-2026年09月17日-来自_得到大脑_.md）
  （线上课程 / 2026-09-17 / 16 章节 / 10 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-13] ingest | 老伙计连麦答疑会：创业、AI落地与自媒体定位问题解答
- 实录归档: 姜胡说知识库/线上课程/2026-09-17-老伙计连麦创业AI落地与自媒体定位-姜胡说.md
  （源文件：江湖说社群老伙计连麦答疑会_..._2026年09月17日-来自_得到大脑_.md）
  （线上课程 / 2026-09-17 / 145min / 16 章节 / 10 金句 / 6 待办 / 6 位连麦老伙计）
- 提炼方法论卡 6 张: 必须有一款收费产品 · 拥抱不确定允许一切发生 · 载体不等于卖点 · 本地信息差降维打击 · AI落地切一小块做深做透 · 把自卑经历转成IP优势
- 金句库追加: 9 句
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线上课程」，判别逻辑持续生效

### [2026-11-13] ingest | 姜胡说课程实录入库 连麦分享自媒体线下活动与AI应用
- 实录归档: 姜胡说知识库/线上课程/2026-10-05-连麦分享自媒体线下活动与AI应用-姜胡说
  （源文件：江湖说社群连麦分享_自媒体_线下活动与AI应用的成长交流-2026年10月05日-来自_得到大脑_.md）
  （线上课程 / 2026-10-05 / 16 章节 / 7 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-13] ingest | 连麦分享：自媒体、线下活动与AI应用的成长交流
- 实录归档: 姜胡说知识库/线上课程/2026-10-05-连麦分享自媒体线下活动与AI应用-姜胡说.md
  （源文件：江湖说社群连麦分享_..._2026年10月05日-来自_得到大脑_.md）
  （线上课程 / 2026-10-05 / 129min / 16 章节 / 7 金句 / 5 待办 / 5 位连麦老伙计）
- 提炼方法论卡 6 张: 先做单次分享自然延伸系列 · 抄内容换钱不如形成资产 · AI只提炼自己输出不保留生成 · 用借维帮企业补齐认知 · 先玩起来不要过早商业化 · 降低行动难度撕开改变的口子
- 金句库追加: 14 句
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线上课程」

### [2026-11-13] ingest | 姜胡说课程实录入库 直播连麦四位创业者卡点咨询
- 实录归档: 姜胡说知识库/线上课程/2026-10-22-直播连麦四位创业者卡点咨询-姜胡说
  （源文件：江湖说直播连麦_四位创业者的创业卡点咨询与指导-2026年10月22日-来自_得到大脑_.md）
  （线上课程 / 2026-10-22 / 13 章节 / 6 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-13] ingest | 直播连麦：四位创业者的创业卡点咨询与指导
- 实录归档: 姜胡说知识库/线上课程/2026-10-22-直播连麦四位创业者卡点咨询-姜胡说.md
  （源文件：江湖说直播连麦_四位创业者的创业卡点咨询与指导_2026年10月22日-来自_得到大脑_.md）
  （线上课程 / 2026-10-22 / 126min / 13 章节 / 6 金句 / 4 待办 / 4 位连麦创业者）
- 提炼方法论卡 6 张: 短周期小demo避免沉没成本 · 只有付费才是真需求 · 从1V1抽离公共场景做服务分层 · 手工产品别卖太便宜 · AI是基础设施用复盘长新内容 · 方向不用急着定先碰撞
- 金句库追加: 16 句
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线上课程」

### [2026-11-13] ingest | 姜胡说课程实录入库 AI创作自媒体从构建到生态位
- 实录归档: 姜胡说知识库/线上课程/2026-09-23-AI创作自媒体从构建到生态位-姜胡说
  （源文件：利用AI创作做自媒体_从构建到生态位的实战分享-2026年09月23日-来自_得到大脑_.md）
  （线上课程 / 2026-09-23 / 11 章节 / 8 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-13] ingest | AI创作做自媒体：从构建到生态位的实战分享
- 实录归档: 姜胡说知识库/线上课程/2026-09-23-AI创作自媒体从构建到生态位-姜胡说.md
  （源文件：利用AI创作做自媒体_从构建到生态位的实战分享_2026年09月23日-来自_得到大脑_.md）
  （线上课程 / 2026-09-23 / 95min / 11 章节 / 8 金句 / **胡子哥本人主讲，非连麦**）
- 提炼方法论卡 6 张: 创造者与消费者的区别是动手习惯 · 小白鼠实验流量是随机糖果 · 同心圆标签拓展 · 生态位是免费分享换来的信任 · 真实表达不是表演技巧 · 不做别人语言的奴隶
- 金句库追加: 17 句
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线上课程」
- 备注: 这是全库**胡子哥本人方法论课**（其余多为连麦答疑），体系性最强，建议优先用于课件

### [2026-11-13] ingest | 姜胡说课程实录入库 眉山线下老伙计分享会直播筹备
- 实录归档: 姜胡说知识库/线上课程/2026-10-29-眉山线下老伙计分享会直播筹备-姜胡说
  （源文件：眉山线下老伙计分享会直播筹备及学员成长经验分享-2026年10月29日-来自_得到大脑_.md）
  （线上课程 / 2026-10-29 / 40min / 13 章节 / 8 金句 / 5 待办）
- 提炼方法论卡 6 张: 执行才是处理的环节 · 低门槛高上限的赛道选择 · 做成小闭环 · 蜕变要掉层皮重新学 · 每月固定分享场机制 · 付费前先跑一次闭环
- 金句库追加: 7 句
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线上课程」
- 备注: 眉山线下每月最后一周老伙计专属分享场，4 位老伙计登台（杨珊珊/佳伟/李皮皮/王鑫）—— **成果图鉴的一手数据来源**

### [2026-11-13] ingest | 姜胡说课程实录入库 普通人的认知进阶与抓住变化中的机会
- 实录归档: 姜胡说知识库/线下答疑/2026-10-12-普通人的认知进阶与抓住变化中的机会-姜胡说
  （源文件：普通人的认知进阶与抓住变化中的机会分享-2026年10月12日-来自_得到大脑_.md）
  （线下答疑 / 2026-10-12 / 55min / 16 章节 / 7 金句）
- 提炼方法论卡 6 张: 认知的四个阶段 · 学会投机但不要成为投机分子 · 校准认知靠犯错 · 触摸才能感知机会 · 独立思考不等别人认可 · 赚小钱不难难在认知行动力
- 金句库追加: 13 句
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线下答疑」（本份为胡子哥单向分享，非连麦）
- 备注: **全库最完整的认知模型课** —— 认知四阶段 + 投机五步（校准→不确定→触摸→行动→独立思考）+ 成本重估。建议作为《普通人的认知进阶》课件主线

### [2026-11-13] ingest | 姜胡说课程实录入库 输入输出抓住机会赚小钱实现成长
- 实录归档: 姜胡说知识库/线上课程/2026-10-12-输入输出抓住机会赚小钱实现成长-姜胡说
  （源文件：普通人如何通过输入输出抓住机会_赚小钱实现成长-2026年10月12日-来自_得到大脑_.md）
  （线上课程 / 2026-10-12 / 14 章节 / 8 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-13] ingest | 普通人如何通过输入输出抓住机会，赚小钱实现成长
- 实录归档: 姜胡说知识库/线上课程/2026-10-12-输入输出抓住机会赚小钱实现成长-姜胡说.md
  （源文件：普通人如何通过输入输出抓住机会_赚小钱实现成长_2026年10月12日-来自_得到大脑_.md）
  （线上课程 / 2026-10-12 / 92min / 14 章节 / 8 金句）
- 提炼方法论卡 6 张: 非对称收益原则 · 不敢拍是因为扮演了别人 · 输出扩张幸运表面积 · 会输入会输出就会赚钱 · 简单模式化才能快速迭代 · 同一内容深挖三条
- 金句库追加: 20 句
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线上课程」
- 备注: **10-12 同日第二场**（17:41-19:14，与『认知进阶』15:50-16:45 同一天两场）；重叠 131 片段但新增方法论信号为主。含胡子哥**完整短视频 SOP**（一部手机/一镜到底/掐头去尾加字幕/固定结构/变量少）+ 迭代法 + 辨识度 + 非对称收益

### [2026-11-13] deliverable | 普通人的创作操作系统（体系课 + 行动清单）
- 课件: `普通人的创作操作系统-周盛讲师版.pptx`（15 页 · 529 KB）
  - 位置: PPT文档库/ + 桌面（双入库）
  - 结构: P1 封面 → P2 痛点 → P3 认知四阶段 → P4 投机五步 → P5 五个坑 → P6 同心圆定位 → P7 内容 SOP → P8 迭代深挖三条 → P9 表达 → P10 变现闭环 → P11 5 个真实起点 → P12 ★证据链(Sunny 5 周前后) → P13 诊断 8 格 → P14 金句墙 → P15 今天做一件事
- 清单: `普通人的创作操作系统-30天行动清单-周盛讲师版.docx`（60 段）+ `姜胡说知识库/核心方法论/普通人的创作操作系统30天行动清单.md`
- 素材来源: 姜胡说 3 场本人主讲实录（09-23 / 10-12×2）+ 5 份老伙计连麦实录（09-17 / 10-05 / 10-17 / 10-22 / 10-29）
- 数字纪律: **全部数字逐句回源 grep 核对**（涨粉2000 / 48万播放 / 255篇13万字 / 60万 / 14单 / 素人榜第一 / 十几万 / 前八家大模型 / 1800次 / 月销一万本）
- 金句纪律: 26 句候选逐句回源，**通过 26/30**，4 句未命中已剔除，**无出处造假**
- 体检: `ppt_doctor.py` 全部通过（版式 + 结构 + 脱敏 + 预览）；预览肉眼复核 5 页，**修掉 P12 徽章压字问题**
- 顺手修: 全库画布审计扫出 4 个历史文件轻微溢出（13.50 vs 13.333），已修 4 处并同步桌面 → **21/21 全部一致**
- JS 生成器: `~/workspace/ppt-src/ops/`（theme.js + part1-3.js + gen.js + action_spec.json，持久可改版）

### [2026-11-14] ingest | 姜胡说课程实录入库 早起AI共创营迭代与创业方向
- 实录归档: 姜胡说知识库/线下答疑/2026-10-05-早起AI共创营迭代与创业方向-姜胡说
  （源文件：线下交流_早起AI共创营迭代与创业方向探讨-2026年10月05日-来自_得到大脑_.md）
  （线下答疑 / 2026-10-05 / 33min / 16 章节 / 5 金句 / 3 待办）
- 提炼方法论卡 6 张: 没有数据的决策只是梦想 · 免费筛种子用户再收费 · 让AI反过来提问 · 四轮迭代法 · 教别人就是自己认知重构 · 能讲出来知识就属于你
- 金句库追加: 16 句（17 句候选逐句 grep 回源，命中才入库；其中 4 句因空格差异二次校正）
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线下答疑」（线下交流，非连麦）
- 备注: 与同日『连麦分享』为**不同场次**（19:46-20:20 vs 另一场），12字+片段仅重叠 85/294 —— **新内容为主**。含社群运营完整方法论：四轮迭代 + 免费三阶段策略 + AI反问 + 认知重构四步

### [2026-11-14] ingest | 姜胡说课程实录入库 直播答疑与普通人赚钱进化路径
- 实录归档: 姜胡说知识库/线下答疑/2026-10-12-直播答疑与普通人赚钱进化路径-姜胡说
  （源文件：直播答疑与普通人赚钱进化路径分享-2026年10月12日-来自_得到大脑_.md）
  （线下答疑 / 2026-10-12 / 36min / 12 章节 / 5 金句）
- 提炼方法论卡 6 张: 有价值才能变现只有流量不能 · 确定的好机会都明码标价 · 赚的钱必须对应价值 · 连续踩中五次风口 · 慢车道思维 · 突破认知后的两种假努力
- 金句库追加: 16 句（17 句候选逐句 grep 回源，命中才入库；1 句为通用词未命中已剔除）
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线下答疑」（直播答疑）
- 备注: **10-12 当天第三场**（16:52-17:28，夹在『认知进阶』与『输入输出』之间）；与前两份 12字+片段重叠 95/192 —— **一半新内容**。含【视频号变现核心逻辑】+【知识星球退费规则：今年加入可随时退】+【不夹带私货原则】+【胡子哥个人经历时间线：1994中专土木→1998土建→北大旁听→五次风口→王兴分享→认识张一鸣】

### [2026-11-14] ingest | 姜胡说课程实录入库 赚钱完整闭环从需求到反馈
- 实录归档: 姜胡说知识库/线下答疑/2026-10-14-赚钱完整闭环从需求到反馈-姜胡说
  （源文件：赚钱的完整闭环_从需求到反馈的商业逻辑分享-2026年10月14日-来自_得到大脑_.md）
  （线下答疑 / 2026-10-14 / 11 章节 / 5 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-13] ingest | 赚钱的完整闭环：从需求到反馈的商业逻辑分享
- 实录归档: 姜胡说知识库/线下答疑/2026-10-14-赚钱完整闭环从需求到反馈-姜胡说.md
  （源文件：赚钱的完整闭环_从需求到反馈的商业逻辑分享_2026年10月14日-来自_得到大脑_.md）
  （线下答疑 / 2026-10-14 / 12min / 11 章节 / 5 金句 / 2 待办）
- 提炼方法论卡 6 张: 赚钱闭环的五个环节 · 走出困境靠解决别人的问题 · 不匹配用户就是气氛组 · 触达是两件事 · 交换才是赚钱的最终指标 · 认知卡点是看不见的大山
- 金句库追加: 21 句（18 句候选逐句 grep 回源，命中才入库；其中 5 句因表述差异二次校正后补入）
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线下答疑」（播客/商业分享）
- 备注: **胡子哥独讲 12 分钟**（参与人数 1 人）；与库里 19 份实录 **12字+片段重叠 0/71 —— 完全独立的新内容**，是**全库最『商业』的一份**。含【赚钱闭环五环节：需求→供给→触达→交换→反馈】【触达两件事：认知触达+物理触达，海飞丝类比】【交换才是最终指标，点赞关注只是辅助指标】【敢定高价=双赢】【钱不干净是重大认知bug】【7 个认知卡点=看不见的大山】【短视频商业定位格局太小】

### [2026-11-13] deliverable | 普通人的商业闭环地图（商业课 + 行动清单）
- 课件: `普通人的商业闭环地图-周盛讲师版.pptx`（12 页 · 430 KB）
  - 位置: PPT文档库/ + 桌面（双入库）
  - 结构: P1 封面 → P2 ★五环节闭环图 → P3 需求+供给 → P4 触达两件事(海飞丝类比) → P5 交换与定价 → P6 ★认知卡点地图 → P7 短视频重新定位 → P8 4 位老伙计成果 → P9 ★★一页纸地图(学员拍照带走) → P10 10 问自检 → P11 金句墙 → P12 今天做一件事
- 清单: `普通人的商业闭环地图-30天行动清单-周盛讲师版.docx`（59 段）+ `姜胡说知识库/核心方法论/普通人的商业闭环地图30天行动清单.md`
- 素材来源: 2026-10-14《赚钱的完整闭环》（胡子哥独讲）+ 2026-10-12《直播答疑与普通人赚钱进化路径》+ 案例（10-29 眉山: 嘉伟/李皮皮/王鑫；10-22: Sunny）
- 数字纪律: 全部数字逐句回源 grep 核对（60万/20万负债/14单/素人榜第一/48万/涨粉2000/40℃罚200/单工单7-20元）
- 金句纪律: 23 句候选逐句回源，**21/23 命中**，2 句未命中已剔除
- **命名核对**: 眉山实录作「佳伟」，10-14/10-30 作「嘉伟」—— 经 10-30 原文「跟嘉伟他们又学习」交叉核对**为同一人**，课件统一用 10-14 原文写法，已在清单脚注说明
- 体检: `ppt_doctor.py` 全部通过；预览肉眼复核 5 页，**修掉 P2 底部卡片文字溢出（加高 1.02→1.28in）**；复验零溢出
- 全库画布审计: **22/22 全部一致**
- JS 生成器: `~/workspace/ppt-src/biz/`（theme.js 复用 ops/theme.js 配色 + part1-3.js + gen.js + action_spec.json）

### [2026-11-13] deliverable | 社群运营 SOP（运营课 + 行动清单）· 三课体系完成
- 课件: `社群运营SOP-周盛讲师版.pptx`（13 页 · 481 KB）
  - 位置: PPT文档库/ + 桌面（双入库）
  - 结构: P1 封面 → P2 ★五步主线 → P3 定位(土壤vs流量池) → P4 拉人(别建群做活动) → P5 筛选(门槛三坑) → P6 迭代(四轮) → P7 变现(三阶段) → P8 定价阶梯+产品线克制+目标vs系统 → P9 4个案例 → P10 ★★一页纸SOP → P11 10问自检 → P12 金句墙 → P13 今天做一件事
- 清单: `社群运营SOP-30天行动清单-周盛讲师版.docx`（72 段）+ `姜胡说知识库/核心方法论/社群运营SOP30天行动清单.md`
- 素材来源: 姜胡子 8 份实录（09-28 / 10-05×2 / 10-13 / 10-17 / 10-23 / 10-29 / 11-03 / 11-11）提炼的 20 张社群方法论卡
- **金句纪律（本轮最重要的一次修正）**: 初稿金句回源仅 6/20 命中 → **逐条抓原文真实写法，修正 27 处** → 最终逐句验证通过。修正要点：
  - 「社群是土壤，不是收费渠道。土壤污染了…」→ 原文是「**不要等靠要，社群是土壤，自己行动才能长出东西**」（11-11）
  - 「最好的方法是做一场特别牛逼的线下活动…」→ 原文是「**最好的方法就是去做一场特别牛逼的线下活动，结束那一天大家一定会自己组个群，然后把你拉进来**」（11-03）
  - 「门槛不是设计出来的，是观察出来的」→ 原文是「**不需要提前预设门槛，放用户进来，通过实际接触总结目标用户的特质，几次之后自然就知道该怎么设置门槛了**」（10-13）
  - 「目标只能让你成功一次，系统才能让…」→ 原文是「**目标只能让你成功一次，构建系统才能让成功不断复现**」（10-23）
- **★ 抓出一处虚构数据**: 初稿写「能连续 21 天坚持早起」作门槛示例 —— **实录中不存在此表述**（原文是「21天迭代21轮知识卡片」，不同的事）。已替换为 10-13 蜗牛真实用过的「**门票+连续100天输出**」双重门槛
- 案例数据: 全部回源（开悟65天/安庆线下 · 佳伟第10期/15名学员 · 大露露10→17→45/35份调研/续费率50% · 亮哥每期30人/一人一故事）
- 体检: `ppt_doctor.py` 全部通过；预览肉眼复核 4 页；**修掉 3 处文字溢出**（P1 讲师行 / P2 底部卡片重排加高 / P8 氛围卡加高）；复验零溢出
- 全库画布审计: **23/23 全部一致**
- JS 生成器: `~/workspace/ppt-src/soc/`（theme.js 复用 ops 配色 + part1-3.js + gen.js + action_spec.json）
- ★ **三课体系完成**：《创作操作系统》(执行层) + 《商业闭环地图》(商业层) + 《社群运营SOP》(组织层)

### [2026-11-14] ingest | 姜胡说课程实录入库 周末连麦成长进展与运营问题
- 实录归档: 姜胡说知识库/线上课程/2026-09-18-周末连麦成长进展与运营问题-姜胡说
  （源文件：自媒体创业者周末连麦交流_成长进展与运营问题解答-2026年09月18日-来自_得到大脑_.md）
  （线上课程 / 2026-09-18 / 11 章节 / 6 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-13] ingest | 自媒体创业者周末连麦交流：成长进展与运营问题解答
- 实录归档: 姜胡说知识库/线上课程/2026-09-18-周末连麦成长进展与运营问题-姜胡说.md
  （源文件：自媒体创业者周末连麦交流_成长进展与运营问题解答_2026年09月18日-来自_得到大脑_.md）
  （线上课程 / 2026-09-18 / 60min / 11 章节 / 6 金句 / 3 待办）
- 提炼方法论卡 6 张: 讲我的事但说的是你们 · 内容拉回策略 · 不能让自己成为系统 · 知识卡片提取管线 · 只做线下活动社群才有粘性 · 小组互持是最低成本的社群
- 金句库追加: 见下方明细（逐句 grep 回源，命中才入库）
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线上课程」（线上社群连麦）
- 备注: 康康 / 佩佩 / 小溪三位老伙计（与 2026-10-17 同一批人，**一个月后的复盘**），12字+片段重叠 345/450 —— 高度重叠但仍有明确增量。**全库唯一出现的三人同期交叉验证**：「做一件小事」在小溪身上有 2 个月空转的实证；「知识干货会被AI淘汰」在康康身上有流量从过万掉到大几千的实证；「线下活动才有粘性」在佩佩身上有江西见面的落地

### [2026-11-14] ingest | 姜胡说课程实录入库 眉山线下分享会学员蜕变经历
- 实录归档: 姜胡说知识库/线下答疑/2026-10-30-眉山线下分享会学员蜕变经历-姜胡说
  （源文件：自媒体社群成员分享跟随导师成长蜕变的创业经历-2026年10月30日-来自_得到大脑_.md）
  （线下答疑 / 2026-10-30 / 29 章节 / 10 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）

### [2026-11-13] ingest | 自媒体社群成员分享：跟随导师成长蜕变的创业经历（眉山）
- 实录归档: 姜胡说知识库/线下答疑/2026-10-30-眉山线下分享会学员蜕变经历-姜胡说.md
  （源文件：自媒体社群成员分享跟随导师成长蜕变的创业经历_2026年10月30日-来自_得到大脑_.md）
  （线下答疑 / 2026-10-30 / 86min / 8人 / 29 章节 / 10 金句 / 6 待办）
- 提炼方法论卡 6 张: 公开构建 · 带人梯队 · 问问题的方式 · 先不要去创新 · 卖货的人跟产品的差距 · 逆着人心修自己顺着人心做生意
- 金句库追加: 见下方明细（逐句 grep 回源，命中才入库）
- 索引同步: index.md 更新
- 判别说明: **未传 --kind**，detect_kind 自动判定为「线下答疑」（线下活动现场 + 线下分享会）
- 查重说明: **同一天已有另一份 10-30**（线下答疑/2026-10-30-多位普通人直播创业突破经历，17min/5人/韭黄智利依晨）—— **内容完全不同，重叠为 0**，本份是眉山线下老伙计分享会（86min/8人/7位学员）
- **库价值标注**: 全库成果最集中的一份 —— 7 位学员完整蜕变路径 + 胡子哥现场点评（社交能力三原则）。硬数据：黄豆10万粉/300人/GMV200万、公开构建后150人学会直播/50人多4位数/15-20人月入5位数、李公子30万学费/365元星球/2000箱苹果、单日10万销冠、内蒙古TOP1预测50W、宝妈赚200个

### [2026-11-14] ingest | 姜胡说课程实录入库 AI智能体训练营学员成果复盘
- 实录归档: 姜胡说知识库/线下答疑/2026-10-22-AI智能体训练营学员成果复盘-姜胡说
  （源文件：AI智能体训练营陪跑学员成果复盘与后续工作安排-2026年10月22日-来自_得到大脑_.md）
  （线下答疑 / 2026-10-22 / 16 章节 / 3 金句）
- 方法论卡 + 金句: 待提炼（见 skill Step ③/④）


- 提炼方法论卡 4 张: 痛点清单是弹药库 · 蒸馏验证迭代三段式 · 结果前置做强钩子 · 黄金四大结构
- 金句库追加: 18 句（逐句 grep 回源，命中才入库）
- 索引同步: index.md 已更新（4 张卡 + 实录链接）
- 判别说明: 未传 --kind，detect_kind 自动判定为「线下答疑」
- 查重说明: 零重叠（12字+片段 263 段全部新增）
- 补漏说明: 本次为**全库覆盖率核查**发现的漏入库文件 —— 工作区 22 份源文件 vs 库里 22 份实录按日期比对，10-22 有 2 份工作区文件但库里仅 1 份
- 格式修复: 本份为全库唯一旧版嵌套标记（`## ✨ 课堂金句`/`## 📝 待办事项`）→ 已统一为顶层 `# ✨ 金句精选`/`# 📋 待办事项`
