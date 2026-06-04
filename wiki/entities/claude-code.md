---
title: Claude Code
created: 2026-04-27
updated: 2026-06-03
type: entity
tags: [agent-harness, agent-harnesses, claude-code, context-management, anthropic]
sources: [raw/articles/2026-04-26-aparna-dhinakaran-context-management-agent-harnesses.md, raw/twitter/trq212-a-harness-for-every-task-dynamic-workflows-in-claude-code-2026-06-02.md]
author: auto
---

# Claude Code

Anthropic agent harness.

## Context Management
- File reads: 256KB pre-gate, 25k token post-gate, default 2k lines, line trunc 2k chars, dedup stubs.
- Pre-query tool result persist (2KB previews).
- Compaction: 9-section LLM summary prompt, post-compact file re-attach.

## Dynamic Workflows in Claude Code

Claude Code can generate **dynamic workflows** that write a task-specific harness on-the-fly, enabling different subagent configurations and isolation levels for different problem classes.

- Related concepts: [[workflow-automation]], [[agent-harnesses]], [[agentic-infrastructure]]
- 
[[context-management-in-agent-harnesses]]