---
title: Agent Harness Engineering
author: Addy Osmani
date: 2026-04-19
source: https://addyosmani.com/blog/agent-harness-engineering/
ingested: 2026-04-22
tags: [harness-engineering, agentic-dev, llm-arch]
---

# Agent Harness Engineering

## Thesis
Agent = Model + Harness. Harness engineering: Treat scaffolding (prompts/tools/context/hooks/sandboxes/subagents/feedback) as artifact; tighten on every slip. Decent model + great harness > great model + bad harness.

## Key Ideas
- **Skill Issue Reframe**: Failures = config problems, not model limits (HumanLayer).
- **Ratchet**: Mistakes → permanent rules (AGENTS.md, hooks).
- **Components**:
  - Filesystem/Git: Durable state.
  - Bash/code exec: General tool.
  - Sandboxes: Safe exec.
  - Memory/search: Continual learning.
  - Context rot fixes: Compaction, offloading, progressive skills.
  - Long-horizon: Ralph Loops, planner/evaluator splits.
  - Hooks: Enforcement (lint/test/approval).
  - AGENTS.md: Concise checklist.

## Harness-as-Service (HaaS)
Frameworks like Claude/Codex SDKs provide loop/tools; customize config.

Refs: Viv Trivedy (Anatomy), Anthropic (long-running), Simon Willison (loops).