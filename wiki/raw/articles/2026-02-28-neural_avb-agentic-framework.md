---
title: A simple framework to build Agentic Systems that just works
author: neural_avb
date: 2026-02-28
tags: [agentic-systems, frameworks, post-training, LLM, preference-optimization]
---

# A simple framework to build Agentic Systems that just works

Build agentic systems by applying a human-centric mental model: "Put yourself in the agent's shoes."

## Core Framework Principles

### 1. System Prompt
Define the agent's role, objectives, and environment clearly. Key components include:
- **Observations:** What does the agent perceive?
- **Expected Outcome:** Clear definition of success.
- **External Tools:** Available action primitives.
- **Guardrails & Role:** Standard practices for expert behavior.

### 2. Lazy Loading Context
Avoid overloading an agent with full context. Enable lazy loading where the agent accesses specific indices or lookup tables only when required by the task.

### 3. Action Space Design
Define tools based on human necessity.
- Aim for **minimalism**: Too many tools lead to decision paralysis (agentic dementia).
- Name and describe tools precisely.
- Include usage examples in the system prompt.

### 4. Subagent Architectures (Delegation)
Delegate to subagents when:
- Managing diverse, unrelated workloads.
- Handling massive tool outputs that require distillation.
- Executing long-running tasks.
- Parallellizing independent workloads.

### 5. Persistent Work (Memory)
Distinguish between ephemeral turn-based conversation and persistent entity/task state:
- **Chat History:** For conversational context.
- **Memory/Entity Logs:** For persistent knowledge (specific papers, codebases, statistics).
- **Control Flow:** Use tools like TODO lists/scratchpads to track long-term progress.

## Evaluation & Science
Agentic systems design is both an art (design taste) and a science (falsifiable experimentation).
1. **Trace Logging:** Log all agent actions.
2. **Harnessing:** Replay prompts and numerically reward outputs.
3. **Hyperparameter Tuning:** Iteratively test structural/algorithmic changes.
4. **Self-Reflection:** When diagnosing failures, ask "Why might I logically make this same mistake?" to identify context confusion or overload.

---
Source: [Twitter/X Status 2027721962479288566](https://x.com/i/status/2027721962479288566)
