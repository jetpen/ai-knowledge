---
title: Agent Loop as Control System
created: 2026-06-09
updated: 2026-06-11
type: concept
tags: [agentic-dev, agent, agent-harness-loop, harness-engineering, agent-memory-stack]
sources: ["raw/twitter/2026-06-09-intuitmachine-loop-around-the-model.md", "raw/twitter/2026-06-11-loop-engineering-isn-t-what-you-think.md"]
author: auto
---

# Agent Loop as Control System

## Thesis (from the X post)
Model quality is rarely the limiting factor when agents fail in production.
Failure is primarily caused by the loop around the model—how control is implemented for planning/execution/verification and how the agent transitions between steps.

## What this implies for production
- Optimize the execution loop (control policy) before searching for a better model.
- Treat the harness/agent loop as an explicit engineering artifact with measurable failure modes.
- Prefer loops with an objective success function (tests, scores, template matching) and explicit exit criteria.
- When success is subjective (taste/vision/UX), require a human-in-the-loop gate to prevent uncontrolled drift and expensive “slot machine” loops.

## Related
- [[concepts/production-agent-runtime]]
- [[concepts/agent-harness]]
- [[concepts/harness-engineering]]
- [[concepts/agent-learning-loop]]
- [[concepts/human-in-the-loop]]
- [[concepts/task-planning]]
