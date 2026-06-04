---
tags:
  - agentic-framework
  - deterministic-control
  - lifecycle-hooks
  - agent-workflow
---

# Agent Hooks

**Agent Hooks** provide a deterministic control mechanism for agent workflows. They allow developers to attach user-defined handlers to specific lifecycle points in an agent session, ensuring compliance with established rules, policies, and workflows without relying on model memory.

## Lifecycle Hooks

1.  **SessionStart**: Initialize session context, such as project conventions, active constraints, environment facts, or a relevant runbook.
2.  **UserPromptSubmit**: Inspect the user prompt before the model receives it. Opportunities include adding context, routing the request, or blocking malicious prompts.
3.  **PreToolUse**: Inspect a tool call before execution. Enforce project policies by blocking, approving, or modifying behavior.
4.  **PostToolUse**: Run validation after a tool call completes. Common tasks include running tests, formatting, scanning, logging, or state capture.
5.  **Stop**: Check whether the agent should be allowed to finish the turn.

## Value Proposition
- **Deterministic Control**: Rules (scripts, tests, policies, runbooks) execute at fixed lifecycle points.
- **Reliability**: Reduces dependence on model inference to "remember" and follow complex instructions.
- **Enforcement**: Enables automated quality gates (e.g., blocking completion if tests fail, verifying tool outputs).

## Links
- [[agentic-infrastructure]]
- [[agent-harness]]
- [[sdlc-automation]]
