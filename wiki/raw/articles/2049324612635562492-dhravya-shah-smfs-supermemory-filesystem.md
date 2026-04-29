---
title: Introducing SMFS - Supermemory Filesystem
author: Dhravya Shah (@DhravyaShah)
date: 2026-04-29
source: https://x.com/i/status/2049324612635562492
description: Thread introducing SMFS: mountable filesystem merging RAG semantic search with traditional FS ops for agentic workflows. Replaces grep/ls/cat with semantic-aware versions.
images:
  - https://pbs.twimg.com/media/HHCdhUSasAARz_M?format=jpg&name=small
  - https://pbs.twimg.com/media/HHCnPpMboAEb57Q?format=jpg&name=small
---

# Introducing SMFS - RAG sucks and filesystems are broken. We fixed both with supermemory filesystems.

TLDR: Mountable filesystem (SMFS.ai, https://github.com/supermemoryai/smfs) blending RAG + FS for agents.

## Key Critique
- Agentic search (grep on FS) great for codebases, fails on messy notes/PDFs.
- RAG: severs chunks from context → poor answers.

## SMFS Solution
- **Semantic grep**: Vector query under grep interface, scoped to path.
- Full FS ops (ls, cat) + semantic search.
- Index + tree preserved.

1. Semantic search without tool proliferation.
2. Handles unstructured data (PDFs, transcripts).
3. Agent muscle memory preserved.

Relates to [[agentic-search]], [[rag-limitations]], [[filesystem-for-agents]].

*(Images: Architecture diagrams)*