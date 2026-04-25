---
title: Daytona
created: 2026-04-17
updated: 2026-04-17
type: entity
tags: [ai-infrastructure, agentic-framework, compute-and-sandboxing]
sources: [https://www.daytona.io/]
author: auto
---

# Daytona

## Overview
Daytona is an "AI-first" secure infrastructure platform designed to run AI-generated code. It provides fast, stateful, and isolated sandboxes (micro-VMs/containers) that allow developers to execute agent-driven tasks securely in their own cloud or premises.

## Key Facts
- **Core Purpose**: Secure execution of AI-generated code, shell commands, and automation scripts.
- **Performance**: Capable of sub-90ms sandbox creation.
- **Capabilities**:
    - **Compute Isolation**: Sandboxes run in customer-managed environments to ensure compliance (SOC 2, GDPR, HIPAA).
    - **Statefulness**: Supports persistent environments suitable for long-running agents.
    - **Computer Use**: Provides virtual desktop environments (Linux, macOS, Windows) for UI/desktop automation.
    - **Programmatic Control**: Offers APIs for file system access, Git integration, LSP support, and process execution.
- **Accessibility**: Open-source control plane with remote accessibility via SSH, Web terminal, and VS Code integration.

## Relationships
- **Supports**: [Coding Agents](/wiki/entities/coding-agents.md) and autonomous desktop automation systems.
- **Related Technologies**: [Compute and Sandboxing](/wiki/entities/compute-and-sandboxing.md), [E2B](/wiki/entities/e2b.md) (similar goal of secure execution).

## References
- [Daytona Official Website](https://www.daytona.io/)
