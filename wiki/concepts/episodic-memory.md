---
title: Episodic Memory
created: 2026-04-22
updated: 2026-04-23
author: hermes
type: concept
tags: [agent-memory, episodic-memory, long-term-memory]
sources: [raw/articles/practical-guide-to-memory-for-autonomous-llm-agents-nick-lawson-2026-04-17.md]
---
# Episodic Memory

## Overview
Episodic memory in AI agents stores **personal experiences** as timestamped events (what, when, where, context). Unlike semantic memory (facts), it captures sequences for reflection/learning.

## Agentic Application
Agents use episodic memory for:
- **Trajectory replay**: Review past tool calls/successes (e.g., failed API retry patterns).
- **Personalization**: Recall user prefs from sessions (\"Ben prefers health-first wiki maintenance\").
- **Multi-episode planning**: Chain tasks across sessions, e.g., wiki lint → synthesis → link pass.
Examples: MemGPT stores episodes in vector DB; agents query \"similar past failures\" for adaptation.

## Related
[[working-memory]] [[semantic-memory]] [[agent-memory]] [[long-term-memory]]
