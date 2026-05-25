---
updated: 2026-04-25
type: concept
author: auto
title: Agentic Memory
created: 2026-04-14
tags: [memory, agentic-memory, llm-arch, context-window, long-term-memory]
sources: 
 - raw/articles/2026-04-13-ramakrishna-agentic-memory-detailed-breakdown.md
 - raw/articles/2043020014035570784.md
---

# Agentic Memory

## Overview
Agentic Memory enables LLMs to transition from stateless chatbots to agents capable of persistent recall, learning, and cumulative conversational evolution.

## Roles of Memory
- **Continuity**: Identity and personal preferences.
- **Context**: Task-specific state (tool outputs, scratchpad).
- **Learning**: Improving future decisions based on history.

## Memory Types
1. **In-context Memory**: The "working desk" of the agent. Limited by the context window. Stores active conversation, system prompts, current tools, and working scratchpad.
2. **External Memory**: Persistent storage outside the model boundary (db, files).
    *   **Structured**: Key-value or SQL lookups.
    *   **Vector**: Semantic similarity retrieval.
3. **[[episodic-memory|Episodic Memory]]**: Recorded events for long-term recall.

## Layered Memory Context
For [[long-running-agents]]:
- **Memory Bank**: Long-Term Memory (LTM), topic-curated.
- **Profiles**: Working Memory (WM), low-latency.

Governance and Audit:
- **Governance**: [[agent-identity]] (IAM), [[agent-registry]] (discovery), [[agent-gateway]] (policy enforcement against PII/drift).
- **Audit**: Monitor and audit memory writes to track behavioral shifts.

## Memory Challenges and Lock-in
Long-term conversational memory remains largely unsolved due to severe trade-offs:
- **Lossy Trade-offs**: "Raw" storage preserves verbatim input but lacks interpretation; "Derived" storage (summaries) is usable but subject to drift over time.
- **Economic Constraints**: Processing full history is costly and context-length limited.
- **Evaluation Paradox**: Lack of ground truth for evaluating long-term conversational significance versus simple retrieval.
- **Memory Lock-in**: As identified by Harrison Chase, memory is becoming the "great competitive moat." Proprietary systems (e.g., OpenAI) encourage vendor lock-in.
    - **Mitigation**: Need for portable solutions such as [[portable-agent-memory]] and [[codejunkie99-brain]].

## See Also
- [[memory-design-axes]]
- [[hermes-agent]]
- [[llm-architecture]] | [[ag-ui]] | [[model-context-protocol]] | [[agent-communication-protocol]]

