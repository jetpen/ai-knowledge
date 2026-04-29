---
title: Tuning Deep Agents to Work Well with Different Models
created: 2026-04-29
updated: 2026-04-29
type: summary
tags: [deep-agents, harness-engineering, model-profiles, agent-harness, benchmarks]
sources: ["https://x.com/i/status/2049535740233523600"]
author: Viv (@Vtrivedy10)
---

## Summary

**TL;DR:** Deep Agents was previously designed generically to work across model families. Now adding model-specific profiles to adjust prompts, tools, and middleware. Ships profiles for OpenAI, Anthropic, and Google models. Leads to 10–20 point jump on a subset of [[tau2-bench]] over default harness.

Until today, deepagents shipped with a single set of prompts, tools, and middleware for all LLMs. Builders could swap models or extend tools, but base was fixed.

**Harness Profiles:** Control prompts, tools, middleware per-model.

**Why it matters:**
- Prompting guides differ: OpenAI's [[Codex Prompting Guide]] (apply_patch, shell_command), Anthropic's [[Claude prompting guidance]], Opus 4.6→4.7 changes.
- Eval leaderboards: Terminal-Bench 2.0 shows harness impact. Claude Code harness ranks last for Opus 4.6. Previous: gpt-5.2-codex from 52.8% to 66.5% on Terminal-Bench 2.0 via harness changes.

**Results:** 10-20pt improvement on tau2-bench subset.

![Image from post](https://pbs.twimg.com/media/GUs0o0WXAAA1Z1C?format=jpg&amp;name=small)
