---
title: Opik
created: 2026-06-08
updated: 2026-06-08
type: entity
tags: [company, ai-agents, agent-harness, evaluation, agentic-infrastructure, open-source]
sources: [raw/articles/2026-06-08-akshay_pachaar-your-agent-harness-should-repair-itself.md]
author: auto
---

# Opik

## Overview
- Open-source logging, debugging, and optimization platform for AI agents and LLM applications.
- Focus: turn observability traces into an automated debugging + regression-testing loop.

## Core loop (from the source)
1. Trace
2. Ollie diagnoses
3. Ollie proposes a fix
4. Fix applied and verified
5. Test Suite locks the failure as a regression test
6. Back to Trace

## Relationships
- Related to [[agentic-infrastructure]] and [[production-agent-infrastructure]].
- Provides an applied form of [[evaluation]] via regression tests and judge checks.
- Implementable as an [[agent-harness]]-style control loop around a model.

## Related
- [[self-healing-agent-harness]]
