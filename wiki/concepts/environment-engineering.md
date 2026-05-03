---
title: Environment Engineering
created: 2026-04-23
updated: 2026-04-23
type: concept
tags: [environment-engineering, agent-harness, long-horizon-agents, hola-os]
sources: [raw/articles/2026-04-23-li-jeffrey-agent-harness-is-not-enough.md]
author: auto
---
# Environment Engineering

Practice of designing durable operating contexts around [[agent-harness]] for long-horizon agent systems ([[long-horizon-agents]]).

Introduced by [[li-jeffrey]] in "Agent Harness Is Not Enough."

## Harness vs Environment
- **[[agent-harness]]**: Run-time execution (tools, context mgmt, loops).
- **Environment**: Stable layer (workspace structure, memory, rules, integrations).

Goal: Make invariants portable across harness swaps ([[harness-swap-test]]).

## Layers
- Durable state (files, skills).
- Decidability/governance.
- App wiring.
- Traces/UI.
- Memory (hot/warm/cold).
- Continuity/recovery.

Related: [[harness-engineering]], [[environment-contract]], [[hola-os]].