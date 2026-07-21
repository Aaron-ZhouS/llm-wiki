---
name: knowledge-card-design
description: "知识卡片生成 — 先锻造后出图，Kindle纸书风，零依赖。把卡片内容先通过4铁律（原子性/可行动/可证伪/诚实性），再用纯HTML+Tailwind渲染出可发布的小红书/微信/视频号卡片。"
version: 5.2.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [knowledge-card, social-media, design, html, tailwind, xiaohongshu, wechat-video, kindle-style]
    related_skills: [sketch, baoyu-infographic, baoyu-comic, excalidraw, knowledge-card-forge]
  changelog:
    v5.2: "补充 frontmatter/检查点/失败处理/速查表（保留 v5.1 全部内容）"
    v5.1: "Pitfalls 4 个 + Vision 反馈循环（2026-07-05 实战验证）"
    v5.0: "锻造阶段 + 设计阶段完整化"
allowed-tools: [Read, Write, Bash]
skill_type: 卡片设计
when_to_use: "想把零散经验做成可发布的知识卡片；想要 Kindle 纸书风的视觉风格；想做小红书/视频号/微信图卡；先锻造后出图。"
not_when: "只要纯文字不要图（用 knowledge-card-forge）；要做完整方法论（用 linggan-alchemy）；要做长文卡片（用其他图文类工具）。"
experiment_status: active
usage_count: 0
---

# Knowledge Card Design（知识卡片 · Kindle纸书风）

将任意素材/口播稿/经验提炼为高密度知识卡片，Kindle纸书质感，纯HTML+Tailwind CDN，零依赖，浏览器直出。

**核心定位：先锻造后出图。** 内容质量不过关，不进入渲染流程。

---

## 锻造阶段（先于渲染）

### 四铁律（生成卡片必须通过）

| 铁律 | 要求 |
|------|------|
| **原子性** | 一张卡只承载一个独立知识点 |
| **可行动** | 读完能直接指导行为，不是"有道理但不知道怎么用" |
| **可证伪** | 必须能描述出"这张卡失效"的具体场景（红灯不能为空） |
| **诚实性** | 绿灯场景必须来自真实使用经历，不能基于推测扩大范围 |

四铁律不通过 → 输出现有缺失项，不生成卡片。

### 锻造流程

```
用户输入经验/教训
  ↓
提炼核心洞察（追问至一句话说清）
  ↓
构建行动指南（追问至可直接执行）
  ↓
标定绿灯和红灯（必须有真实经历支撑）
  ↓
四铁律检验
  ↓
生成卡片，初始等级 L1
```

### 等级定义

| 等级 | 含义 | 最低要求 |
|------|------|---------|
| **L1** | 初铸 | 通过四铁律，≥1绿灯+1红灯 |
| **L2** | 试炼 | L1 + 在2个真实场景中使用过 |
| **L3** | 淬火 | L2 + 场景跨越≥2个维度差异（对象/环境/利害/频率） |

升级触发：用户主动申请 `/升级 [卡片ID]`
升级验证：用户需举出具体经历，不接受"可能能用"。

### 命令系统

- `/锻造` — 启动从零锻造流程
- `/迭代 [卡片ID]` — 更新已有卡片
- `/升级 [卡片ID]` — 申请升级等级
- `/评估 [卡片ID]` — 体检卡片质量，输出缺失项

### 首次对话引导

若用户首条消息不是具体知识输入，输出：

```
👋 我是你的知识卡片锻造师。
我可以帮你把零散经验变成结构化知识卡片。
最简单的开始方式：
直接告诉我一条你觉得有用的经验、教训或技巧。
例：「我发现写周报时先写成果再写计划，领导反馈好很多。」
我会帮你把它锻造成一张可复用的卡片。
```

---

## 核心原则（锁定不改）

1. **内容决定形式** — 根据内容类型自动适配布局（概念型/对比型/流程型）
2. **先锻造后渲染** — 先过四铁律，再进入内容提取和HTML渲染
3. **不当好好先生** — 卡片有问题直说，禁止"很好，但是" → 改为"问题是"
4. **不替用户思考** — 追问，不脑补。用户的表述必须经用户确认才算
5. **单文件输出** — 只生成 `index.html`，不留中间文件
6. **浏览器直接看** — 纯 HTML + Tailwind CDN，零依赖
7. **固定配色系统** — Kindle纸书暖色体系（见下）

