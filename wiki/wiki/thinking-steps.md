---
title: Thinking Steps
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["reasoning", "transparency", "ag-ui", "concept", "interaction"]
sources: ["raw/articles/ag-ui-protocol-introduction-2026.md", "raw/articles/deepagents-api-ref-2026.md"]
---

# Thinking Steps

Thinking Steps is a specialized visualization pattern used in modern agentic interfaces to surface an AI agent's intermediate reasoning, traces, and tool events to the end user without exposing the raw, unstructured Chain-of-Thought (CoT).

## Overview
As agents move from simple chatbots to complex problem-solvers, the need for transparency increases. Thinking steps allow users to monitor an agent's progress during long-running tasks, providing a "live view" of its internal logic and decision-making process.

## Protocol Implementation: [[ag-ui]]
In the **[[ag-ui]]** (AG-UI), thinking steps are treated as first-class events:
- **Reasoning Visualization**: The protocol standardizes how intermediate reasoning traces are emitted from the model runtime.
- **Trace Coupling**: If the agent uses **[[subagent-spawning]]**, the UI can visualize coupled reasoning traces across the parent and all child sub-agents.
- **Non-Raw Feeds**: Unlike raw LLM logs, thinking steps are structured events that represent significant cognitive milestones or tool execution intents.

## Role in [[deep-agents-sdk]]
Within an **[[agent-harness]]** like deepagents, thinking steps are often coupled with the **[[task-planning]]** mechanism:
- **Plan Progress**: The UI updates the current "thinking step" as the agent completes or revises items in its task plan.
- **Tool Traces**: When the agent uses tools (e.g., `grep` or `edit_file`), these actions are recorded as discrete steps in the reasoning trajectory.

## Benefits
- **Trust & Verification**: Allows users to verify that the agent is on the right track before it reaches a final deliverable or an ****Interrupts|Interrupt**** gate.
- **Debugging**: Facilitates the identification of where an agent's reasoning diverged or where a specific tool call failed.
- **Engagement**: Makes long-running, autonomous tasks feel more responsive and "alive" to the user.

## Related Concepts
- ****Agent Steering****: Users can often use information from thinking steps to redirect the agent in real-time.
- **[[human-in-the-loop]]**: Thinking steps provide the necessary context for users to make informed decisions during approval requests.
- **[[shared-state]]**: The results of thinking steps may be reflected in the real-time updates of a common data store.
