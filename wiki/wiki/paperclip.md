---
title: Paperclip
created: 2026-04-21
updated: 2026-04-21
type: entity
tags: [framework, agentic-framework, ai-framework, open-source, orchestration, agents, multi-agent, company]
sources: [raw/articles/paperclip-github-repo-2026-04-21.md, raw/articles/paperclip-readme-2026-04-21.md]
author: auto
---

# Paperclip

Open-source orchestration platform for building "zero-human companies" using AI agents.

## Key Facts
- **Repo**: [paperclipai/paperclip](https://github.com/paperclipai/paperclip)
- **Stars**: 56.9k
- **Forks**: 9.8k
- **Commits**: 2,283+ on master (as of 2026-04-21)
- **Activity**: Highly active; recent commits on agent heartbeat scheduling, liveness continuations, API auth hardening, UI Storybook coverage.
- **License**: Open-source (inferred MIT/Apache-style)

## Components
- **Agent Skills**: `.agents/skills/` - Modular agent capabilities.
- **CLI**: Command-line tools with hardened API authorization.
- **Docs/UI**: `.github/`, `doc/` with roadmap, Storybook.
- **Other**: `.claude/skills/`, workflow integrations.

## Relationships
Complements [[symphony-service]], [[hermes-agent]], [[deep-agents]] in agentic orchestration space. Focuses on production-grade agent coordination, monitoring (heartbeats, liveness), and skills composition. Potential integration with [[model-context-protocol]] (MCP) or [[agent-network-protocol]] (ANP) for tool use and communication.

## Status
Rapid development with community contributions (e.g., codex-assisted PRs).
