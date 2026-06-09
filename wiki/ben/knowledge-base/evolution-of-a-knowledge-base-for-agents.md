---
title: Evolution of a Knowledge Base for Agents
author: Ben Eng
created: 2026-05-07
tags:
  - knowledge-graph
  - agent-harness
  - ai-agents
  - future-trends
---
![[agent-evolution.drawio.png]]

Asked ChatGPT: `does Codex use more token consumption when many skills are registered? or does the context window not get filled up by skill names and descriptions to match prompts to skill calls?`

Answer:  

Yes—there is some token overhead from registered skills in Codex, but it is bounded. OpenAI says Codex starts with each skill's name, description, and file path in context, and that initial skills list is capped at roughly 2% of the model's context window, or 8,000 characters when the window is unknown. When there are too many skills, Codex shortens descriptions first, and for very large sets some skills may be omitted from the initial list.

So the answer is: many registered skills can increase prompt-token usage somewhat, but not without limit.

The 2% limit resulting in compression and capping would explain why some people are seeing unreliable skill execution.

It won't be long before we see every agent harness innovate in these areas:  
  

1. Given a knowledge base containing the totality of knowledge about a business (mission, strategy, processes, procedures, policies, standards, guidelines, etc.), based on my current task (prompt) fetch the most relevant knowledge into my context to guide its execution.
2. Given a knowledge base containing the totality of skills, MCP tools, workflows, recipes, and every type of markdown that is relevant to every job role in my business, do the matching of my prompt without occupying any tokens in my context.

[The runtime behind production deep agents](https://x.com/sydneyrunkle/status/2046277232537256002) by Sydney Runkle

[Harness Engineering: What Every AI Engineer Needs to Know in 2026](https://x.com/i/status/2063544956158185927) by Rahul

[The Anatomy of an Agent Harness](https://x.com/i/status/2031408954517971368) by Viv

[Why Every Company Is Building a Brain to Capture All Working Context](https://x.com/i/status/2062185564871295459) by Mr. Buzzoni

Models improve

Orchestration of a unit of work for the business. It is called a loop, because it controls the execution and failure handling until the work is done. The work may be delegated to one or more subagents.

[WTF Is a Loop? Peter Steinberger vs. Boris Cherny](https://x.com/i/status/2063865685558903149) by Matt Van Horn

Long context problems

[RLM Agents live healthier when they talk via Structured Outputs](https://x.com/i/status/2063907440509571354) by 

Overcoming context rot [Lost in the Middle: How Language Models Use Long Contexts](https://arxiv.org/abs/2307.03172) by Nelson F. Liu, et al