---

## 配色系统（3.0锁定）

```css
外背景:   #e8e0d5
卡片底:   #f5f0eb
Header:  #3c3a37
强调色:   #b8a088
分割线:   #e0d5c8
摘要文字: #3c3a37
正文字:   #7a7062
辅助字:   #8a8072
Footer:   #b0a898
Header标题: #f0ebe4
Header英文: #a09888
Header编号: #8a8072
认知组灰底: #ede6dc
执行组底:   rgba(184,160,136,0.12)
```

---

## 内容提取工作流（胡子哥5板块法）

锻造通过后，用此工作流提炼，再填入 HTML 模板。

### 第一步：门禁检查

- 内容是否有结构化潜力？（有变量关系/因果链 → 通过；纯情绪宣泄 → 只输出警告）
- 若未通过门禁：输出 `⚠️ 价值过低：内容缺乏结构化潜力，建议丢弃或补充具体因果链。`

### 第二步：5板块提炼

对通过的素材，提取以下5个板块：

| 板块 | 内容要求 |
|------|---------|
| **元信息** | 来源 / 核心学科 / 核心变量 → 结果 / 关系类型 |
| **核心界定** | X本质不是A，而是B（一句话本质） |
| **机制** | 默认假设谬误 + 真实因果链 + 关键杠杆点 |
| **边界** | 成立前提 + 系统断裂点（失效条件） |
| **最小动作** | 物理动作 + 具体指令 + 完成信号 |

### 第三步：内容映射到模板

根据内容类型选择布局：

| 内容类型 | 模板布局 | 板块映射 |
|---------|---------|---------|
| 流程/步骤型 | 摘要+机制+行动①-④ | 机制→认知组，行动①-④→执行组 |
| 对比/框架型 | 摘要+机制+分区对比 | 机制→认知组，分区→执行组 |
| 单概念/洞见 | 摘要+展开+行动①-② | 核心界定→摘要，机制→机制区，行动→执行组 |

### 第四步：渲染输出

```
① 锻造检验 → 四铁律
② 分析素材 → 门禁检查
③ 5板块提炼 → 结构化洞见
④ 选择布局（流程型/对比型/概念型）
⑤ 填充 HTML 模板（Tailwind CDN）
⑥ 写出 index.html → Windows桌面
⑦ 执行 html2img.py → 生成 PNG 到桌面
⑧ 写入 Obsidian Markdown（双路径）
```

---

## 卡片结构（锻造输出格式）

```
📇 卡片名称：[简短命名]
🔖 卡片ID：KC-[领域缩写]-[序号]
📊 等级：L[1-3]
💡 核心洞察（一句话）
[用最精炼的语言表达这张卡的知识要点]
📐 行动指南
[具体怎么用、步骤或决策规则]
🟢 绿灯（适用场景）
· [场景1]
· [场景2]
🔴 红灯（不适用场景）
· [场景1]
· [场景2]
🔗 关联卡片
· [关系] KC-XXX：[说明]
```

---

## 布局结构

```
┌────────────────────────────────────┐  ← 外背景 #e8e0d5
│  ┌──────────────────────────────┐  │
│  │  HEADER (#3c3a37, h-128px)  │  │  ← 深炭灰顶栏
│  │  [TAG]  NO.001              │  │
│  │  标题（黑体 30px）           │  │
│  │  SUBTITLE                   │  │
│  └──────────────────────────────┘  │
│  ┌──────────────────────────────┐  │
│  │  BODY (#f5f0eb)             │  │  ← 卡片底色
│  │                              │  │
│  │  ▎ 摘要区（竖线装饰）        │  │  ← 认知组
│  │  ────────────────────────   │  │
│  │  机制区（灰底 #ede6dc）      │  │
│  │                              │  │
│  │  ╭────────────────────────╮  │  │
│  │  │  执行组（半透明暖底）   │  │  │  ← 执行组
│  │  │  ◈ 行动标题            │  │  │
│  │  │  ① xxx — xxx           │  │  │
│  │  │  ② xxx — xxx           │  │  │
│  │  │  ③ xxx — xxx           │  │  │
│  │  │  ④ xxx — xxx           │  │  │
│  │  ╰────────────────────────╯  │  │
│  │                              │  │
│  │  "金句收尾…" (斜体, #8a8072) │  │  ← 金句
│  │                              │  │
│  │  ────────────────────────   │  │
│  │  Footer: BY 作者名          │  │
│  └──────────────────────────────┘  │
└────────────────────────────────────┘
```

