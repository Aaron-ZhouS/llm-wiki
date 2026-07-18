---
title: 女娲 & 达尔文 Skill 安装指南
created: 2026-05-17
updated: 2026-05-17
type: concept
tags: [skill, install, nuwa, darwin, guide, 安装指南]
sources: [alchaincyf/nuwa-skill, alchaincyf/darwin-skill]
confidence: high
---

# 女娲 & 达尔文 Skill 安装指南

本文档介绍如何在 Hermes Agent 中安装和使用 **女娲 Skill**（人物 Skill 工厂）和 **达尔文 Skill**（Skill 自动优化器）。

---

## 1. 女娲 Skill 安装

### 方式一：通过 GitHub API 直接下载（推荐，适合 WSL/GitHub 访问受限场景）

**步骤 1：创建 Skill 目录**
```bash
mkdir -p ~/.hermes/skills/nuwa-skill/{references,scripts}
```

**步骤 2：下载核心文件 SKILL.md**

需要 GitHub PAT（Personal Access Token），在 https://github.com/settings/tokens 生成（勾选 `repo` 权限）：
```bash
GITHUB_TOKEN="<YOUR_PAT>"
curl -s --max-time 15 -H "Authorization: token $GITHUB_TOKEN" \
  "https://api.github.com/repos/alchaincyf/nuwa-skill/contents/SKILL.md" \
  | python3 -c "import sys, json, base64; d=json.load(sys.stdin); print(base64.b64decode(d['content']).decode('utf-8'))" \
  > ~/.hermes/skills/nuwa-skill/SKILL.md
```

**步骤 3：下载辅助文件**

同样方法下载 README.md、scripts/、examples/ 等辅助文件：
```bash
# 下载 README
curl -s -H "Authorization: token $GITHUB_TOKEN" \
  "https://api.github.com/repos/alchaincyf/nuwa-skill/contents/README.md" \
  | python3 -c "import sys, json, base64; print(base64.b64decode(json.load(sys.stdin)['content']).decode('utf-8'))" \
  > ~/.hermes/skills/nuwa-skill/README.md

# 下载 scripts 下的所有文件
curl -s -H "Authorization: token $GITHUB_TOKEN" \
  "https://api.github.com/repos/alchaincyf/nuwa-skill/contents/scripts" \
  | python3 -c "
import sys, json, base64, os
items = json.load(sys.stdin)
for item in items:
    if item['type'] == 'file':
        content = base64.b64decode(item['content']).decode('utf-8')
        with open(os.path.join(os.path.expanduser('~/.hermes/skills/nuwa-skill/scripts'), item['name']), 'w') as f:
            f.write(content)
        print('  -> ' + item['name'])
"
```

**步骤 4：验证安装**
```bash
ls ~/.hermes/skills/nuwa-skill/
cat ~/.hermes/skills/nuwa-skill/SKILL.md | head -10
```

### 方式二：通过 git clone（如果 GitHub 访问正常）
```bash
git clone https://github.com/alchaincyf/nuwa-skill.git ~/.hermes/skills/nuwa-skill
```

---

## 2. 达尔文 Skill 安装

### 方式一：通过 GitHub API（推荐）

**步骤 1：创建 Skill 目录**
```bash
mkdir -p ~/.hermes/skills/darwin-skill/{docs,scripts,templates}
```

**步骤 2：下载核心文件**
```bash
GITHUB_TOKEN="<YOUR_PAT>"
curl -s -H "Authorization: token $GITHUB_TOKEN" \
  "https://api.github.com/repos/alchaincyf/darwin-skill/contents/SKILL.md" \
  | python3 -c "import sys, json, base64; print(base64.b64decode(json.load(sys.stdin)['content']).decode('utf-8'))" \
  > ~/.hermes/skills/darwin-skill/SKILL.md
```

**步骤 3：下载辅助文件**（README、scripts、templates 等）

**步骤 4：验证**
```bash
ls ~/.hermes/skills/darwin-skill/
```

### 方式二：通过 git clone
```bash
git clone https://github.com/alchaincyf/darwin-skill.git ~/.hermes/skills/darwin-skill
```

---

## 3. 一键安装脚本（最推荐）

保存以下脚本为 `install-skills.sh`，一键安装两个 Skill：

