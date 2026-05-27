---
title: Context Management in Agent Harnesses Comparison
created: 2026-04-27
updated: 2026-05-27
type: comparison
tags: [context-management, agent-harnesses, convergence, comparison]
sources: [raw/articles/2026-04-26-aparna-dhinakaran-context-management-agent-harnesses.md]
author: auto
---

# Context Management in Agent Harnesses Comparison

Active management of context window: high-value state close, paging/indexing, truncation hints.

## Compared Harnesses
| Harness | File Reads | Session Pruning | Subagents |
|---------|------------|-----------------|-----------|
| [[pi-mono]] | 2k/50k cap, head+ nudge | LLM compact tail-keep | Isolated new process |
| [[openclaw]] | Pi + bootstrap caps, tool budgets | Chunk-drop + multi-pass summary | Isolated/fork |
| [[claude-code]] | 256k/25kt gates, dedup | 9-sec prompt summary | Typed/fork |
| [[letta]] | Vector embed + trunc/LRU | Sliding + self-compact | No fork |

Convergent: caps, offset/limit, compaction, isolation.

Arize [[alyx-agent]] independently converges.

---
**See Also**
- [[aparna-dhinakaran]]
- [[harness-engineering]]
- [[agentic-infrastructure]]