---

## 内容适配规则

根据素材类型选择布局：

| 内容特征 | 布局 | 示例 |
|---------|------|------|
| 流程/步骤型 | 摘要 + 机制 + 行动①-④ | 兴趣切入法 |
| 对比/框架型 | 摘要 + 机制 + 分区对比 | 三盏灯法 |
| 单概念/洞见 | 摘要 + 展开 + 行动①-② | 单一金句 |

---

## cardData 规范

```js
cardData = {
  // 元信息
  source:     "来源场景",      // 来源
  subject:    "学科标签",       // 核心学科
  variable:   "X → Y",         // 核心变量关系
  relation:   "线性/阈值/负反馈等", // 关系类型

  // 内容区
  tag:      "COGNITION",       // 英文大写标签
  number:   "001",              // 3位数字编号
  title:    "标题文字",         // ≤8汉字
  subtitle: "SUBTITLE",        // 英文全大写副标题

  // 5板块提炼
  essence:    "X本质不是A，而是B",  // 核心界定（一句话）
  mechanism:  "因为→所以→最终",     // 机制因果链
  fallacy:    "人们通常认为X，实际Y", // 默认假设谬误
  fulcrum:    "杠杆点描述",          // 关键杠杆点
  boundary:   "成立前提 + 断裂点",   // 边界条件

  // 执行组
  actions: [                 // 0-4条
    { step:"①", title:"行动标题", desc:"具体描述" }
  ],

  // 对比型（可选）
  groups: [
    { label:"标签", badge:"徽章", title:"标题", desc:"描述", color:"#b8a088" }
  ],

  // 金句
  quote:  "金句收尾…"
}
```

---

## HTML 模板规范

```html
<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=1080">
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Ma+Shan+Zheng&family=Noto+Sans+SC:wght@400;500;700&display=swap" rel="stylesheet">
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            outer:   '#e8e0d5',
            card:    '#f5f0eb',
            header:  '#3c3a37',
            accent:  '#b8a088',
            divider: '#e0d5c8',
            'cog-bg':'#ede6dc',
            'exec-bg':'rgba(184,160,136,0.12)',
            body:    '#7a7062',
            muted:   '#8a8072',
            footer:  '#b0a898',
          }
        }
      }
    }
  </script>
  <style>
    body { background: #e8e0d5; font-family: 'Noto Sans SC', sans-serif; }
    .msz { font-family: 'Ma Shan Zheng', cursive; }
  </style>
</head>
<body class="flex items-start justify-center p-8" style="background: #e8e0d5; font-family: 'Noto Sans SC', sans-serif;">

  <!-- 卡片外壳（不设 min-height，让内容自然撑开；html2img.py 会按 body.scrollHeight 动态截图） -->
  <div class="w-[1080px] bg-card rounded-xl overflow-hidden shadow-2xl"
       style="background:#f5f0eb;">

    <!-- HEADER -->
    <div class="h-32 px-10 flex flex-col justify-center border-b-2"
         style="background:#3c3a37; border-color:#b8a088;">
      <div class="flex items-center gap-4 mb-2">
        <span class="text-sm tracking-widest uppercase" style="color:#8a8072;">[COGNITION]</span>
        <span class="text-sm" style="color:#8a8072;">NO.001</span>
      </div>
      <h1 class="text-4xl font-black leading-tight" style="color:#f0ebe4; font-family:'Ma Shan Zheng',cursive;">
        标题文字
      </h1>
      <p class="text-lg tracking-widest mt-1" style="color:#a09888;">SUBTITLE</p>
    </div>

    <!-- BODY -->
    <div class="px-10 py-8 space-y-6" style="background:#f5f0eb;">

      <!-- 认知组 -->
      <div class="space-y-4">
        <!-- 摘要区 -->
        <div class="flex gap-4">
          <div class="w-1.5 rounded-full flex-shrink-0" style="background:#b8a088;"></div>
          <p class="text-xl font-bold leading-relaxed flex-1" style="color:#3c3a37;">
            一句话概要摘要摘要
          </p>
        </div>
        <!-- 机制区 -->
        <div class="px-5 py-4 rounded-lg text-base leading-relaxed" style="background:#ede6dc; color:#7a7062;">
          机制解释：这里是机制说明文字，小字灰色底。
        </div>
      </div>

      <!-- 执行组 -->
      <div class="rounded-xl p-6 space-y-4" style="background:rgba(184,160,136,0.12);">
        <div class="text-lg font-bold mb-3" style="color:#3c3a37;">
          ◈ 执行行动
        </div>
        <!-- 行动项 -->
        <div class="space-y-3">
          <div class="flex items-start gap-3">
            <span class="text-xl font-black flex-shrink-0 w-8" style="color:#b8a088;">①</span>
            <div>
              <span class="font-bold" style="color:#3c3a37;">行动标题</span>
              <span class="ml-2" style="color:#7a7062;">— 具体描述</span>
            </div>
          </div>
          <!-- ②③④ 同结构 -->
        </div>
      </div>

      <!-- 金句 -->
      <blockquote class="text-center italic text-xl leading-relaxed py-4"
                  style="color:#8a8072;">
        "金句收尾内容，斜体居中"
      </blockquote>

    </div>

    <!-- FOOTER -->
    <div class="px-10 py-4 text-center text-sm border-t"
         style="color:#b0a898; border-color:#e0d5c8;">
      BY 周盛说
    </div>

  </div>

</body>
</html>
```

