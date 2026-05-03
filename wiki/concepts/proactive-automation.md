---
title: Proactive Automation
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["automation", "agents", "concept", "openclaw", "hermes"]
sources: ["raw/articles/openclaw-2026.md", "raw/articles/hermes-agent-readme-2026.md", "raw/articles/symphony-service-spec-2026.md"]
---

# Proactive Automation

Proactive Automation is a behavioral design pattern for AI agents where the agent initiates work autonomously based on internal schedules, external triggers, or recognized needs, rather than waiting for a direct user command.

## Philosophical Core: "AI as Employee"
The move toward proactive automation shifts the user's role from "Interrogator" to "Manager." 
- **Reactive (Old)**: User asks a question; agent provides an answer.
- **Proactive (New)**: Agent monitors project state; agent identifies a bug; agent fixes the bug; agent notifies the user of the result.

## Mechanisms of Proactivity

### 1. Time-Based Triggers
Agents use a built-in **[[agent-cron-scheduler]]** to run recurring tasks unattended.
- **[[openclaw]]**: Historically used for flight check-ins and daily heartbeats.
- **[[hermes-agent]]**: Used for nightly backups, weekly audits, and daily briefings delivered to chat apps—all in natural language.

### 2. Event-Driven Triggers
Agents act in response to system events.
- **[[symphony]]**: Continuously polls issue trackers (like [[linear]]) to find new work, acting as a "daemon" service.
- **Webhook Integration**: Triggering an agent when an error is captured in a platform like Sentry or a PR is opened on GitHub.

### 3. Internal Needs Discovery
Self-improving agents like **[[hermes-agent]]** use their **[[agent-learning-loop]]** to recognize when they should:
- Persist new knowledge into memory without being told.
- Update or create new skills from recent trajectories.
- Perform dialectic user modeling to refine future interactions.

## Critical Support Patterns
- **[[durable-execution]]**: Essential for proactive tasks that must survive service restarts.
- **[[human-in-the-loop]]**: Required to ensure that proactive agents don't perform destructive actions without an approval gate.
- **[[agentic-workspace]]**: Providing the agent with the "hands" (tools and environment) to act proactively.

## Related Concepts
- **[[digital-employee]]**: The role identity of a proactive agent.
- **[[long-running-automation-service]]**: The architectural host for proactive behavior.
- **[[automated-workflows]]**: The complex tasks executed proactively.
