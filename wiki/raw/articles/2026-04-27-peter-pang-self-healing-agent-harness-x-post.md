---
title: The Self-Healing Agent Harness
created: 2026-04-27
updated: 2026-04-27
type: source
tags: [agent-harness, self-healing, agentic-ai, production-ai, qa-evaluation]
sources: 
  - https://x.com/intuitiveml/status/2048912026018484317
---

# Original X Post by Peter Pang (@intuitiveml)

**Posted:** 2026-04-27  
**Engagement:** 5 replies, 31 reposts, 196 likes, 456 bookmarks, 11K views  

**Media:** 
![Image 1](https://pbs.twimg.com/media/HG8NRQ1bwAA2sVU?format=jpg&name=large)
![Image 2](https://pbs.twimg.com/media/HG8NzS2aUAA2vXa?format=jpg&name=large)
![Image 3](https://pbs.twimg.com/media/HG8OC7mbgAAUUfu?format=jpg&name=large)
![Image 4](https://pbs.twimg.com/media/HG8OY2TbYAAUxqz?format=jpg&name=large)
![Image 5](https://pbs.twimg.com/media/HG8Py53bMAADV2u?format=jpg&name=large)
![Image 6](https://pbs.twimg.com/media/HG8Qf7FboAAF8nO?format=jpg&name=large)
![Image 7](https://pbs.twimg.com/media/HG8QywWbAAAVw24?format=jpg&name=large)
![Image 8](https://pbs.twimg.com/media/HG8Q-bvaoAAcZ9r?format=jpg&name=large)

## Post Content

> The Self-Healing Agent Harness 

> Last month, I said 99% of our production code is written by AI.  
> That wasn’t a small change. We had to rebuild the way we work, with agents at the center. Now we ship to production three to eight times a day.  

> Since then, the question I hear most from other founders is:  
> Who tests it?  

> The answer is not “more QA.” We don’t have a QA team. We don’t have a staging environment where people click around before a release. No one on the team is sitting there reading transcripts and scoring agent replies by hand.  

> Instead, we built a system that catches failures and helps fix them. We call it the self-healing Agent Harness  

> After running this in production, two lessons became obvious:  
> - Grade the outcome, not the trajectory. Agents often take paths that look inefficient or strange to humans, but still produce the right answer. Penalizing the path is not an efficient way to evaluate agent performance.  
> - A score with no ticket means nothing. A bad score that does not feed engineering is just a dashboard. A bug pipeline without grader signals is blind. Build both, or build neither.  

> Don't get trapped chasing "scientific correctness." I've seen plenty of people with research backgrounds get caught debating whether agent-based evaluation is methodologically rigorous enough. For a startup, that kind of debate is a luxury you can’t afford. It misses the point. The purpose of an agent-based grader isn’t to rank models against each other for a paper. It’s to identify recurring issues in your product, fast. A good enough signal that triggers a fix today beats a perfectly defensible benchmark that ships next quarter.  

> That loop, grade, triage, fix, verify, and gate releases, is what we call the Agent Harness  

> **The Thesis: Evaluation and QA Are the Same Loop**  

> In a traditional SaaS company, these usually live in different places:  
> • Model evaluation asks: is the model giving good answers on live traffic? ML or data science owns that. They make dashboards.  
> • QA asks: does the product work in production? Engineering owns that. They file tickets, fix bugs, and ship releases.  

> For an AI agent platform, those are the same question. A bad agent response is both a metric to chart and a bug to triage and fix. And that bug could come from almost anywhere:  
> • The model reasoned poorly or hallucinated  
> ...

## Key Entities
- **Self-Healing Agent Harness**: Production system for AI-generated code (99% of prod code), ships 3-8x/day.
- **Agent Harness**: Unified eval + QA loop (grade → triage → fix → verify → gate).
- **IntuitiveML**: @intuitiveml (Peter Pang).