```bash
#!/bin/bash
# install-skills.sh - 一键安装女娲 + 达尔文

GITHUB_TOKEN="<YOUR_PAT>"  # 替换为你的 GitHub PAT

install_skill() {
    local repo=$1
    local name=$2
    local skill_dir="$HOME/.hermes/skills/$name"

    echo "============================================"
    echo "Installing $name from $repo"
    echo "============================================"
    mkdir -p "$skill_dir"

    # Get all top-level files
    curl -s --max-time 30 -H "Authorization: token $GITHUB_TOKEN" \
        "https://api.github.com/repos/$repo/contents/" | python3 -c "
import sys, json, base64, os
items = json.load(sys.stdin)
for item in items:
    if item['type'] == 'file' and item['name'] != 'package-lock.json':
        content = base64.b64decode(item['content']).decode('utf-8')
        path = os.path.join('$skill_dir', item['name'])
        with open(path, 'w') as f:
            f.write(content)
        print('  -> ' + item['name'])
"

    echo "Done: $skill_dir"
    echo ""
}

install_skill "alchaincyf/nuwa-skill" "nuwa-skill"
install_skill "alchaincyf/darwin-skill" "darwin-skill"

echo "============================================"
echo "Verify installation:"
echo "============================================"
echo "女娲:"
ls ~/.hermes/skills/nuwa-skill/
echo ""
echo "达尔文:"
ls ~/.hermes/skills/darwin-skill/
```

**使用方法：**
```bash
chmod +x install-skills.sh
./install-skills.sh
```

---

## 4. 安装后的验证

### 步骤 1：确认 Skill 已被 Hermes 识别

在 Hermes 中输入：`skills list`

应该能看到：
- `nuwa-skill`: 女娲造人：输入人名/主题...
- `darwin-skill`: Darwin Skill: autonomous skill optimizer...

### 步骤 2：测试触发词

- 输入 `女娲` → 应出现造人相关的回复
- 输入 `达尔文` → 应出现 skill 优化相关的回复

### 步骤 3：实战测试

**女娲测试：**
```
女娲：蒸馏查理·芒格的思维方式
```
→ 应开始调研芒格资料，生成 Skill

**达尔文测试：**
```
达尔文：给我 koubo-cola skill 打分
```
→ 应输出 8 维评分结果

---

## 5. 常见安装问题

### Q1：GitHub API 返回 401？
**原因**：Token 过期或权限不足
**解决**：
1. 重新生成 PAT
2. 确保勾选了 `repo` 权限
3. 检查 token 字符串是否完整

### Q2：下载文件不完整？
**原因**：GitHub API 单次请求限制 1MB
**解决**：重新运行脚本，或者用 `git clone` 方式

### Q3：安装后 Skill 不生效？
**解决**：重启 Hermes 会话，让 Skill 重新加载

### Q4：没有 PAT 怎么办？
**解决**：
1. 打开 https://github.com/settings/tokens
2. 点 `Generate new token (classic)`
3. 勾选 `repo` 权限
4. 生成后复制 token（**只显示一次**）
5. 把 token 替换到脚本中的 `<YOUR_PAT>`

### Q5：脚本中包含敏感信息会泄露吗？
**注意**：
- PAT 等同于密码，不要提交到 GitHub
- PAT 可以随时在 GitHub 后台 revoke
- 建议脚本只放在本地，不上传

---

## 6. 系统要求

| 依赖 | 最低版本 | 用途 |
|------|---------|------|
| Python | 3.8+ | 解码 base64 内容 |
| curl | 任意 | 调用 GitHub API |
| base64 | Python 自带 | 解码 |
| GitHub PAT | repo 权限 | 避免 API 限流 |

---

## 7. 安装完成后自动获得的能力

### 女娲 Skill
- 输入任意人名 → 自动生成可运行的人物思维 Skill
- 输入模糊需求 → 诊断后推荐合适思维模型
- 已有 Skill 迭代 → 更新优化

### 达尔文 Skill
- 8 维评分任意 SKILL.md
- 自动 hill-climbing 优化循环
- git 版本控制（自动回滚退步）
- 生成改进报告 + 成果卡片

---

## 8. 两个 Skill 的依赖关系

- 女娲独立运行，无需依赖
- 达尔文独立运行，无需依赖
- 两者可配合使用（先女娲造，后达尔文优化）
- 实战示例：女娲造芒格 skill → 达尔文优化到 90+ 分 → 实战验证

---

## 9. 相关链接

| 资源 | 链接 |
|------|------|
| 女娲 GitHub | https://github.com/alchaincyf/nuwa-skill |
| 达尔文 GitHub | https://github.com/alchaincyf/darwin-skill |
| GitHub PAT 生成 | https://github.com/settings/tokens |
| 本 Skill 本地路径 | ~/.hermes/skills/nuwa-skill/ 和 darwin-skill/ |
| 飞书文档 | https://feishu.cn/docx/W5gPdM1PBoaZt1xsvnOcKBxPnub |

---

*本指南由 Hermes Agent 整理，最后更新：2026-05-17*