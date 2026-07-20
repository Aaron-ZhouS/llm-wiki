---
title: Skill 自动入库脚本说明
created: 2026-05-17
updated: 2026-05-17
type: concept
tags: [automation, script, skill-management, workflow]
sources: [sync-skill-to-wiki.sh]
confidence: high
---

# Skill 自动入库脚本

## 一句话说明

每次新建/优化 Skill 后，一键同步到 Obsidian 知识库 + GitHub。

---

## 脚本位置

```
/home/aaron/.hermes/scripts/sync-skill-to-wiki.sh
```

## 使用方法

```bash
bash /home/aaron/.hermes/scripts/sync-skill-to-wiki.sh <skill-name>
```

**示例**：

```bash
# 同步 8D 工具 Skill
bash /home/aaron/.hermes/scripts/sync-skill-to-wiki.sh 8d-toolkit

# 同步飞轮 Skill
bash /home/aaron/.hermes/scripts/sync-skill-to-wiki.sh huashu-flywheel
```

---

## 自动执行的 5 步

| Step | 操作 | 输出 |
|------|------|------|
| 1 | 复制 SKILL.md | `~/.hermes/skills/X/SKILL.md` → `concepts/X.md` |
| 2 | 提取 description | 从 frontmatter 读取用于 index.md |
| 3 | 更新 index.md | 在 Concepts 板块追加 `[[X]]` 条目 |
| 4 | 更新 log.md | 记录同步时间+文件大小+版本 |
| 5 | Git commit + push | 自动提交并推送到 GitHub |

---

## 前置条件

- Skill 已安装在 `~/.hermes/skills/<skill-name>/`
- Wiki 仓库在 `/mnt/d/Obsidian/llm-wiki/`
- Git 已配置 remote（GitHub）

## 失败处理

| 失败场景 | 表现 | 解决 |
|---------|------|------|
| 找不到源文件 | `❌ 找不到 ~/.hermes/skills/X/SKILL.md` | 先安装 Skill |
| index.md 找不到 Concepts 板块 | `⚠️ 找不到 Concepts 板块` | 手动检查 index.md |
| Git push 超时 | `⚠️ push 超时` | 下次 cron 会自动同步 |
| 已有同名条目 | `✅ index.md 已包含条目` | 跳过，幂等 |

---

## 完整流程图

```
新建 Skill (~/.hermes/skills/X/)
       ↓
运行 sync-skill-to-wiki.sh X
       ↓
   ┌── 复制 SKILL.md → concepts/X.md
   ├── 提取 description
   ├── 更新 index.md (Concepts 板块)
   ├── 更新 log.md
   └── Git commit + push
       ↓
Obsidian 自动同步（5 分钟内）
       ↓
在 Windows Obsidian 里看到新 Skill 文档
```

---

## 幂等性

脚本可以**重复运行**，已存在的条目会自动跳过：
- index.md 已有 `[[X]]` → 跳过更新
- log.md 追加新条目（不覆盖旧的）
- 文件直接覆盖（最新版本）

---

## 来源

整理自大盛的工作流（Skill 安装 → 知识库同步 → GitHub 协作）。