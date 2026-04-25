---
title: Agent Memory Architecture
created: 2026-04-22
updated: 2026-04-22
type: query
tags: [agent-memory, agent-harness, architecture, agentic-memory-types, hermes-agent, openclaw]
sources:
  - entities/agent-memory-dimensions.md
  - raw/articles/practical-guide-to-memory-for-autonomous-llm-agents-nick-lawson-2026-04-17.md
  - raw/harrison-chase-agent-harness-2026.md
  - entities/hermes-agent.md
  - production-agent-runtime.md
  - index.md
author: Hermes
---

# Agent Memory Architecture in Agent Harnesses

## Overview
Agent memory is a foundational architectural element of **agent harnesses**—the persistent scaffolding that surrounds LLMs to enable reliable, stateful autonomy. As noted by Harrison Chase (2026), while models evolve rapidly, the harness endures as the system responsible for **managing context and memory**. This includes short-term (conversation state, tool results) and long-term (cross-session persistence) handling. Memory is not a "plugin" but the **core of the harness**, with proprietary harnesses risking lock-in.

Modern taxonomies distill agent memory into **three orthogonal dimensions** (Persistence, Content, Storage), yielding a comprehensive typology of memory types. This framework, drawn from cognitive architectures (ACT-R/SOAR), LLM frameworks (LangChain, CrewAI), and surveys (arXiv:2603.07670), captures >95% of implementations.

The **write-manage-read loop** governs all types:
- **Write**: Encode new info (e.g., log episode, distill fact).
- **Manage**: Prune/consolidate (e.g., summarize episodes into semantics).
- **Read**: Retrieve for reasoning/action.

## The Three Dimensions
### 1. Persistence: Volatile ↔ Durable
- **Volatile**: Ephemeral (single turn/session); cleared on reset.
- **Durable**: Persists across sessions/restarts (external storage).

### 2. Content: Declarative ↔ Procedural
- **Declarative**: "What" – facts/events (episodic/semantic).
- **Procedural**: "How" – skills/behaviors/workflows.

### 3. Storage: Parametric ↔ Non-parametric
- **Parametric**: In-model (weights, activations).
- **Non-parametric**: External (files, DBs, vectors).

## Memory Types Table
| Memory Type                  | Persistence | Content      | Storage       | Description & Examples |
|------------------------------|-------------|--------------|---------------|------------------------|
| **Working Memory**           | Volatile   | Declarative | Parametric   | LLM context window; conversation buffer; scratchpad. Prone to "lost in the middle." (LangChain `ConversationBufferMemory`) |
| **Episodic Memory**          | Durable    | Declarative | Non-parametric | Event logs/standups; experiences. E.g., OpenClaw `DREAMS.md`, CrewAI short-term, Hermes SQLite FTS5 log. |
| **Semantic Memory**          | Durable    | Declarative | Non-parametric | Facts/heuristics; RAG stores. E.g., `~/wiki/entities/`, Chroma/FAISS, Mem0, AgentCore long-term. |
| **Procedural Memory (Parametric)** | Durable | Procedural  | Parametric   | Implicit skills in weights (RLHF, fine-tuning). |
| **Procedural Memory (Non-parametric)** | Durable | Procedural | Non-parametric | Skill libraries. E.g., Hermes `SKILL.md`, AgentSkills.io, OpenClaw tools, Deep Agents `SkillsMiddleware`. |

*Rare*: Volatile procedural (reflexes, subsumed into working).

## Role in Agent Harnesses
Harnesses like **Hermes Agent**, **OpenClaw**, **Deep Agents**, and **Symphony** integrate these stores:
- **Hermes Agent** (Nous Research): Four stores – Declarative (`MEMORY.md`/`USER.md`), Procedural (`SKILL.md`), Episodic (SQLite), Identity (`SOUL.md`). Bounded, frozen snapshots, routing logic.
- **OpenClaw**: Predecessor to Hermes; file-based (e.g., `DREAMS.md` for episodic).
- **Deep Agents** (LangChain): `MemoryMiddleware` loads from `AGENTS.md`; harness for planning/memory.
- **Production Runtimes** (e.g., LangSmith LSD): Durable execution + memory integration (working/episodic/semantic/procedural).

**~/wiki** as Semantic Store: Entities (`~/wiki/entities/`), raw episodic (`~/wiki/raw/`), procedural (skills/workflows).

## Challenges & Frontiers
- **Raw-Derived Tradeoff**: Verbatim (lossless) vs. summarized (lossy).
- **POMDP Framing**: Memory as belief state over partial observability.
- **Lock-in**: Own your harness to own your memory.

## See Also
- [[agent-memory-dimensions]]
- [[write-manage-read-loop]]
- [[hermes-agent]]
- [[production-agent-runtime]]
- [[agent-harness]]
