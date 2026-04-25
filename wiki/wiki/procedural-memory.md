---
title: [[procedural-memory|Procedural Memory]]
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["memory", "concept", "agents", "skills", "hermes"]
sources: ["raw/articles/deepagents-api-ref-2026.md", "raw/articles/hermes-agent-readme-2026.md"]
---

# [[procedural-memory|Procedural Memory]] (Agent Skills)

[[procedural-memory|Procedural Memory]] is a type of persistent agent storage dedicated to "how-to" knowledge. It consists of discrete, reusable workflows or "skills" that teach an AI agent how to use its tools to achieve specific outcomes. This is distinct from "Declarative Memory" (which stores facts) or "[[episodic-memory|Episodic Memory]]" (which stores past conversation events).

## Functional [[procedural-memory|procedural memory]] is increasingly standardized via the **[[agent-skills-standard]]** (agentskills.io). It allows agents to move beyond granular tool calls to high-level procedural execution.

## Implementation in the Ecosystem

### 1. [[hermes-agent]]
In the H[[procedural-memory|procedural memory]]e, procedural memory is the output of the **[[agent-learning-loop]]**.
- **Autonomous Creation**: The agent analyzes successful trajectories and formalizes them in[[procedural-memory|procedural memory]]in procedural memory.
- **Self-Impro[[procedural-memory|procedural memory]]in procedural memory are updated and refined as the agent encounters new edge cases.
- **Discovery**: The agent uses FTS5 session search to identify and retrieve r[[procedural-memory|procedural memory]]om procedural memory in real-time.

### 2. [[deep-agents-sdk]]
Dee[[procedural-memory|procedural memory]]ts procedural memory through the `SkillsMiddleware`.
- **SkillMetadata**: Structures skill data including purpose, trigger conditions, and instructional steps.
- **AGENTS.md**: Context engineering technique where procedural guidance is loaded from local markdown files into the agent's memory state.

## Core Components of a Skill
- **Metadata**: Title, version, and tags for discovery.
- **Triggers**: Conditions under which the skill should be invoked.
- **Steps**: Procedural, markdown-formatted instructions for the agent to follow.
- **Verification**: Steps for the agent to confirm the task was completed successfully.

## Benefits
- **Compound Intelligence**: The agent's library of capabilities grows over time through experience.
- **Context Efficiency**: Instead of having every possible tool instruction in the system prompt, the agent only retrieves specific procedural memories relevant to the user's current goal.
- **Interoperability**: Skills conforming to the open standard can potentially be shared across different conforming agent frameworks.

## Related Concepts
- **[[agent-learning-loop]]**: The primary source of new procedural memories.
- **[[conversation-compaction]]**: Manages the [[procedural-memory|procedural memory]] [[episodic-memory|Episodic Memory]] while procedural memory remains stable.
- **[[dialectic-user-modeling]]**: Stores personalized preferences that shape how procedural memories are applied.
