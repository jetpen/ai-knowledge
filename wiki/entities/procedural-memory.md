---
updated: 2026-04-25
type: concept
author: auto
title: Procedural Memory
---

1|---
     2|title: [[procedural-memory|Procedural Memory]]
     3|created: 2026-04-12
     4|updated: 2026-04-12
     5|type: concept
     6|tags: ["memory", "concept", "agents", "skills", "hermes"]
     7|sources: ["raw/articles/deepagents-api-ref-2026.md", "raw/articles/hermes-agent-readme-2026.md"]
     8|---
     9|
    10|# [[procedural-memory|Procedural Memory]] (Agent Skills)
    11|
    12|[[procedural-memory|Procedural Memory]] is a type of persistent agent storage dedicated to "how-to" knowledge. It consists of discrete, reusable workflows or "skills" that teach an AI agent how to use its tools to achieve specific outcomes. This is distinct from "Declarative Memory" (which stores facts) or "[[episodic-memory|Episodic Memory]]" (which stores past conversation events).
    13|
    14|## Functional [[procedural-memory|procedural memory]] is increasingly standardized via the **[[agent-skills-standard]]** (agentskills.io). It allows agents to move beyond granular tool calls to high-level procedural execution.
    15|
    16|## Implementation in the Ecosystem
    17|
    18|### 1. [[hermes-agent]]
    19|In the H[[procedural-memory|procedural memory]]e, procedural memory is the output of the **[[agent-learning-loop]]**.
    20|- **Autonomous Creation**: The agent analyzes successful trajectories and formalizes them in[[procedural-memory|procedural memory]]in procedural memory.
    21|- **Self-Impro[[procedural-memory|procedural memory]]in procedural memory are updated and refined as the agent encounters new edge cases.
    22|- **Discovery**: The agent uses FTS5 session search to identify and retrieve r[[procedural-memory|procedural memory]]om procedural memory in real-time.
    23|
    24|### 2. [[deep-agents-sdk]]
    25|Dee[[procedural-memory|procedural memory]]ts procedural memory through the `SkillsMiddleware`.
    26|- **SkillMetadata**: Structures skill data including purpose, trigger conditions, and instructional steps.
    27|- **AGENTS.md**: Context engineering technique where procedural guidance is loaded from local markdown files into the agent's memory state.
    28|
    29|## Core Components of a Skill
    30|- **Metadata**: Title, version, and tags for discovery.
    31|- **Triggers**: Conditions under which the skill should be invoked.
    32|- **Steps**: Procedural, markdown-formatted instructions for the agent to follow.
    33|- **Verification**: Steps for the agent to confirm the task was completed successfully.
    34|
    35|## Benefits
    36|- **Compound Intelligence**: The agent's library of capabilities grows over time through experience.
    37|- **Context Efficiency**: Instead of having every possible tool instruction in the system prompt, the agent only retrieves specific procedural memories relevant to the user's current goal.
    38|- **Interoperability**: Skills conforming to the open standard can potentially be shared across different conforming agent frameworks.
    39|
    40|## Related Concepts
    41|- **[[agent-learning-loop]]**: The primary source of new procedural memories.
    42|- **[[conversation-compaction]]**: Manages the [[procedural-memory|procedural memory]] [[episodic-memory|Episodic Memory]] while procedural memory remains stable.
    43|- **[[dialectic-user-modeling]]**: Stores personalized preferences that shape how procedural memories are applied.
    44|