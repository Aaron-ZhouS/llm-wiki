---
title: 知识库 Agent 协议 v1.0
type: protocol
status: core
created: 2026-07-05
audience: ai-agent
tags: [meta, protocol, agent-handbook, PARA, WSL-D盘]
related: [[我的知识库怎么用]], [[知识周转率闭环系统]], [[11-skill-接力图]]
---

# 知识库 Agent 协议 v1.0

> 给所有接手大盛知识库工作流的 AI agent 读。
> 配套说明（哲学/理由/设计）见 [[我的知识库怎么用]] 和 [[知识周转率闭环系统]]。
> 本文件**只讲协议和约束**，不讲为什么。

---

## 0. 核心规则（违反任何一条 = 错）

```
R01. 写文件只走 WSL 软链入口，绝不直接写 /mnt/d/
R02. 修改任何 skill 之前必读 ~/.hermes/skills/kuangcai/references/pipeline-overview.md
R03. 收到"以前安装过"的 skill → 先 ls ~/.hermes/skills/.archive/ | grep + find ~/.hermes -name 双向查实
R04. 用户发的是"skill 输出"（如口播脚本/4 要素块/拍摄建议）而非 SKILL.md → 识别为下游格式，bridge 进现有 skill，不装
R05. 不可逆操作（删文件/推 git/重置）前必须 stop + 3 选项 + 推荐，让用户拍
R06. 用户的 5 个信号词：单字回复（"1"/"建"/"同意"）= 完全接受 / "听你的" = 拍板权交给你 / "继续" = 接着做 / "够了" = 真的停 / 沉默 = 不知道想要什么，主动 stop 问
```

---

## 1. 物理布局

### 1.1 单一真身：D 盘 Obsidian vault

```
/mnt/d/Obsidian/llm-wiki/   ← 唯一真身
├── .obsidian/                ← Obsidian 客户端配置
├── .git/                     ← D 盘端 git 仓（独立）
├── 00-灵感库/                ← 用户日常看
├── 03-Resources/             ← 工具/SOP/参考
├── Synthesis/                ← 长期责任区（扮演 Areas）
├── 灵感库/                   ← PARA 完整结构
│   ├── 00-灵感库/            ← 5 种子 + 新入盒素材
│   ├── 01-项目/              ← 有截止日
│   ├── 02-领域/              ← 长期领域卡
│   └── 04-归档/
├── Knowledge-Cards/          ← 卡片
├── Articles/                 ← 长文
├── Notes/                    ← 草稿
├── concepts/ entities/ decisions/ comparisons/ raw/  ← Karpathy LLM Wiki 痕迹
├── audit/ DanKoe/ Synthesis/  ← 既有目录不动
└── [原 131 个文件全部保留]
```

### 1.2 WSL 软链入口

```
/home/aaron/wiki/
├── 灵感库  →  /mnt/d/Obsidian/llm-wiki/灵感库   ← 软链（必走这里写）
├── .git/                                          ← WSL 端 git（独立仓，跟 D 盘不同）
├── 任务控制中心.md (68KB)                         ← 活跃
├── log.md / index.md / SCHEMA.md / 4Profile协作指南.md
├── concepts/ entities/ comparisons/ queries/ raw/  ← Karpathy 痕迹
├── projects/ Knowledge-Cards/                      ← 旧文件不动
```

### 1.3 Hermes skill 写入路径（已锁定）

| Skill | 写文件位置 | 路径在哪 | 备注 |
|---|---|---|---|
| `para-collide` 收件 | `灵感库/00-灵感库/` | `~/.hermes/skills/para-collide/SKILL.md:39` | 软链自动落 D 盘 |
| `para-collide` 归档 | `灵感库/02-领域/<方向>/` | `para-collide/SKILL.md:87` | 同上 |
| `knowledge-card-design` | Windows 桌面 + Obsidian Knowledge-Cards/ | `creative/knowledge-card-design/SKILL.md` | 三线输出 |
| 其它 9 个 skill | 不直接写文件 | — | LLM 行为协议 |

---

## 2. PARA 库协议

### 2.1 入盒规则（00-灵感库）

笔记必须满足**至少一条**才进 `00-灵感库/`：

- 🔴 观点我不认同，要说出来
- 🔴 东西我以为懂了，但讲不清
- 🔴 现象让我困惑，没有简单解释
- 🔴 旧认知最近被动摇

**不满足 = 直接删，不进库。**

### 2.2 门禁 4 问（强制，两周内完成）

```
1. 可证伪测试 — 10 秒内能说出反例吗？
2. 穿透力测试 — 能同时解释 A 和 B 两个不相关现象吗？
3. 最强反方测试 — 比用户聪明的人会质疑哪里？
4. 迭代检查 — 之前讲过类似的？这次新在哪？
```

