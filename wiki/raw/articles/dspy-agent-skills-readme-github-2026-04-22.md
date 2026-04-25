---
title: DSPy Agent Skills README
author: intertwine (Bryan Young et al.)
date: 2026-04-21 (latest commit)
source: https://github.com/intertwine/dspy-agent-skills/blob/main/README.md
ingested: 2026-04-22
tags: [dspy, agent-skills, claude-code, codex-cli, coding-agents]
---

# DSPy Agent Skills

Production-grade DSPy 3.2.x skills for coding agents. Pack of 5 spec-compliant skills turning Claude Code/Codex CLI/agentskills.io agents into DSPy experts.

## Skills
| Skill | Trigger |
|-------|---------|
| [[dspy-fundamentals]] | New DSPy code: signatures/modules/Predict/CoT/ReAct/save-load |
| [[dspy-evaluation-harness]] | Metrics/dev-val/Evaluate |
| [[dspy-gepa-optimizer]] | Compiling w/ GEPA |
| [[dspy-rlm-module]] | Long-context QA/RLM |
| [[dspy-advanced-workflow]] | End-to-end orchestration |

## Install
- Claude marketplace: `/plugin marketplace add intertwine/dspy-agent-skills`
- Clone + `./scripts/install.sh`
- Manual symlink to ~/.claude/skills/

## Examples
- 01-rag-qa: Ministral 3B baseline 75% → GEPA 100%
- 02-math: 85% → 93%
- 03-invoice-extraction: 0.83 → 0.93 F1

Grounded in DSPy.ai/docs, validated 80+ tests. MIT license.