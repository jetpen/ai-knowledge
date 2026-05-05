---
title: HALO (Hierarchical Agent Loop Optimization)
created: 2026-05-05
updated: 2026-05-05
type: concept
tags: [harness-engineering, self-improving-agents, benchmarks]
sources: [raw/articles/2026-05-05-amarsvs-halo-hierarchical-agent-loop-optimization.md]
author: auto
---

# HALO: Hierarchical Agent Loop Optimization

Methodology for **recursively self-improving agent harnesses** via **HALO-Engine** (specialized RLM for large trace analysis).

## Core Loop
1. Collect harness traces (AppWorld: 457 APIs/728 tasks).
2. RLM diagnoses (bugs/patterns).
3. Coding agent fixes.
4. Redeploy.
5. Repeat.

**Results:** SGC 73.7%→**89.5%** (5 cycles; Sonnet 4.6 harness, GPT 5.5 Engine).

**Insights:** Aggregate traces reveal tool/arg/hallucination issues; diagnostics > fixes.

Relates: [[self-healing-agent-harness]], [[harness-engineering]], [[agent-harness]], [[amar-svs]]

**OS:** Repo w/ AppWorld demo/CLI. Hosted: Catalyst.