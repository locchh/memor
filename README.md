# hebb

## Related to

**Foundations**

[Donald O. Hebb](https://en.wikipedia.org/wiki/Donald_O._Hebb) - Neuropsychologist behind "neurons that fire together wire together," cell assemblies, and phase sequences — the conceptual root of agent memory.

**Harness Engineering**

[Learn Harness Engineering](https://walkinglabs.github.io/learn-harness-engineering/en/) - Learn Harness Engineering is a course dedicated to the engineering of AI coding agents.

[Harness Engineering là gì?](https://goonnguyen.substack.com/p/harness-engineering-la-gi) - The explanation about Harness Engineering—the emerging practice of building robust environments around AI models to prevent errors and maximize performance

[Harness engineering: leveraging Codex in an agent-first world](https://openai.com/index/harness-engineering/) - OpenAI's article describes a real-world experiment where they built an internal product with 0 lines of manually-written code

**Agent memory frameworks**

[claude-mem](https://github.com/thedotmack/claude-mem) - Persistent memory for Claude Code via lifecycle hooks, SQLite+FTS5, and Chroma; progressive disclosure for ~10× token savings on recall.

[mem0](https://github.com/mem0ai/mem0) - Multi-tier (user/session/agent) memory with hybrid vector + BM25 + entity-linking retrieval and single-pass ADD-only extraction.

[cognee](https://github.com/topoteretes/cognee) - Graph + vector hybrid with ontology grounding and a remember–recall–forget–improve control loop.

[zep](https://github.com/getzep/zep) - Context engineering platform built on Graphiti, a temporal knowledge graph with bi-temporal facts (`valid_at` / `invalid_at`).

[letta](https://github.com/letta-ai/letta) - MemGPT successor: OS-style tiered memory (core/archival/recall) that the agent self-edits via tool calls.

[engram](https://github.com/Gentleman-Programming/engram) - Single Go binary providing local-first, MCP-accessible persistent memory for coding agents (SQLite + FTS5).

**Code-as-knowledge-graph**

[Understand-Anything](https://github.com/Lum1104/Understand-Anything) - Multi-agent pipeline that turns a codebase into an interactive knowledge graph with architecture tours and diff-impact analysis.

[GitNexus](https://github.com/abhigyanpatwari/GitNexus) - Browser-native, Tree-sitter across 14+ languages into LadybugDB; precomputes communities, execution flows, and confidence-scored call edges.

[graphify](https://github.com/safishamsi/graphify) - Python CLI that maps code, docs, and media into a queryable graph with confidence tagging (EXTRACTED/INFERRED/AMBIGUOUS).

**Research**

[arxiv 2603.09022](https://arxiv.org/abs/2603.09022) - MEMO: memory-augmented context optimization for multi-turn multi-agent LLM games; combines a retention bank with tournament-style prompt evolution.

**Claude-native primitives**

[Claude Code memory docs](https://code.claude.com/docs/en/memory) - Official guide to CLAUDE.md scopes, `.claude/rules/`, and auto memory at `~/.claude/projects/<project>/memory/`.

[Contextual Embeddings cookbook](https://platform.claude.com/cookbook/capabilities-contextual-embeddings-guide) - Prepending LLM-generated chunk context before embedding; 35% fewer retrieval failures, paired with BM25 and reranking.