---

## 三线输出（必须全部完成）

### 输出①：HTML → Windows桌面

```bash
cp /tmp/card.html /mnt/c/Users/Aaron/Desktop/<标题>.html
```

### 输出②：PNG → Windows桌面（自动化）

```bash
/home/aaron/.hermes/hermes-agent/venv/bin/python3 \
  /home/aaron/.hermes/skills/creative/knowledge-card-design/scripts/html2img.py \
  "/mnt/c/Users/Aaron/Desktop/<标题>.html" \
  "/mnt/c/Users/Aaron/Desktop/<标题>.png"
```

### 输出③：Markdown → Obsidian（双路径）

```bash
# Obsidian Git同步目录
/home/aaron/wiki/Knowledge-Cards/<标题>.md
# Obsidian 主库
/home/aaron/wiki/Knowledge-Cards/<标题>.md
```

Markdown格式：
```md
---
来源: 微信/飞书
创建时间: 2026-XX-XX
类型: 知识卡片
标签: [COGNITION, 一人公司]
等级: L1
相关概念: [[相关概念A]], [[相关概念B]]
---

# 标题

> 一句话概要

**机制**：机制解释...

**行动**：
1. 行动标题 — 描述
2. ...

> "金句..."

**绿灯**：场景1、场景2
**红灯**：场景1
```

---

## 禁区（永远不碰）

- ❌ 不改配色系统（已锁定在3.0）
- ❌ 不改布局层级结构
- ❌ 不生成中间文件
- ❌ 不塞入其他框架格式
- ❌ 不改变输出三线（HTML/PNG/Obsidian）
- ❌ 不跳过四铁律检验直接渲染
- ❌ 不替用户脑补经历（绿灯/红灯必须用户确认）

---

## 出图提示

💡 需要把这个知识卡片生成高密度信息图风格？回复「出图」，我来帮你用 baoyu-infographic 跑另一个版本。

---

## 常见问题

