---
title: Self-Healing Agent Harness
created: 2026-04-27
updated: 2026-04-27
type: concept
tags: [agent-harness, self-healing, production-ai, qa-evaluation, agentic-ai]
sources: 
  - ~/projects/ai-knowledge/wiki/raw/articles/2026-04-27-peter-pang-self-healing-agent-harness-x-post.md
---

# Self-Healing Agent Harness

Production system catching/fixing agent failures automatically (IntuitiveML).

## Core Loop
1. **Grade outcome** (not trajectory) on live traffic.
2. **Triage** → ticket (no score without fix).
3. **Fix** (model/prompt/tool).
4. **Verify** + gate releases.

> "Evaluation and QA are the same loop."

Lessons:
- Avoid path penalization (agents detour successfully).
- Dashboards without engineering = useless.
- Prioritize fast signals over "scientific" benchmarks.

## Relationships
- Enables [[agent-harness]] at scale (3-8x/day deploys).
- Builds on [[harness-engineering]], [[agent-harness-design-principles]].
- Addresses QA in [[production-ai]] (no manual QA/staging).

Exemplar: [[intuitiveml]] (99% AI code).
