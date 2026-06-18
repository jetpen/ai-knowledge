---
title: Autonomous Loop Workflows
created: 2026-06-18
updated: 2026-06-18
type: concept
tags: [concept, automation, agent-harness-loop, agentic-dev, efficiency]
sources: [raw/twitter/2026-06-11-loop-engineering-isn-t-what-you-think.md]
author: auto
---

# Autonomous Loop Workflows

**Autonomous Loop Workflows** (often abbreviated as **Agentic Loops** or **Autonomous Loops**) refer to execution loops where the human is removed from active step-by-step guidance. Instead of direct steering, the human closes the loop *once* at the beginning by providing a goal definition (such as `/goal` or `/sloop` commands) and objective evaluation criteria.

The agent generates work, evaluates its output, course-corrects, and loops on its own until termination.

## Structural Tradeoffs

Removing human oversight introduces specific benefits and severe cost/drift risks:

| Dimension | [[concepts/human-in-the-loop.md|Human-in-the-Loop (HITL)]] | Autonomous Loop Workflows |
|---|---|---|
| **Course Correction** | High and fast; catches semantic drift before expensive code is written. | Deferred; errors propagate during execution, risking random "slot machine" outcomes. |
| **Token Cost** | Lower; bounded context iterations. | Extremely High; compounding token cost over 10-50 execution runs carrying full state. |
| **Success Domain** | Subjective (taste, UX, vision, startup building). | Objective (test passes, migration validations, template matching). |

## Economics of Loop Workflows
Because autonomous loops run repeated cycles of generation, analysis, and execution, they carry massive context overhead across active turns. This compounds token usage rapidly, making unbounded loops economically unviable for individual developers or teams unless capped standard exit thresholds are enforced.

## Key Examples
- **Ralph Wiggum Loop**: Minimal script-scoped testing loops popularized by [[entities/geoffrey-huntley.md|Geoffrey Huntley]].
- **Automated Code Review Loop**: A pattern where a review engine (such as Greptile or CodeRabbit) grades shifts, and a self-improving loop automatically applies fixes and re-pushes commits until a specific target score is achieved.

## See Also
- [[concepts/agent-loop-control-system.md|Agent Loop as Control System]]
- [[concepts/ralph-wiggum-loop.md|Ralph Wiggum Loop]]
- [[concepts/human-in-the-loop.md|Human-in-the-Loop (HITL)]]
- [[concepts/code-review-loop.md|Code-Review Loop]]
- Source document: [[raw/twitter/2026-06-11-loop-engineering-isn-t-what-you-think.md|Loop Engineering Isn't What You Think]]