**通过 → 提炼进 skill 流水线 → 输出**
**没通过 → 删掉**

### 2.3 演进协议

- 素材**不删**（留作以后对撞）
- 02-领域 只能放"已铸卡的最终版"，不放"未压缩素材"
- 每篇内容输出末尾加"上期回顾"，形成认知迭代线
- 灵感库保持 ≤ 10 篇待处理

---

## 3. 11 Skill 接力协议

完整图见 `~/.hermes/skills/kuangcai/references/pipeline-overview.md`（**改任何 skill 前必查**）。

| 11 个 skill | 写入文件系统？ | 主要用途 |
|---|---|---|
| `mvp` | ❌ | 卡住时抽最小动作 |
| `book-extract` | ❌ | 拆书 + 拍摄块 |
| `insight-forge` | ❌ | 单主题 7 刃切割 |
| `knowledge-card-forge` | ❌ | 造卡片内容（4 铁律 + L1-L3）|
| `knowledge-card-design` | ✅ 三线 | Kindle 纸书风出图 |
| `oral-alchemy` | ❌ | 3-7 分钟长口播 |
| `sankuaifa` | ❌ | 三块法：理解→连接→落地 |
| `deep-insight` | ❌ | 长文→洞见+证据等级 |
| `para-collide` | ✅ PARA 库 | 跨素材对撞 + 铸卡 + 归档 |
| `kuangcai` | ❌ | 短想法压缩成判断（8→5 规则）|
| `video-script-generator` | ❌ | 30-40 秒视频号短稿 |

**严肃度滑块（轻→重）：** mvp → book-extract → deep-insight → sankuaifa

---

## 4. 操作协议

### 4.1 写文件协议

```bash
# ✅ 正确：走 WSL 软链入口
echo "..." > /home/aaron/wiki/灵感库/00-灵感库/新素材-$(date +%Y%m%d).md

# ❌ 错误：直接写 D 盘（绕过软链 + 破坏 git 跟踪）
echo "..." > /mnt/d/Obsidian/llm-wiki/灵感库/00-灵感库/xxx.md
```

**例外：** 一次性大规模初始化（如重建结构）可直写 D 盘，但写完必须 `ls -la` 验证软链同步。

### 4.2 软链维护协议

```bash
# 检查软链
ls -la /home/aaron/wiki/灵感库
# 期望：灵感库 -> /mnt/d/Obsidian/llm-wiki/灵感库

# 重建软链（删旧的不影响 D 盘数据）
unlink /home/aaron/wiki/灵感库
ln -s /mnt/d/Obsidian/llm-wiki/灵感库 /home/aaron/wiki/灵感库

# 软链写测试
touch /home/aaron/wiki/灵感库/00-灵感库/写测试.md && \
  ls /mnt/d/Obsidian/llm-wiki/灵感库/00-灵感库/写测试.md && \
  rm /home/aaron/wiki/灵感库/00-灵感库/写测试.md
```

### 4.3 触发词词典

| 触发词 | 含义 | 调哪个 skill |
|---|---|---|
| `/MVP` "卡住了" "想做什么但太大了" "动不了" | 想法太大抽最小动作 | `mvp` |
| `/拆书` "拆一下" "把这本书的精华抽出来" | 拆书出知识卡 | `book-extract` |
| `/灵感炼金` "给我个洞见" "换个角度" "更毒舌" "更深" | 7 刃切割 | `insight-forge` |
| `/锻造` `/迭代` `/升级` `/评估` "我学到一条经验" "把这条变卡片" | 造卡片内容 | `knowledge-card-forge` |
| `/口播炼金` `/长口播` "写个 5 分钟口播" "做个 B 站视频脚本" "诊断口播" "打磨口播" | 长口播 | `oral-alchemy` |
| `/三块法` `块一` `块二` `块三` "三块法：[概念]" "理解一下" "我想搞懂 XX" | 三块法 | `sankuaifa` |
| `/深度分析` `/长灵感萃取` `/灵感对撞机` "把这篇拆深一点" "深度分析这段" | 长文分析 | `deep-insight` |
| `/对撞` "碰一下" "我在想 ____" "让灵感打架" "挖矿" "知识库碰撞" | PARA 对撞 | `para-collide` |
| `/挖矿` `/炼洞见` "挖一下" "压一下" "把这个想法压成判断" | 短想法压缩 | `kuangcai` |
| 5 版口播管线 | 视频号短稿 | `video-script-generator` |
| "出图" "出信息图" | 出图 | `knowledge-card-design` / `sn-infographic` |

### 4.4 5 个用户信号词

