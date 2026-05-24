---
title: supermemory
created: 2026-04-15
updated: 2026-04-15
type: entity
tags: [agentic-memory, memory-backends]
sources: [raw/witcheer-agent-memory-thread.md]
---

# supermemory

A memory backend designed to move away from static RAG towards evolving state.

## Key Features
* **Connectors**: Google Drive, Gmail, Notion, OneDrive, GitHub.
* **Temporal Awareness**: Automatically deprecates expired/outdated facts (e.g., changes in user location).
* **Scope**: Multi-modal (PDFs, images, videos, code).

## SMFS (Supermemory Filesystem)
- **Concept**: A mountable filesystem for agents combining semantic (RAG-like) search with standard POSIX ops (`ls`, `cat`, `grep`).
- **Functionality**:
    - **Semantic Grep**: Performs vector DB queries into files, returning actionable file paths and line numbers.
    - **Agent Utility**: Enables agents to work with complex data types (PDFs, transcripts, code) directly within existing tools.
- **Resources**: [GitHub](https://github.com/supermemoryai/smfs), [Site](https://smfs.ai)

## Related
[[supermemory-filesystem]], [[dhravya-shah]], [[agentic-filesystem]]
