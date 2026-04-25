---
title: Agent Harness Design Principles
created: 2026-04-24
updated: 2026-04-24
type: concept
tags: [agent-harness, design-principles, tool-scoping, reasoning-strategy, permissions, agents]
sources: [raw/articles/akshay-pachaar-agent-harness-design-principles-2026-04-24.md]
---

# Agent Harness Design Principles (Akshay Pachaar)

From [[akshay-pachaar]] (2026-04-24 X post): Every production [[agent-harness]] results from **7 architectural bets**:

1. **Agent count**
2. **Reasoning strategy** ([[react]] vs [[plan-and-execute]])
3. **Context strategy**
4. **Verification**
5. **Permissions** (restrictive > permissive)
6. **Tool scoping** (fewer tools > more; dynamic loading)
7. **Harness thickness**

## Counterintuitive Bets (3 where intuition fails)

### 1. Tool Scoping: Fewer Tools Win
- Intuition: More tools = more capable.
- Reality: Tools consume context, add decision points. Vercel v0 cut 80% tools → better agent. Claude Code: dynamic load → 95% context reduction.
- Principle: Bloated toolkit = cognitive load.

### 2. Reasoning Strategy: Plan-Execute > ReAct
- Intuition: ReAct (reason at every step) is modern/sophisticated.
- Reality: Plan once, execute → 3.6x faster for bounded tasks. Most steps need execution, not re-reasoning.

### 3. Permissions: Restrictive > Permissive
- Intuition: Permissive = fast dev/ship.
- Reality: Friction (gates/approvals) prevents incidents. Permissive leads to irreversible errors in prod.

## Pattern
Intuitive choices optimize dev feel (more visible capability). Optimal optimize prod performance (less context/LLM calls, fewer mistakes).

Examples: Anthropic, OpenAI, CrewAI, LangChain.

Akshay building minimal open-source harness.

Related: [[harness-engineering]], [[agent-harness]]