| 信号 | 含义 | agent 动作 |
|---|---|---|
| 单字回复（"1"/"建"/"同意"/"4"）| 完全接受 | 不展开多选项，直接执行 |
| "听你的" / "你拍" / "你定" | 把判断权交给你 | 列 A/B/C 短选项 + 推荐，他选完就做 |
| "继续" | 接着做 | 按既定流程继续 |
| "够了" / "停" | 真的停 | 收尾报告 + 明确"还差什么" |
| 沉默 5 秒+ | 不知道想要什么 | stop 主动问"你想要 A 还是 B" |

---

## 5. skill 评估协议（重要）

收到新 skill 时按这个流程：

```
1. 识别是 SKILL.md 还是 skill 输出
   - 包含 YAML frontmatter + # 标题 + 规则/结构 → SKILL.md
   - 是口播脚本/4 要素块/拍摄建议 → 是 skill 输出，不是 skill

2. SKILL.md 走"评估四问"：
   a) ls ~/.hermes/skills/<name>/ 2>/dev/null → 已装？
   b) ls ~/.hermes/skills/.archive/ | grep <name> → 归档过？
   c) find ~/.hermes -name "<name>*" → 任何 reference 引用？
   d) grep -r "<关键词>" ~/.hermes/skills/ → 撞名？

3. 决策树：
   - 已装（活跃）→ 不重装，可补触发词/接力表/断链
   - 在 archive → 复活 + 升级（不删 archive）
   - 撞名 → 命名区分 + 接力表串接
   - 是 skill 输出 → bridge 进现有 skill，不装
   - 全新且不重复 → 装
```

---

## 6. 故障协议

### 6.1 软链断

```bash
ls -la /home/aaron/wiki/灵感库
# 期望输出含"-> /mnt/d/Obsidian/llm-wiki/灵感库"
# 没有就重建（4.2 节）
```

### 6.2 D 盘挂载掉

```bash
mount | grep /mnt/d
# 没输出 → sudo mount -t drvfs D: /mnt/d -o metadata,uid=1000,gid=1000
```

### 6.3 D 盘写权限

```bash
touch /mnt/d/Obsidian/llm-wiki/test.md && rm /mnt/d/Obsidian/llm-wiki/test.md
# 失败 → 检查 ls -la /mnt/d/Obsidian/llm-wiki/ | head -5 权限
```

### 6.4 para-collide 收件失败

1. 软链状态（6.1）
2. D 盘写权限（6.3）
3. para-collide/SKILL.md 路径配置：`grep "灵感库" ~/.hermes/skills/para-collide/SKILL.md`
4. 期望 3 处都是 `/mnt/d/Obsidian/llm-wiki/灵感库/`

### 6.5 Obsidian 看不到新文件

1. Obsidian → 设置 → 文件与链接 → 强制刷新
2. 检查 `.obsidian/app.json` 里 `alwaysUpdateLinks: true`

---

## 7. 不可逆操作清单（跑 B 模式）

| 操作 | 风险等级 | 必备动作 |
|---|---|---|
| `rm` 任何文件 | 高 | stop + 3 选项 + 推荐 + 用户拍 |
| `git push` 上游 | 高 | 同上 |
| `git commit` 后 reset | 高 | 同上 |
| `git rebase` | 中 | stop 警告，列出冲突 |
| `hermes skills install` | 中 | 先评估（5 节流程）|
| `hermes curator` 操作 | 中 | stop + 推荐 |
| 编辑 / 写文件 / 查 | 低 | 直接做 |
| 软链重建 | 低 | 直接做（D 盘数据不动）|

**完整规则参考：** `~/.hermes/skills/.../references/release-changelog-workflow.md`

---

## 8. 必备 reference

| 路径 | 用途 |
|---|---|
| `~/.hermes/skills/kuangcai/references/pipeline-overview.md` | 11 skill 全景（改 skill 必查）|
| `~/.hermes/skills/para-collide/SKILL.md` | PARA 库协议源头 |
| `/mnt/d/Obsidian/llm-wiki/Synthesis/知识周转率闭环系统.md` | 顶层哲学 |
| `/mnt/d/Obsidian/llm-wiki/Synthesis/我的知识库怎么用.md` | 用户向使用指南 |
| `/mnt/d/Obsidian/llm-wiki/Synthesis/知识库搭建说明书.md` | 设计原理 + 演进日志 |
| `/mnt/d/Obsidian/llm-wiki/03-Resources/11-skill-接力图.md` | 11 skill 接力图（D 盘版）|
| `/mnt/d/Obsidian/llm-wiki/00-灵感库/index.md` | 入盒规则 + 门禁 4 问 |

---

## 9. 版本

| 版本 | 日期 | 变更 |
|---|---|---|
| 1.0 | 2026-07-05 | 初版，跟 11 skill 收口 + PARA 软链迁移同步发布 |

---

**最后一条铁律：**

> **执行前先确认协议。执行中实时对照。执行后写报告。**
> 不可逆操作前 stop。可逆操作直接做。
> 用户信号词优先于本协议。
