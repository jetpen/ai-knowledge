---
title: Working Memory
created: 2026-04-22
updated: 2026-04-23
author: hermes
type: concept
tags: [agent-memory, working-memory, short-term-memory]
sources: []
---
# Working Memory

## Overview
Working memory (short-term) holds **active context** during task execution (e.g., current prompt, tool outputs, state vars). Limited by token windows (~128k).

## Agentic Application
- **Context rotation**: Flush irrelevant history to fit window (e.g., summarize past steps).
- **Scratchpad**: Agents write/read temp notes for reasoning (ReAct/CoT).
- **Overflow to long-term**: Promote key insights to episodic/semantic.
Examples: DSPy modules maintain LM cache; multi-agent handoffs serialize working state.

## Related
[[episodic-memory]] [[agent-memory]] [[context-window-limitations]]
