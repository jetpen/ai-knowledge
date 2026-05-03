---
title: Frontend Tool Calls
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["agents", "interaction", "ag-ui", "concept", "tools"]
sources: ["raw/articles/ag-ui-protocol-introduction-2026.md"]
---

# Frontend Tool Calls

Frontend Tool Calls (often referred to as client-side tool calls) are a mechanism in the **[[ag-ui]]** (AG-UI) that allows an AI agent to trigger executable actions directly within the user's frontend application, rather than on the agent's backend server.

## Overview
While traditional tool calls happen in the agent's runtime (e.g., querying a database via **[[mcp]]**), frontend tool calls enable the agent to interact with the user's local environment or browser state. This pattern is essential for features that require direct access to client-side APIs, DOM manipulation, or local user data.

## Mechanism
Frontend tool calls follow a typed handoff pattern:
1. **Request**: The agent backend identifies a need for a frontend action and emits a "call" event via the **[[ag-ui]]** protocol.
2. **Execution**: The frontend application intercepts the event, executes the requested logic (e.g., "Navigating to a page", "Opening a locally stored file", or "Playing a notification sound"), and captures the result.
3. **Response**: The result is sent back to the agent backend as a first-class event, allowing the agent to continue its reasoning loop based on the outcome.

## Key Building Blocks
- **Typed Handoffs**: Standardized schemas that define common frontend actions, reducing ad-hoc wiring for application developers.
- **Bi-directional Flow**: Ensures the backend knows if a frontend action succeeded, failed, or was cancelled by the user.
- ****Agent Steering****: Allows the user to provide real-time input during the execution of a frontend tool.

## Use Case Examples
- **Navigation**: Redirecting the user to a specific dashboard or settings page.
- **LocalStorage Access**: Reading or writing persistent user preferences stored in the browser.
- **Local App Integration**: Triggering actions in software running on the user's machine that doesn't have a public API.

## Related Concepts
- **[[ag-ui]]**: The protocol that provides the infrastructure for these calls.
- **[[generative-ui-specification]]**: While frontend tool calls perform *actions*, Generative UI delivers *components*.
- ****Interrupts****: Often used to gate risky or significant frontend tool calls with human approval.
