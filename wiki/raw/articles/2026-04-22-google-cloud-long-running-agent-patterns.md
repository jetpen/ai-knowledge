---
title: 5 Agent Design Patterns for Long-running AI Agents
author: Google Cloud Tech (@GoogleCloudTech), @addyosmani, @Saboo_Shubham_
date: 2026-04-22
source: https://x.com/i/status/2046989964077146490
type: x-article
tags: [long-running-agents, agent-runtime-google, google-agent-development-kit, production]
---

# 5 Agent Design Patterns for Long-running AI Agents

**Posted by:** Google Cloud Tech (@GoogleCloudTech)  
**Date:** Apr 22, 2026 (11:30 AM)  
**Engagement:** 3 replies, 92 reposts, 565 likes, 997 bookmarks, 55.4K views  

Developers spend weeks perfecting prompt engineering, tool calling, and response latency. None of it matters when your agent needs to stay alive for five days.

The workflows that actually matter in production (processing thousands of insurance claims, running week-long sales sequences, reconciling financial data across systems) don't fit inside a single conversation turn. They take days, not seconds.

The moment you try to build these long-running agents, you realize most agent architectures are stateless. They reconstruct context from databases on every interaction. They lose the reasoning chain, the soft signals, and the confidence gradients that made the agent's previous decisions make sense.

At Cloud Next '26, we announced that [[agent-runtime-google|Agent Runtime]] now supports long-running agents that maintain state for up to seven days. In this article, we’ll share five essential agent design patterns for building long-running agents with Agent Runtime.

By [[addy-osmani|@addyosmani]] and [[shubham-saboo|@Saboo_Shubham_]]

Here are five design patterns that separate production systems from demos.

## Pattern 1: [[checkpoint-and-resume|Checkpoint-and-Resume]]

The most common failure mode in multi-day workflows is context loss. An agent processes 200 documents over four hours, then hits an error on document 201. Without checkpointing, you restart from scratch.

Long-running agents on [[agent-runtime-google|Agent Runtime]] maintain persistent execution state in a secure cloud sandbox. The agent has full access to bash commands and a sandboxed file system, so you can write intermediate results to disk, maintain processing logs, and recover from failures.

Treat your agent like a long-running server process, not a request handler. The same way you build a data pipeline that processes millions of records: checkpoint progress, handle partial failures, ensure idempotency.

Here is how you structure a document processing agent that checkpoints after every batch using [[google-agent-development-kit|Google Agent Development Kit]]:

```python
from google.adk import Agent, ToolContext

class DocumentProcessor(Agent):
    """Processes large document sets with checkpoint-and-resume."""

    async def process_batch(self, docs: list, ctx: ToolContext):
        checkpoint = self.load_checkpoint()  # Resume from last position
        start_idx = checkpoint.get("last_processed", 0)

        for i, doc in enumerate(docs[start_idx:], start=start_idx):
            result = await self.classify_and_extract(doc)
            self.results.append(result)

            # Checkpoint every 50 documents
            if (i + 1) % 50 == 0:
                self.save_checkpoint({
                    "last_processed": i + 1,
                    "partial_results": self.results,
                    "timestamp": datetime.now().isoformat()
                })

        return self.compile_final_report()
```

Notice the checkpoint granularity. Not after every document (wasteful). Not only at the end (risky). Fifty documents per batch balances durability against overhead.

## Pattern 2: [[delegated-approval|Delegated Approval (Human-in-the-Loop)]]

Every framework advertises human-in-the-loop. But in practice, most implementations are: serialize state to JSON, send a webhook, hope someone checks it.

When the human responds hours later, the agent has to deserialize, re-establish context.

Long-running agents handle this differently: pause in place with full state intact. Mission Control provides categorized inbox ("Needs input", "Errors").

## Pattern 3: [[memory-layered-context|Memory-Layered Context]]

Memory Bank (long-term) + Profiles (working). Govern with [[agent-identity]], [[agent-registry]], [[agent-gateway]] to prevent drift/leakage.

## Pattern 4: [[ambient-processing|Ambient Processing]]

Event-driven (Pub/Sub, BigQuery). Policies externalized via Gateway.

## Pattern 5: [[fleet-orchestration|Fleet Orchestration]]

Coordinator delegates to specialists; independent updates via containers.

Get started: https://cloud.google.com/gemini-enterprise/agents
