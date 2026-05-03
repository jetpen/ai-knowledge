---
title: Agentic AI Design Patterns
created: 2026-04-15
updated: 2026-04-15
type: concept
tags: [agentic-ai, design-patterns, architecture]
sources: [raw/roadmap-to-agentic-ai-2026-04-15.md]
---

# Agentic AI Design Patterns

Agentic design patterns are reusable architectural templates for creating predictable, debuggable, and composable agent systems.

## Core Philosophy
- **Architectural vs. Prompt Failures**: System behavior issues are often better solved by architectural refinement (explicit loops, state management) than prompt engineering alone.
- **Pattern Selection**: Follows a "start simple" philosophy. Avoid premature architectural complexity to minimize latency, costs, and failure surfaces.

## ReAct (Reasoning and Acting)
[[react]] is the foundational agentic pattern. It utilizes a continuous feedback loop:
1. **Thought**: Reason about the next step.
2. **Action**: Invoke a tool or perform a task.
3. **Observation**: Process results and refine the plan.

## Design Principles
- Define clear exit conditions.
- Establish contracts for tool invocation.
- Ground reasoning in observability.
