---
title: RAG (Retrieval-Augmented Generation)
created: 2026-05-13
updated: 2026-05-13
type: concept
tags: [ai-technique, inference, tool]
sources: [raw/papers/karpathy-llm-wiki-2026.md]
confidence: high
---

# RAG (Retrieval-Augmented Generation)

## 定义

RAG = Retrieval-Augmented Generation（检索增强生成）。将外部文档分块、向量化，查询时通过向量相似度检索相关片段，由 LLM 综合生成答案。

## 工作流程

```
用户查询 → 向量检索 → Top-K 相关文档块 → LLM 生成回答
```

## 局限性

- **无积累**：每次查询都从原始文档重新发现知识
- **无交叉**：文档之间没有建立关系，复杂问题需要拼凑多个片段
- **矛盾静默**：新旧信息冲突时，LLM 倾向于覆盖而非标注
- **重复劳动**：问5个文档中的一个问题，LLM 每次都要重新检索和拼凑

## LLM Wiki 对比

见 [[comparisons/rag-vs-llm-wiki]]。

## 适用场景

- 文档量大但查询简单的场景
- 一次性分析，不需要长期维护
- 实时性要求高（文档经常变化）的场景

## 相关概念

- [[llm-wiki-pattern]] — RAG 的替代方案
- [[agent]] — 可结合 RAG 使用的 AI 智能体
- [[comparisons/rag-vs-llm-wiki]] — 详细对比
