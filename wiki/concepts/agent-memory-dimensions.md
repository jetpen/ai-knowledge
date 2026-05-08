---
title: Agent Memory Dimensions
created: 2026-04-19
updated: 2026-04-19
type: concept
tags: [agentic-memory, ai-agents, llm-arch, memory]
sources:
  - https://towardsdatascience.com/a-practical-guide-to-memory-for-autonomous-llm-agents/
  - https://arxiv.org/pdf/2603.07670
  - https://docs.langchain.com/docs/modules/memory/
  - https://docs.crewai.com/concepts/#memory
  - https://en.wikipedia.org/wiki/Cognitive_architecture
author: Hermes
---

# Agent Memory: Orthogonal Dimensions

## Overview

Classifications of agent memory from cognitive architectures, LLM agent frameworks, and recent research can be distilled into three independent (orthogonal) dimensions. This model provides a compact, generative typology that captures >95% of observed memory types while exposing their fundamental trade-offs.

## The Three Dimensions

### 1. Persistence: Volatile ↔ Durable
- **Volatile**: Memory that exists only during a single agent turn or session; cleared on reset or context window overflow.
  - *Examples*: LLM context window, conversation buffer, temporary scratchpad.
  - *Failure modes*: Catastrophic forgetting, limited horizon, "lost in the middle".
- **Durable**: Memory that persists across sessions, agent restarts, or system reboots; stored externally.
  - *Examples*: Fact databases, skill libraries, event logs, procedural traces.
  - *Failure modes*: Storage bloat, retrieval latency, consistency challenges.

### 2. Content: Declarative ↔ Procedural
- **Declarative**: "Knowledge what" – facts, events, heuristics, beliefs that can be explicitly stated or queried.
  - Subtypes:
    - **Episodic**: Concrete, time-bound experiences (e.g., "yesterday the user asked about X").
    - **Semantic**: Abstracted, context-free knowledge (e.g., "Paris is the capital of France").
  - *Storage*: Often symbolic, textual, or embedded vectors.
- **Procedural**: "Knowledge how" – skills, behaviors, policies, or executable workflows that map situations to actions.
  - *Nature*: Often implicit, compiled, or represented as rules/programs.
  - *Execution*: Triggered by context; may involve tool use, planning, or motor output.

### 3. Storage: Parametric ↔ Non-parametric
- **Parametric**: Memory encoded within the agent's model parameters or immediate context (e.g., weights, activations, prompt).
  - *Advantages*: No external lookup; tightly coupled with inference.
  - *Limitations*: Fixed capacity; expensive to update; prone to interference.
- **Non-parametric**: Memory stored in external, addressable systems (e.g., databases, files, vector stores, graphs).
  - *Advantages*: Theoretically unbounded; modular; independently updatable.
  - *Limitations*: Retrieval latency; requires indexing/search; consistency overhead.

## Combining the Dimensions: Memory Types Table

The three dimensions combine to yield eight theoretical regions. In practice, six are commonly observed; two (volatile procedural) are rare or nonsensical.

| Memory Type | Persistence | Content     | Storage          | Typical Use Cases & Examples |
|-------------|-------------|-------------|------------------|------------------------------|
| **Working Memory** | Volatile | Declarative | Parametric | LLM context window; LangChain `ConversationBufferMemory`; temporary reasoning scratchpad. |
| **Episodic Memory** | Durable | Declarative | Non-parametric | Autobiographical event log; OpenClaw `DREAMS.md` or daily standups; CrewAI short-term memory; AgentCore short-term. |
| **Semantic Memory** | Durable | Declarative | Non-parametric | Curated fact base; vector store (Chroma, FAISS, Pinecone) for RAG; Mem0/MemPalace; AgentCore long-term; `~/wiki/` itself as a semantic store. |
| **Procedural Memory (Parametric)** | Durable | Procedural | Parametric | Fine-tuned policy networks; implicit skills in model weights (e.g., via RLHF); learned attention patterns. |
| **Procedural Memory (Non-parametric)** | Durable | Procedural | Non-parametric | Explicit skill library; Hermes `SKILL.md` files; AgentSkill Standard (agentskills.io) workflows; OpenClaw tool scripts; ACT-R production rules. |
| **(Rare) Volatile Procedural** | Volatile | Procedural | Parametric | Momentary action policies (e.g., single-step reflex); generally subsumed into working memory or ignored. |

*Note*: Pure volatile non-parametric declarative is also uncommon; transient external caches might fit but are typically treated as working memory extensions.

## Relationship to Other Taxonomies

### Backends vs. Substrates (Witcheer Thread)
- **Memory Backends** (fact extraction → vector/graph DB) ≈ Durable + Declarative + Non-parametric (Semantic/Episodic).
- **Context Substrates** (human-readable files compounding over sessions) ≈ Durable + Declarative/Procedural + Non-parametric (e.g., OpenClaw's `MEMORY.md`, `DREAMS.md`, skill files) *or* Durable + Procedural + Parametric if skills are internalized.

### Write-Manage-Read Loop (Lawson, TDS 2026)
The loop operates across all dimensions:
- **Write**: Encoding new information into any cell (e.g., adding a fact to semantic memory, logging an episode, acquiring a skill).
- **Manage**: Pruning, consolidating, or redistributing (e.g., summarizing episodes into semantic facts; distilling skills; vector index maintenance).
- **Read**: Retrieval for use in reasoning or action (e.g., context injection, skill activation, fact lookup).

### Cognitive Architectures (ACT-R/SOAR)
- Maps cleanly: Declarative ↔ chunks (episodic/semantic); Procedural ↔ productions; Working ↔ goal buffer (parametric, volatile).

## Practical Implications for AI/ML Wiki Maintenance

In the context of Ben's AI/ML research wiki (`~/wiki`):
- **Working Memory**: Agent's context window during a session; not persisted.
- **Episodic Memory**: Ingestion timeline (`~/wiki/raw/articles/`), daily notes, interaction logs.
- **Semantic Memory**: Entity wiki pages (`~/wiki/entities/`), concept maps, tag taxonomy (`SCHEMA.md`).
- **Procedural Memory (Non-parametric)**: Skill files (`~/wiki/entities/*-skill.md`), agent loops (e.g., `agent-learning-loop`), maintenance workflows (this very skill).
- **Procedural Memory (Parametric)**: Fine-tuned models that have internalized wiki navigation or synthesis patterns (not currently present but aspirational).

Maintenance workflows (health check, discovery link pass, synthesis) are themselves procedural memory artifacts that manage the semantic and episodic stores.

## References

1. Lawson, N. (2026, April 17). *A Practical Guide to Memory for Autonomous LLM Agents*. Towards Data Science. https://towardsdatascience.com/a-practical-guide-to-memory-for-autonomous-llm-agents/
2. Zhang, Y. et al. (2026). *Memory for Autonomous LLM Agents: Mechanisms, Evaluation, and Emerging Frontiers*. arXiv:2603.07670.
3. LangChain. *Memory*. https://docs.langchain.com/docs/modules/memory/
4. CrewAI. *Memory Concepts*. https://docs.crewai.com/concepts/#memory
5. Wikipedia contributors. (2026). *Cognitive architecture*. Wikipedia, The Free Encyclopedia. https://en.wikipedia.org/wiki/Cognitive_architecture

## See Also

- [[working-memory]]
- [[episodic-memory]]
- [[semantic-memory]]
- [[procedural-memory]]
- [[queries/agent-memory-architecture]]
- [[write-manage-read-loop]]
- [[agent-skills-standard]]
- [[agent-learning-loop]]
- [[memory-design-axes]]