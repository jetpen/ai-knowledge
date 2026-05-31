---
title: "Pi Coding Agent"
author: "Ben Eng"
date: 2026-05-31
tags: ["concept", "harness", "agent"]
sources: ["https://pi.dev"]
---

# Pi Coding Agent

**Pi** is a minimal, highly extensible terminal-based coding harness designed to adapt to user workflows rather than forcing users into a rigid structure. It prioritizes "primitives over features," allowing users to build or install custom functionality via extensions, skills, and prompt templates.

## Core Philosophy
Pi is not a "sealed product." It intentionally omits common agent features (like built-in plan mode or sub-agents) in favor of a modular architecture where users can build or install exactly what they need.

*   **Extensibility**: Customize via TypeScript-based extensions, skills, prompt templates, and themes.
*   **Package Management**: Bundle customizations and share them via npm or git.
    *   `$ pi install npm:@foo/pi-tools`
    *   `$ pi install git:github.com/badlogic/pi-doom`
*   **Context Engineering**: Uses a minimal system prompt and supports `AGENTS.md` (project instructions) and `SYSTEM.md` (custom system prompts) to manage the context window effectively.

## Key Capabilities
*   **Model Flexibility**: Supports 15+ providers (Anthropic, OpenAI, etc.) with mid-session switching.
*   **Session Management**: Tree-structured history (branch/continue) and session sharing (HTML/Gists).
*   **Operational Modes**: TUI, Print/JSON (for scripting), RPC (stdin/stdout), and SDK.
*   **Context Management**: Auto-compaction, on-demand skill loading, and dynamic RAG injection via extensions.

## Position as Harness
Pi is an example of the "minimal/bottom-up" agent harness philosophy. It avoids "baked-in" features like integrated MCP, sub-agent logic, or permission UIs, pushing these to the user level (e.g., via extensions, shell-level `tmux` usage, or containers).
