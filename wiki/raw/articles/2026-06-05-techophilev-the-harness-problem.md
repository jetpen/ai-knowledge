---
title: "The Harness Problem: Why My Agents Keep Breaking After Step 3"
author: techophilev
date: 2026-06-05
source: https://x.com/techophilev/status/2062944609727385989
tags: [agent-harnesses, agentic-infrastructure, code-as-agent-harness, evaluation, planning, belief-state, state-sharing, task-planning]
---

# techophilev on X: "The Harness Problem: Why My Agents Keep Breaking After Step 3"

An article published on X by techophilev (ThatAIGuy) exploring the architecture of agentic systems, focusing on the concepts from the Stanford/UIUC/Meta paper "Code as Agent Harness: Toward Executable, Verifiable, and Stateful Agent Systems" (arXiv: 2605.18747).

## Core Thesis
- Standard agent patterns rely too heavily on raw LLM reasoning (prompts & simple retry loops) to maintain state and planning, leading to failures on long tasks.
- A **harness** (everything around the brain/model) must manage execution, check outcomes, track history, and maintain belief consistency.
- Code should serve as the medium for building this harness because it is executable (results can be validated), leaves structured traces (inspected intermediate steps), and persists state across steps.

## The Plan-Execute-Verify Loop
- Agents shouldn't just act in a loop. They must form a contract-like plan, execute in a sandbox, and undergo rigorous external validation (compilers, linters, tests, or human review).
- Natural language plans are brittle; structured (JSON/code) plans are machine-readable and verifiable.

## Layer-by-Layer Architecture

### Layer 1: Internal Reason and Action (The Local Scope)
- Represents intent and state explicitly (machine-readable structures instead of raw prose).
- Direct environment mutations are forbidden; any state change must route through a central, controlled state coordinator managed by the harness.

### Layer 2: Long-Step Reliability (The Temporal Scope)
- **Structure-Grounded Planning**: Linear decomposition (sequential steps) fails in dynamic tasks. The harness must maintain a state dependency graph, preventing step $N$ from executing until dependencies are verified met.
- **Runnable Memory**: Natural-language message histories expand unboundedly and compress poorly. Memory should be bifurcated into:
  1. *Semantic memory* for tasks and constraints.
  2. *Experiential memory* tracking past errors, attempts, and outcomes to prune loops.
  - High-value memory can contain executable/callable behaviors (small code snippets/tool wrappers) to speed up execution rather than forcing the agent to rebuild them from scratch.

### Layer 3: Collaborative Multi-Agent Consensus (The Social Scope)
- **Belief-State Consistency**: Multiple agents modifying a system suffer from desynchronized context and assumptions, even if files are updated correctly.
- **Semantic Conflict Detection**: Before executing, each agent registers its **read set** (dependencies) and **write set** (targets) with the harness. The harness locks these items to prevent race conditions and semantic state drift.

## Missing Capabilities in Current Harnesses
- **Evidence Bundles**: Rather than simple pass/fail testing, actions should carry detailed verification bundles (ran $X$ tests, auth state preserved, rollback checklist, untracked risks).
- **Self-Modifying Harnesses**: The harness modifying its own rules/dependency graphs carries edge-case risks. Formal safety guarantees and rollback mechanisms for mutated harnesses do not yet exist.

## The Three Critical Architecture Questions
1. Does the execution loop have a physical **sandbox and verify step**, or does it run on simple prompt-based retries?
2. Is the agent memory **runnable and executable**, or is it only text-based retrieval?
3. Does the agent permission model physically live **in the harness code**, or does it depend on polite instructions in a system prompt?
