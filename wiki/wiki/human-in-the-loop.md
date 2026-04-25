---
title: Human-in-the-loop
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["agents", "interaction", "concept", "safety", "collaboration"]
sources: ["raw/articles/deepagents-overview-2026.md", "raw/articles/ag-ui-protocol-introduction-2026.md", "raw/articles/symphony-service-spec-2026.md", "raw/articles/claude-cowork-2026.md"]
---

# Human-in-the-loop (HITL)

Human-in-the-loop (HITL) is a design pattern and operational requirement for AI agents where human intervention is integrated into the agent's autonomous execution cycle. This ensures safety, alignment, and accuracy for complex or high-stakes tasks.

## Core Mechanisms

### 1. Approval Gates
Agents pause execution and wait for explicit human confirmation before taking significant actions.
- **[[claude-cowork]]**: Shows the user a plan and waits for approval before interacting with Slack, GitHub, or Notion.
- **[[symphony]]**: Supports implementation-defined "operator-confirmation" policies for coding agent tasks.

### 2. Interrupts and Steering
Allows users to redirect or refine the agent's path in real-time.
- **[[ag-ui]] Protocol**: Standardizes "Interrupts" where users can pause, approve, edit, retry, or escalate a flow mid-session without losing state.
- ****Agent Steering****: Dynamically redirecting agent execution via real-time user input.

### 3. Handoff States
Workflows may end at a specific state requiring human review rather than a final "Done" state.
- **[[symphony]]**: A successful daemon run may end at a "Human Review" tracker state.

## Implementation in [[deep-agents-sdk]]
Deep Agents leverages the **[[langgraph]]** runtime to provide native HITL capabilities:
- **Durable Checkpointing**: The agent's state is persisted while it hibernates waiting for user input.
- **Manual Compaction**: Tools like `compact_conversation` can be gated by HITL to ensure context is managed according to user priorities.

## Benefits
- **Safety**: Prevents agents from executing destructive commands in an **[[isolated-workspace]]**.
- **Alignment**: Allows the agent to learn from user corrections, feeding into the **[[agent-learning-loop]]**.
- **Transparency**: Uses **[[thinking-steps]]** to visualize reasoning before the human grants permission.

## Related Concepts
- **[[durable-execution]]**: The technical foundation that allows agents to wait for humans without crashing.
- **[[shared-state]]**: Enables humans and agents to collaborate on the same data structures during an interrupt.
- **[[agentic-workspace]]**: The environment where HITL controls are most frequently applied.
