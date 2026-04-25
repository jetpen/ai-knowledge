---
title: Harness Engineering
created: 2026-04-14
updated: 2026-04-22
type: concept
tags: [harness-engineering, agentic-dev, llm-arch, software-development, agents, ai-infrastructure]
sources: 
  - raw/articles/2037200578842157462.md
  - raw/articles/agent-harness-engineering-addyosmani-2026-04-22.md
  - raw/articles/2026-04-22-alphasignal-ai-harness-engineering.md
author: auto
---

# Harness Engineering

## Overview
Harness Engineering: Agent = Model + Harness.  
Optimize scaffolding (prompts/tools/context/hooks/sandboxes/subagents/loops) as artifact.  
Decent model + great harness > great model + bad harness (Addy Osmani, Nav Toor, AlphaSignal AI).  
Failures = config/skill issues → ratchet into rules/hooks (AGENTS.md).

AlphaSignal AI (2026-04-22): In 2026, harness engineering emerged as the key moat. OpenAI shipped 1M lines via agent-written code in a tightly constrained repo environment. Anthropic decoupled brain/hands via Planner-Generator-Evaluator. LangChain boosted Terminal Bench 2.0 from 52.8%→66.5% via "reasoning sandwich." ThoughtWorks framework: guide/sensor × computational/inferential axes.

## Core Philosophy
Elite teams treat agent mistakes as engineering problems: fix the system so errors recur less frequently. Major gains on fixed models (LangChain: 52.8%→66.5%; Opus 4.7 self-verification reduces evaluator need).

## Components (Osmani/Vivek/Anthropic/AlphaSignal)
- **Filesystem/Git**: Durable state.
- **Bash/code exec**: General tool.
- **Sandboxes**: Safe exec w/ defaults.
- **Memory/search**: AGENTS.md injection, [[agentic-memory]], MCP.
- **Context rot**: Compaction/offload/progressive skills/resets.
- **Long-horizon**: Ralph Loops/planner-evaluator/sprint contracts.
- **Hooks**: Lint/test/approval enforcement.
- **HaaS**: SDKs (Claude/Codex/[[deep-agents-sdk]]) for loop/tools/config.
- **OpenAI Repo Push**: Strict deps (Types→Config→Repo→Service→Runtime→UI); agent-written linters; CI everywhere.
- **Anthropic Meta-Harness**: Planner→Generator→Evaluator (Playwright); brain/hands/session decoupled.
- **ThoughtWorks Axes**: Guide (pre-act) vs Sensor (post); Computational (fast) vs Inferential (LLM); "harnessability" for stack choice.

## Benchmarks/Evidence
- LangChain GPT-5.2-Codex: Terminal Bench 2.0 52.8%→66.5% (harness only).
- OpenAI Codex: Sora Android #1 Play Store, 99.9% crash-free.
- Anthropic: +10pts structured tasks vs prompting.
- Opus 4.7: SWE-bench 80.8%→87.6%; self-verifies, absorbs harness components.

## Approaches & Limits
| Approach | Strength | Weakness |
|----------|----------|----------|
| OpenAI (Repo Constraints) | Scales to 1M LOC | Greenfield arch weak |
| Anthropic (Multi-Agent) | Quality via eval | 22x costlier |
| ThoughtWorks (Framework) | Audit blueprint | No turnkey tools |

## TRAE Guide (2026-04-23)
"Definitive Guide": Harness Engineering = horse (model) + reins (control). Coined [[mitchell-hashimoto]], R.E.S.T framework. Agent = SOTA Model + Harness = Elite.

## See Also
- [[environment-engineering]] (complement for long-horizon: [[li-jeffrey]]).
- [[agent-harness]]
- [[agentic-memory]]
- [[llm-architecture]]
- [[coding-agents]]
- [[production-agent-runtime]]
- [[deep-agents-sdk]]
- [[agent-harness]]
