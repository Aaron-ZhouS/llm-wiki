# Wiki Log

> 所有 wiki 操作的时序记录。只追加，不编辑。
> 格式：`## [YYYY-MM-DD] action | subject`
> Actions: ingest, update, query, lint, create, archive, delete
> 本文件超过 500 条时轮换：重命名为 `log-YYYY.md`，新建空白文件。

## [2026-05-13] create | Wiki initialized
- Domain: AI研究 / 一人公司 / 个人成长
- Structure created with SCHEMA.md, index.md, log.md
- Directories: raw/{articles,papers,transcripts,assets}, entities/, concepts/, comparisons/, queries/
- Vault path: ~/wiki

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