| 问题 | 原因 | 解决 |
|------|------|------|
| **卡片头重脚轻（内容 35% + 空白 60%）** | ① HTML 模板的 `min-h-screen` 撑出 viewport 高度（默认 1920px），② `min-height: 1400px` 强制卡片外壳固定高度 | ① body 改 `items-start justify-center p-8`（去掉 `min-h-screen`），② 卡片外壳**不要**设 `min-height`，让内容自然撑开，③ html2img.py 用 `document.body.scrollHeight` 动态测高度后再截（已内置） |
| Tailwind CDN失效 | 网络问题 | 降级为纯内联样式（备用方案在 templates/kindle-fallback.html） |
| 字体发虚 | 浏览器渲染差异 | `font-smooth: antialiased` + html2img.py 已内置 `wait_for_load_state("networkidle")` + `document.fonts.ready` + 0.5s 等待 |
| 行动项超过4条 | 内容过长 | 合并或删减，4条封顶 |
| 四铁律不通过 | 内容缺乏结构化潜力或边界不清 | 输出缺失项，不生成卡片，让用户补充后重试 |
| html2img.py报"executable doesn't exist" | Chromium浏览器未安装 | 背景运行 `python3 -m playwright install chromium`，完成后通知；超时则告知用户手动用浏览器Ctrl+P打印PDF |

---

## Pitfalls（v5.1 新增，2026-07-05 出图实战验证）

### ⚠️ Pitfall 1：HTML 模板的"高度"陷阱

**别在 body 或卡片外壳设任何 min-height / min-h-screen：**
- `min-h-screen` 让 body 撑到 viewport 高度（1920px），下半部分是空白
- `min-height: 1400px` 让卡片外壳固定 1400px，**实际内容只有 470px 时下半部分是空白**
- 这两种都是"内容不到 1000px 但 PNG 出来 1920px，头重脚轻"的根因

**正确做法：**
- body 用 `flex items-start justify-center p-8`，高度由内容决定
- 卡片外壳只设 `background:#f5f0eb`，不设 min-height
- html2img.py 内部用 `document.body.scrollHeight` 测出真实高度，调 viewport 后截图

### ⚠️ Pitfall 2：`document.body.scrollHeight` ≠ `documentElement.scrollHeight`

之前用 `Math.max(body.scrollHeight, documentElement.scrollHeight)` 取最大值，结果取了 documentElement 的 1920px（被 `min-h-screen` 撑大）。

**正确做法：只取 `document.body.scrollHeight`**，因为 `body` 的高度才是真实内容高度，`documentElement` 在有 `min-h-screen` 时会被强制撑到 viewport。

### ⚠️ Pitfall 3：html2img.py 必须等字体加载完成

Tailwind CDN + Google Fonts 是异步加载，截图过早会"字体发虚"或回退到系统默认字体。

**内置修复：** `wait_for_load_state("networkidle")` + `document.fonts.ready` + 0.5s 等待。

### ⚠️ Pitfall 4：Vision 反馈循环（看图→修图→再看）

PNG 出图后**必须用 `vision_analyze` 看一眼**，不要直接交付。常见需修问题：
- 头重脚轻 / 留白过多
- 文字溢出 / 截断
- 配色"出戏"（Kindle 风被现代 UI 元素破坏）
- 中文字体未渲染（回退到方块）

**2 轮循环通常足够**：第 1 轮跑图 + vision 反馈 + 修，第 2 轮验证。

### ⚠️ Pitfall 5：环境变量 `HTML2IMG_HEIGHT`

如果某张卡需要更长的画布（比如 5 个行动项），可以通过环境变量覆盖默认 1920px：

```bash
HTML2IMG_HEIGHT=2400 /home/aaron/.hermes/hermes-agent/venv/bin/python3 \
  /home/aaron/.hermes/skills/creative/knowledge-card-design/scripts/html2img.py \
  input.html output.png
```

**注意：** 实际输出高度仍由 `body.scrollHeight` 决定（如果内容短，会被截短到 470px），这个环境变量是**上限**保护，不是下限。

---

## PNG 出图最佳实践（v5.1 新增）

1. **写 HTML 模板时**：body 用 `flex items-start justify-center p-8`，卡片外壳不设 min-height
2. **跑 html2img.py 前**：`unset http_proxy https_proxy HTTP_PROXY HTTPS_PROXY no_proxy NO_PROXY`（WSL/agent-reach 必走）
3. **跑完后必走**：用 `vision_analyze` 看一眼 PNG 视觉效果
4. **若头重脚轻**：检查 HTML 有没有 `min-h-screen` 或 `min-height` —— 99% 是这俩之一
5. **若字体发虚**：检查 html2img.py 是否等待了 `document.fonts.ready`（v5.1 已内置，老版需手动加）
6. **桌面路径**：`/mnt/c/Users/Aaron/Desktop/KC-<领域>-<序号>-<标题>.png`

