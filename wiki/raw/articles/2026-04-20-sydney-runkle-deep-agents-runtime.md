---
title: The runtime behind production deep agents
author: Sydney Runkle (@sydneyrunkle)
date: 2026-04-20
source: https://x.com/sydneyrunkle/status/2046277232537256002
tags: [deep-agents, langsmith, lsd, agent-server, durable-execution, agent-runtime, production-agents]
---

# The runtime behind production deep agents

To build a good agent, you need a good harness. To deploy that agent, you need a good runtime.

The harness is the system you build around the model to help your agent be successful in its domain. That includes prompts, tools, skills, and anything else supporting the model and tool calling loop that defines an agent.

The runtime is everything underneath: durable execution, memory, multi-tenancy, observability, the machinery that keeps an agent running in production without your team reinventing it.

This guide walks through the production requirements that surface once you deploy agents, the runtime capabilities that meet them, and how [deepagents deploy](https://docs.langchain.com/oss/python/deepagents/deploy) packages those capabilities into something you can ship.

## Runtime capabilities for production agents

Throughout this section, "the runtime" refers to [LangSmith Deployment (LSD)](https://docs.langchain.com/langsmith/deployment) and its [Agent Server](https://docs.langchain.com/langsmith/agent-server): LSD runs agents in production, and Agent Server is the interface for assistants, threads, runs, memory, and scheduled jobs.

The table below maps each production requirement to the runtime primitive that meets it.

[Image/table placeholder]

### Durable execution

Agents work by running a loop: Given a prompt, the model reasons, calls tools, observes the results, and repeats until it decides the task is complete.

Unlike a typical web request that returns in milliseconds, this loop can span minutes or hours. A single run might make dozens of model calls, spawn subagents, or wait indefinitely for a human to approve a draft. A crash, deploy, or transient failure anywhere in that loop shouldn't erase the work leading up to it.

In practice, you feel it in two places:
- Long runs need to survive infrastructure failures. A research agent spending twenty minutes gathering sources and synthesizing findings can't afford to restart from scratch if the worker process dies: the agent already paid for the tokens and executed the tool calls. What you want is resumption from the last completed step, with all prior state intact.
- Agents need to be able to stop and wait. An agent that pauses for a human to approve a transaction doesn't know if the human will respond in thirty seconds or three days. Tying up a worker process or a client connection for that entire window isn't viable. The agent needs to truly stop: free resources, release workers, then pick up later exactly where it left off.

Both requirements are solved by the same thing: durable execution.

- Agents run on a managed task queue with automatic [checkpointing](https://docs.langchain.com/oss/python/langgraph/persistence#checkpoints), so any run can be retried, replayed, or resumed from the exact point of interruption.
- Each [super-step](https://docs.langchain.com/oss/python/langgraph/persistence#super-steps) of graph execution writes a checkpoint to the persistence layer (PostgreSQL by default), keyed by a thread_id that acts as a persistent cursor into the run.
- When a worker crashes, the run's lease is released and another worker picks it up from the latest checkpoint.
- When an agent waits for human input, the process hands off its slot and the run sleeps indefinitely until resumed.
- Configurable [retry policies](https://docs.langchain.com/oss/python/langgraph/use-graph-api#add-retry-policies) control backoff, max attempts, and which exceptions trigger retries on a per-node basis.

Durability is the foundation the rest of this list depends on. Because execution can pause and resume across process boundaries, agents can wait indefinitely for human input, run in the background, survive deploys mid-run, and handle concurrent inputs without corrupting state.

### Memory

Agents need two different kinds of memory, and the distinction matters.

Short-term memory is what the agent accumulates within a single conversation. The messages exchanged, the tool calls made, the intermediate state built up across a run. This lives in the checkpoint for the thread, scoped to a thread_id, and disappears (conceptually) when the conversation ends. A follow-up message on the same thread sees everything that came before on that thread.

Long-term memory is what the agent carries across conversations. This can include user preferences learned across conversations, project conventions and best practices, or a knowledge base enhanced with each new query. None of this belongs to any single thread. It's user-level or organization-level context that should persist across every conversation the agent has. Checkpoints alone can't do this, because checkpoint state is scoped to a single thread.

Long-term memory is what the Agent Server's built-in [store](https://docs.langchain.com/oss/python/langgraph/persistence#memory-store) provides.

[Note: Content truncated in snapshot; full article covers multi-tenancy, observability, etc.]
