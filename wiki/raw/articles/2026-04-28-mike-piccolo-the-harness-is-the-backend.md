---
title: The Harness Is the Backend
created: 2026-04-28
updated: 2026-04-28
type: summary
tags: [agent-harness, harness-engineering, anthropic, openai, crewai, langgraph, agentic-infrastructure]
sources: []
author: Mike Piccolo (@mfpiccolo)
source-url: https://x.com/i/status/2049139067359568032
image: raw/images/2026-04-28-mike-piccolo-harness-image.jpg
---

# The Harness Is the Backend

**Mike Piccolo (@mfpiccolo)** · 1 reply, 3 reposts, 27 likes, 80 bookmarks, 8079 views

The most important architectural question in AI infrastructure right now isn’t which model to use. It’s how much infrastructure is required to build something useful with it.

Anthropic, OpenAI, CrewAI, LangChain all call that wrapping the agent harness. The harness includes the orchestration loop, tools (MCP, A2A), memory, context management, and error handling that make a model useful. They all agree the model isn’t the product. The infrastructure is. They disagree deeply on how much of it should exist.

Anthropic keeps their harness thin. It’s an elegant loop: Assemble the prompt, call the model, execute tool calls, and repeat. The model decides everything. OpenAI adds more structure: instruction stacks, orchestration modes, and explicit handoff patterns. CrewAI takes a multi-pronged approach: deterministic Flows for routing and validation, autonomous agents for the rest. LangGraph has the biggest harness Every decision is a node, every transition a defined edge, the entire workflow encoded in the harness.

The spectrum runs from strongly trusting the model and weakly encoding the logic to weakly trusting the model, and strongly encoding the logic. And every team building with agents has to choose what size of harness they need.

But there’s an assumption buried in the debate that nobody is questioning: that the harness is extrinsic to the traditional backend.

The agent’s loop, its tools, and its memory live in one layer: the harness. While execution infrastructure such as queues, state, HTTP routing, server side rendering, observability, and all other backend components live in another: “the backend”.

I believe that this is temporary and it’s just a small step along the way to true adoption and acceptance of agentic infrastructure into “the backend”.

## How Agents Work Today

Here’s how most agentic architectures work. The harness is a Python process (or TypeScript, or a managed framework) that wraps the model. When the agent decides to act, the harness translates a tool call into an HTTP request which in turn triggers something to happen on the backend like a queue publish or a database write. The backend is its own world that is kept separate from the agents.

The harness retries on its own schedule, the queue retries on its own conditions, and the HTTP layer manages its own timeouts. There is no trace directly connecting these disparate systems. When something breaks debugging means correlating logs across systems and reconstructing observed behavior. This is a common process in backend engineering but whereas prior systems were largely deterministic, agents are stochastic at best.

With every additional agent the probabilities widen and at the most basic level are agents^2 * services. Put another way, 1 agent and 5 backend systems is 5 stochastic paths to debug. 4 agents and 5 backend systems are 80 stochastic paths to debug.

There is no good way to make agents more deterministic, much of their basic functionality is intended to give varied answers for similar and even identical inputs. They’re not stochastic by chance, they’re stochastic by intention because they make computers useful in a brand new way. The billion dollar question is how to handle agents properly by creating the correct harnesses in the correct contexts.
