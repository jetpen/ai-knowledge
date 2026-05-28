---
title: Human-in-the-loop (HITL)
created: 2026-04-12
updated: 2026-05-27
type: concept
tags: [agents, interaction, concept, safety, collaboration, long-running-agents]
sources: [raw/articles/deepagents-overview-2026.md, raw/articles/ag-ui-protocol-introduction-2026.md, raw/articles/symphony-service-spec-2026.md, raw/articles/claude-cowork-2026.md, raw/articles/2026-04-22-google-cloud-long-running-agent-patterns.md]
author: auto
---

# Human-in-the-loop (HITL)

Human-in-the-loop (HITL) is a design pattern and operational requirement for AI agents where human intervention is integrated into the agent's autonomous execution cycle. This ensures safety, alignment, and accuracy for complex or high-stakes tasks.

## Core Mechanisms

### 1. Approval Gates
Agents pause execution and wait for explicit human confirmation before taking significant actions.
- **[[claude-cowork]]**: Shows the user a plan and waits for approval before interacting with platforms (Slack, GitHub, etc.).
- **[[symphony]]**: Supports implementation-defined "operator-confirmation" policies for coding agent tasks.
- **Delegated Approval**: For [[long-running-agents]], this involves pausing with full state intact (no serialization loss). A "Mission Control" or inbox view categorizes these pauses as "Needs Input," enabling zero-compute state during the delay with sub-second resumption.

### 2. Interrupts and Steering
Allows users to redirect or refine the agent's path in real-time.
- **[[ag-ui]] Protocol**: Standardizes "Interrupts" where users can pause, approve, edit, retry, or escalate a flow mid-session without losing state.
- **Agent Steering**: Dynamically redirecting agent execution via real-time user input.

### 3. Handoff States
Workflows may end at a specific state requiring human review rather than a final "Done" state.
- **[[symphony]]**: A successful daemon run may end at a "Human Review" tracker state.

## Implementation in [[deep-agents-sdk]]
Deep Agents leverages the [[langgraph]] runtime to provide native HITL capabilities:
- **Durable Checkpointing**: State is persisted while the agent hibernates awaiting user input.
- **Manual Compaction**: Tools for conversation maintenance (e.g., `compact_conversation`) gated by HITL to ensure context alignment.

## Benefits
- **Safety**: Prevents execution of destructive commands in an [[isolated-workspace]].
- **Alignment**: Allows learning from user corrections, feeding into the [[agent-learning-loop]].
- **Transparency**: Uses [[thinking-steps]] to visualize reasoning *before* the human grants permission.

## Related Concepts
- [[durable-execution]] - Technical foundation allowing hibernation without crashing.
- [[shared-state]] - Collaboration on data structures during interrupts.
- [[agentic-workspace]] - The environment where HITL is applied.
