---
title: Hybrid Graph (ADK Pattern)
created: 2026-04-23
updated: 2026-04-23
type: concept
tags: [multi-agent-systems, orchestration, agent, framework, google-adk]
sources: [raw/2026-04-23-google-cloud-tech-adk-2.0-orchestration-patterns.md]
author: auto
---

# Hybrid Graph

Pattern 1 in Google Cloud's ADK 2.0 for multi-agent orchestration.

## Description
Addresses orchestration failures by using graph-based workflows:
- Nodes: actions (deterministic or AI-driven).
- Edges: transitions with conditional logic.
- Solves prompt-based workflow drift in LLMs.

Example: Loan application processing – deterministic steps (compliance, credit checks) + AI steps (document assessment).

See [[adk-2.0]] for context and diagram (pattern1.jpg).

## Related
- Part of 5 ADK orchestration patterns.
- Builds on [[agent-skill-design-patterns]].