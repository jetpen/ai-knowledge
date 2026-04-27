---
title: Zed
type: entity
created: 2026-04-27
updated: 2026-04-27
tags: [code-editor, multiplayer-editor, rust, acp, model-context-protocol, llm-integration, agent-panel, parallel-agents]
sources:
  - https://zed.dev/
  - https://zed.dev/blog
  - https://zed.dev/docs
---

# Zed

High-performance, multiplayer code editor built from scratch in Rust for speed, collaboration with humans and AI agents. Supports macOS, Linux, Windows. Creators of Atom and Tree-sitter.

## Key Features
- **Fast**: Leverages multiple CPU cores and GPU for native performance.
- **Collaborative**: Real-time chat, screen/project sharing, channels, private calls.
- **Intelligent**: Deep AI integrations including Agent Panel, Inline Assistant, Edit Prediction (Zeta/Zeta2 models), Rules.

## AI & Agent Integrations
- **Agent Panel**: Run agents with tools, permissions; supports external agents.
- **Parallel Agents**: Execute multiple agents simultaneously in one window (Apr 2026 launch).
- **Model Context Protocol (MCP/ACP)**: Standardized protocol for LLM/editor interactions.
- **Inline Assistant & Edit Prediction**: Autocomplete/transform code via LLMs.
- **Agent Metrics**: Public dashboards tracking AI usage/turn times.

## Architecture
- Rust core (GPUI for UI).
- Cloud sync for collaboration.
- LSP support, Git integration, multibuffers, terminal/tasks/debugger.
- Extensible: Vim/Helix modes, themes, keybindings.

## Relationships
- **Protocols**: [[model-context-protocol]], [[acp]].
- **Frameworks**: Integrates [[deep-agents-sdk]], [[composio]].
- **Concepts**: [[agentic-infrastructure]], [[shared-state]], [[parallel-agents]].

## Source Context
Synthesized from zed.dev (overview/features), blog (Parallel Agents Apr 22 2026, Agent Metrics Apr 9, Zeta2 Apr 7), docs (AI/collaboration sections). Recent activity: PRs for GPUI AccessKit, LSP hovers, cloud billing (Rust/JS stacks).
