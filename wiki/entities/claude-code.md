---
title: Claude Code
created: 2026-04-27
updated: 2026-04-27
type: entity
tags: [agent-harness, claude-code, context-management, anthropic]
sources: [raw/articles/2026-04-26-aparna-dhinakaran-context-management-agent-harnesses.md]
author: auto
---

# Claude Code

Anthropic agent harness.

## Context Management
- File reads: 256KB pre-gate, 25k token post-gate, default 2k lines, line trunc 2k chars, dedup stubs.
- Pre-query tool result persist (2KB previews).
- Compaction: 9-section LLM summary prompt, post-compact file re-attach.

[[context-management-in-agent-harnesses]]