---

## 模板文件

- 主模板：`templates/kindle-card.html`（3.0新）
- 备用纯内联版：`templates/kindle-fallback.html`
- PNG生成器：`scripts/html2img.py`
---

## v5.2 新增（本章是补充，原内容不动）

### 核心工作流回顾

```
第 0 步：输入检测（有内容/没内容）
    ├─ 有内容 → 进入
    └─ 没内容 → 引导用户给素材
       ↓
Step 1: 锻造阶段（先过 4 铁律）
    ├─ 4 铁律全过 → 进入 Step 2
    └─ 不通过 → 补完再进
       ↓
Step 2: 5 板块提炼
    ├─ 5 板块齐 → 进入 Step 3
    └─ 缺 → 补完
       ↓
Step 3: 设计渲染（3 线输出）
    ↓
Step 4: 质量验证（4 个 Pitfall 都过）
```

### 检查点设计

| 检查点 | 触发 | 需要确认 |
|--------|------|----------|
| **CP1** | Step 1 后 | 4 铁律全过？（原子性/可行动/可证伪/诚实性）|
| **CP2** | Step 1 后 | 等级定级（L1/L2/L3）符合实际？|
| **CP3** | Step 2 后 | 5 板块都填了？（钩子/痛点/解药/边界/行动）|
| **CP4** | Step 3 后 | 配色符合 Kindle 纸书风？（不用彩色）|
| **CP5** | Step 3 后 | 3 线输出齐？HTML + PNG + Markdown |
| **CP6** | Step 4 后 | 4 Pitfall 都避开了？（高度/scrollHeight/字体加载/Vision 循环）|
| **CP7** | 完成后 | 卡片可以发布？（草稿 → 公开）|

### 失败处理（Fallback）

| 失败场景 | Fallback |
|---------|---------|
| 4 铁律不过 | 输出现有缺失项，不渲染 |
| 5 板块缺 1+ | 回到上一板块补充，不渲染 |
| HTML 渲染失败 | 用 `templates/kindle-fallback.html`（纯内联）|
| PNG 生成失败 | 检查 html2img.py 是否等待字体 + 路径是否正确 |
| 字体发虚 | 升级到 v5.1（已内置 document.fonts.ready）|
| 卡片太长 | 拆成 2 张（L1 卡片本身就只承载 1 个知识点，应该不会太长）|
| 配色不 Kindle | 强制使用配色：内#f5f0eb / 外#e8e0d5 / Header#3c3a37 / 强调#b8a088 |

### 何时用 knowledge-card-design

**用 knowledge-card-design 的信号**：
- 想做一张可发布的知识卡片（图+文）
- 想要 Kindle 纸书风的视觉
- 想发小红书/视频号/微信图卡
- 想把锻造好的 L1 内容视觉化

**不用 knowledge-card-design 的信号**：
- 只要纯文字不要图（用 knowledge-card-forge）
- 要做完整方法论（用 linggan-alchemy）
- 要做长文卡片（用其他图文类工具）
- 只是记录想法（用普通笔记）

### 红灯边界（硬门禁）

- 🚫 没通过 4 铁律就渲染 → 拒绝
- 🚫 等级不实（虚高）→ 拒绝，回到实际证据
- 🚫 用彩色配色（破坏 Kindle 风）→ 拒绝
- 🚫 PNG 输出没等字体加载 → 退回 v5.1
- 🚫 HTML 输出后跳过 Markdown 入库 → 拒绝
- 🚫 输出和锻造内容不一致 → 拒绝

### 4 铁律详解

详见 `references/four-laws.md`

### 标准卡片模板

详见 `templates/standard-card.md`

### 5 个实战案例

详见 `templates/case-examples.md`

---

## 一页纸速查

详见 `assets/quick-reference.md`

---

## 引用与来源

- **原作者**：Hermes Agent + alchaincyf
- **Hermes 适配**：Hermes Agent（v5.2.0）
- **本地路径**：`~/.hermes/skills/creative/knowledge-card-design/`

---

*Skill 优化版本：5.2（基于 v5.1 实战验证补充 frontmatter/检查点/失败处理）*
