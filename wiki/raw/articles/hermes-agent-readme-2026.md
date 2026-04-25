# Hermes Agent
**The self-improving AI agent built by Nous Research.**

Hermes is an AI agent with a built-in learning loop—it creates and improves skills from experience, persists knowledge, searches past conversations, and builds a deepening model of the user. It is platform-agnostic, supporting CLI, Telegram, Discord, Slack, WhatsApp, Signal, and Email.

## Core Features
- **Learning Loop**: Agent-curated memory, autonomous skill creation, and self-improving skills.
- **Platform Agnostic**: CLI, Telegram, Discord, Slack, WhatsApp, Signal, Email.
- **Scheduled Automations**: Built-in cron scheduler for unattended tasks (reports, backups, audits).
- **Delegation/Parallelization**: Spawns isolated subagents for parallel workstreams.
- **Memory**: Persistent memory, user profiles, FTS5 session search.
- **Runtime Persistence**: Run on $5 VPS, GPU clusters, or serverless with hibernation (Daytona/Modal).

## Key Components
- **CLI**: Terminal TUI with slash-commands, history, and streaming tool output.
- **Messaging Gateway**: Single process for messaging platforms and voice memo transcription.
- **Skills System**: Procedural memory built on `agentskills.io` standard.
- **Tools**: 40+ built-in tools, supports MCP servers.

## Documentation
- Website: https://hermes-agent.nousresearch.com/docs/
- GitHub: https://github.com/NousResearch/hermes-agent
