---
title: ReAct
created: 2026-04-15
updated: 2026-04-15
type: entity
tags: [agentic-ai, design-patterns]
sources: [raw/roadmap-to-agentic-ai-2026-04-15.md]
---

# ReAct

ReAct (Reasoning and Acting) is a foundational agentic design pattern that combines chain-of-thought reasoning with tool use in a continuous feedback loop.

## Structure
The pattern follows a repetitive three-phase structure:
- **Thought**: The agent reasons about the current state and determines the next step.
- **Action**: The agent executes an action (e.g., tool call, code execution, API request).
- **Observation**: The agent observes the results of the action and uses that information to update its plan or conclude the task.
