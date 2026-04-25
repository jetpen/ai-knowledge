---
title: Multi-Agents: What's Actually Working
author: Walden (@walden_yan)
date: 2026-04-22
source: https://x.com/i/status/2047054401341370639
type: x-article
tags: [multi-agent, agents, cognition, context-engineering, devin]
---

# Multi-Agents: What's Actually Working

**Posted by:** Walden (@walden_yan)  
**Date:** Apr 22, 2026  
**Engagement:** 5 replies, 41 reposts, 253 likes, 679 bookmarks, 72.6K views  

10 months ago, I wrote ["Don't Build Multi-Agents"](https://cognition.ai/blog/dont-build-multi-agents), arguing that most people shouldn't try to build multi-agent systems [1]. Parallel agents make implicit choices about style, edge cases, and code patterns. At the time, these decisions often conflicted with each other, leading to fragile products. 

A lot has changed since then. At Cognition, we've begun to deploy multi-agent systems that actually work in practice. Our original observations still hold today for parallel-writer swarms: most of the sexy ideas in that space still don’t see meaningful adoption. But we've found a narrower class of patterns that do: setups where multiple agents contribute intelligence to a task while writes stay single-threaded. In this post, I'll summarize what we've learned building them.

## A Refresher on Context Engineering

In the last post, we encouraged readers to reframe agent-building from “prompt engineering” to “context engineering”. Prompt engineering encourages gimmicky techniques like “you’re a senior software engineer” or “think for longer.” Context engineering is more durable and focuses on giving the right context to models while assuming the models become more capable over time. 

For many reasons, context engineering can get very challenging in a multi-agent setup. In the past, we recommended the following principles:

- Share as much context as possible between the agents. Make sure they see the same sources of information, stay on the same page (todo list, plan files), and share the same priors about the overall task they are meant to accomplish. Help them communicate if needed
- Actions carry implicit decisions. When one agent makes certain changes or edits, it might make implicit choices (style, code patterns, how certain edge cases should be handled) that might conflict with the implicit choices of other parallel agents. As a result, decision-making can get quite fragmented in a multi-agent world where multiple agents are taking write actions.

Though many things have changed in the last few months, the need for thoughtful context engineering has not. As a consequence of principle 2, most multi-agent setups in the world are limited to “readonly” subagents, like web search subagents and code search subagents. For example, Devin can call out to a [Deepwiki](http://deepwiki.com/) subagent to acquire codebase context. But these types of subagents mostly resemble tool calls rather than true multi-agent collaboration. We wanted to explore what capabilities we can unlock when agents collaborate in a more interactive way.

## What Changed in the Last 10 Months

To start, models have become way more naturally “agentic.” They intuitively understand tool use, their own context limits, and how to distill their context for collaborators (human or otherwise). As a result, usage of agents has grown … a shit ton. Even when we look at Devin usage in our largest enterprises segment, the segment that has traditionally been cautious toward adopting new technologies, we see an explosion over the last 6 months (~8x).

This explosion of usage has led to both a push and a pull to multi-agents. On the push side of things, the increased capabilities have led users to naturally experiment with many more multi-agent setups. When you are using so many agents, you naturally start to become bottlenecked on everything around those agents: the management, planning, and reviewing. For instance, some have created scripts for Devins to manage other Devins. Many have also leaned into having their coding agents iterate back and forth with their review agents. 

On the pull side of things, the explosion of agent usage has resulted in an explosion of costs. With a new [Mythos class](https://www-cdn.anthropic.com/08ab9158070959f88f296514c21b7facce6f52bc.pdf) of even larger & more capable models on the horizon, the natural question of how one can achieve frontier capabilities at a lower cost arises. And multi-agent systems may be a natural answer. 

There's also been a wave of sensational demos of throwing tons of agents at large engineering projects. Notable examples include [building a web browser](https://cursor.com/blog/scaling-agents) (200k LOC), [building a C compiler](https://www.anthropic.com/engineering/building-c-compiler) (100k LOC), and [optimizing an LLM training script](https://github.com/karpathy/autoresearch) (10k+ iterations). These are exciting but they all share a property most real software doesn't: a simple, verifiable success criterion. Real software requires a system that scales human taste and decision-making, which is the context in which we set out to explore multi-agent systems.

## Some Practical Multi-agent Experiments

### 1) The Code-Review-Loop that’s so stupid it shouldn’t work

You would think that making a model review its own code would not result in any useful findings. But even on PRs written by Devin, Devin Review catches an average of 2 bugs per PR, of which roughly 58% are severe (logic errors, missing edge cases, security vulnerabilities). Often the system will loop through multiple code-review cycles, finding new bugs each time (which isn't always great since it can take a while). Today, we make Devin and Devin Review natively iterate against one another, so that most bugs are already resolved by the time a human opens the PR.

**The counterintuitive part.** Interestingly, we found this technique to work best when the coding and review agents do not share any context beforehand. Why?

There’s a mix of philosophical and technical justifications for this. To start, we must remember that putting the same model in two agents, even if the agent harness is exactly the same, does not quite make them self-biased/correlated in the same way you might imagine one human doing both tasks would be. These agents are ultimately systems that perform based on their context. They don’t have egos, and any shared bias that might exist ultimately comes from their training process, which nowadays we can assume is quite high-quality.

The review agent having a completely clean context also helps it go deeper into areas the original coding agent may not. For one, this is because it is forced to reason backward from the implementation without the spec, and can openly question things which the original agent might have overlooked due to errors in user instruction (ex. a user telling the agent to implement an insecure pattern). Perhaps more importantly though, having a clean context makes the agent smarter because of the math of attention. Context Rot is a well-documented phenomenon that is a result of models making less intelligent decisions at longer and longer context lengths. Models usually have a limited number of attention heads, and when they need to work on a growing context of instructions, prompts, code, etc, important details may not be fully incorporated into its decision-making. When the coding agent has been working for hours on a task, reading through the repo, running commands, thinking about different approaches, fixing errors, it quickly builds up a large context. The dedicated review agent gets to skip this extraneous context, only look at the diff, and re-discover any context it needs as it reads the code from scratch. With a shorter context, the improved intelligence naturally leads to increased detection of nuanced issues.

The final key part to making this system work really well is the communication bridge between the coding agent and review agent. Basically, does Devin properly use its broader context of user instructions, decisions, etc. to filter the bugs that come back from Devin Review? This is key to preventing looping, disobeying the user, doing work that is out of scope, and so on. We found that with some dedicated prompting, models today can make reasonable judgment calls here, and you end up getting some very interesting interactions between the two agents and humans.

**Takeaways:** clean context leads to a notable improvement in capabilities when using a generator-verifier loop. But clear communication and synthesis with the overall context is important for a cohesive experience.

### 2) Large, expensive models are back - introducing “Smart Friend”

[... truncated for brevity; full content captured in raw ...]

[1] Coincidentally, Anthropic came out the next day with a related blogpost about building a multi-agent research system. Both blogposts touched on similar challenges with context engineering and came to similar conclusions about the first area of applicability being in readonly agents