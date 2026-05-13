---
title: Hermès Agent
created: 2026-05-13
updated: 2026-05-13
type: entity
tags: [ai-model, agent, open-source, tool]
sources: [raw/papers/karpathy-llm-wiki-2026.md]
confidence: high
---

# Hermès Agent

## 概述

Hermès Agent 是 Nous Research 开发的开源自主 AI 智能体框架，GitHub 星标已突破 6 万（2026年5月）。具备持久记忆、自动技能创建和多平台通信能力。

## 核心特性

- **持久记忆**：跨会话积累知识和上下文
- **自动技能创建**：根据使用场景自动构建和维护技能
- **多平台支持**：微信、Telegram、Discord、飞书、钉钉等
- **Skill 系统**：内置模块化技能库，可扩展
- **MCP 支持**：Model Context Protocol，扩展工具能力

## 与 LLM Wiki 的关系

Hermès Agent 可作为 LLM Wiki 的 orchestrator：
- 读取来源、写入 wiki 页面、维护交叉引用
- Obsidian 作为前端 IDE 展示结果
- 两者结合实现 AI 全自动知识管理

## 官方内置技能

- `skills/note-taking/obsidian` — Obsidian 读写
- `skills/research/llm-wiki` — LLM Wiki 管理和维护

## 相关概念

- [[llm-wiki-pattern]] — LLM Wiki 核心理念
- [[agent]] — AI 智能体通用概念
- [[obsidian]] — 推荐的知识库前端
