# 11 Skill 接力流水线 · Reference

> 最后更新：2026-07-05
> 范围：内容生产 + 学习协议 + 知识库管理 共 11 个 skill

---

## 全景图（按角色分层）

```
┌─────────────────────────────────────────────────────────────────────┐
│  层 1 · 原料入口（外部素材）                                          │
├─────────────────────────────────────────────────────────────────────┤
│  book-extract  ──→  拆骨架 + 拍摄块（轻，5 段，视频号/快稿）         │
│  deep-insight  ──→  长文→洞见种子（重，证据等级+反常识）            │
│  para-collide  ──→  PARA 库跨素材对撞（多源，2-3 个素材）            │
│  sankuaifa     ──→  三块法：理解→连接→落地（慢工，严）              │
│  mvp           ──→  想法太大时抽最小动作（5 分钟）                  │
│  insight-forge ──→  单主题 7 刃切割（快狠，反本能）                 │
│  kuangcai      ──→  短想法压缩成判断（敌意审查）                    │
└─────────────────────────────────────────────────────────────────────┘
                                  ↓
┌─────────────────────────────────────────────────────────────────────┐
│  层 2 · 内容锻造（生产资产）                                          │
├─────────────────────────────────────────────────────────────────────┤
│  knowledge-card-forge  ──→  造卡片内容（四铁律 + L1-L3 等级）        │
│         ↓                                                            │
│  knowledge-card-design ──→  出图（Kindle 纸书风 472 行，已存在）     │
└─────────────────────────────────────────────────────────────────────┘
                                  ↓
┌─────────────────────────────────────────────────────────────────────┐
│  层 3 · 出口生产（最终交付）                                          │
├─────────────────────────────────────────────────────────────────────┤
│  video-script-generator ──→  30-40 秒视频号短稿（实战 254 行）       │
│  oral-alchemy           ──→  3-7 分钟 B 站/公众号长稿（8 叙事库）    │
└─────────────────────────────────────────────────────────────────────┘
                                  ↓
                          视频号 / B 站 / 公众号 / 朋友圈
```

---

## 横向接力表（按"我要做 X"反查）

| 我想做的事 | 第一站 | 第二站 | 第三站 |
|---|---|---|---|
| 学完一本书，拍视频号 | `book-extract` | `knowledge-card-forge` | `video-script-generator` |
| 读完一篇深度文章，榨干 | `deep-insight` | `kuangcai`（短判断）| `video-script-generator` |
| 把模糊想法变可发布 | `kuangcai` | `knowledge-card-forge` | `knowledge-card-design` |
| 拍 5 分钟 B 站视频 | `deep-insight` | `oral-alchemy` | — |
| 跟 PARA 库里的种子对撞 | `para-collide` | `kuangcai` | `knowledge-card-forge` |
| 学一个概念并落地 | `sankuaifa` | `mvp`（找最小动作）| `kuangcai`（压成判断）|
| 卡住 / 想法太大 | `mvp` | — | — |
| 一句话反常识金句 | `insight-forge` | — | — |
| 卡片要出图 | `knowledge-card-forge` | `knowledge-card-design` | — |

---

## 严肃度滑块（轻→重）

```
轻 ───────────────────────────────────────────────→ 重
mvp    book-extract    deep-insight    sankuaifa
5min   5 段骨架         证据等级         3 块走一遍
                     ↑
                  kuangcai
                  (短想法压缩)
```

---

## 跟 archive 的关系（防重复装）

| Archive 旧版 | 现役新版 | 关系 |
|---|---|---|
| `sankuaifa-coach_20260611` | `sankuaifa` | 已复活 + 补触发词 |
| `kuangcai-mining_20260611` | `kuangcai` | 已复活 + 8 条精简 5 条 + 长文分析拆到 `deep-insight` |
| `creative/kuangcai-cola_20260611` | （已删）| 早前合并 |
| `creative/linggan-alchemy_20260611` | （已删）| 早前合并 |
| `creative/sankuaifa-coach_20260611` | （已删）| = `sankuaifa` |
| `creative/sn-infographic_20260611` | `sn-infographic` | 仍在用 |
| `creative/video-link-reader_20260611` | `video-link-reader` | 仍在用 |
| `social-media/wechat-channels_20260611` | （已删）| 早前合并 |

**铁律：** 收到"已安装过"的 skill 时，先 `ls ~/.hermes/skills/.archive/ | grep 关键词` + `find ~/.hermes -name "关键词"` 双向查实，再决定装/复活/合并/跳过。

---

## 知识库导航（vault 配套文档）

安装 / 路径 / 软链等基础设施问题，参考以下 3 份说明书：

| 文档 | 路径 | 给谁看 |
|---|---|---|
| 我的知识库怎么用 | `Synthesis/我的知识库怎么用.md` | 大盛（30 秒回忆日常用法）|
| 知识库 Agent 协议 | `Synthesis/知识库-Agent-协议.md` | 任何接手的 AI agent（协议 + 触发词 + 故障命令）|
| 知识库搭建说明书 | `Synthesis/知识库搭建说明书.md` | 混合参考（哲学 + 设计 + 演进日志）|
