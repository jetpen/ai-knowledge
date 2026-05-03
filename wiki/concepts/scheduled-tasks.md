---
title: Scheduled Tasks
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["automation", "scheduling", "workflow", "concept", "product"]
sources: ["raw/articles/claude-cowork-2026.md", "raw/articles/hermes-agent-readme-2026.md", "raw/articles/openclaw-2026.md"]
---

# Scheduled Tasks

Scheduled Tasks are specific units of work that an AI agent is configured to perform at a set cadence or specific future time. This is the primary functional output of an **[[agent-cron-scheduler]]**.

## Implementation in [[claude-cowork]]
In Anthropic's Cowork product, scheduled tasks allow users to "Set it once, skip the ask." Users defines the cadence once, and the agent handles the execution autonomously.
- **Reporting**: Pulling metrics from analytics dashboards and dropping them into report templates every Friday.
- **Communications**: Checking email every morning or running a weekly Slack digest to surface priorities.
- **Organization**: Periodic organization of files or folders based on user-defined rules.

## Evolution from [[openclaw]] to [[hermes-agent]]
- **OpenClaw**: Introduced the proactive model for tasks like automatic flight check-ins and "daily heartbeats" to maintain 24/7 presence.
- **Hermes Agent**: Implements natural language scheduling where a user can say "Backup my database every night at 2 AM," and the agent configures the cron job autonomously.

## Key Properties
- **Unattended Execution**: These tasks run in the background without needing an open terminal or active chat session.
- **Multi-Platform Delivery**: Results (briefings, alerts, files) can be delivered to the user's preferred platform (Telegram, Email, etc.) via a messaging gateway.
- **Persistence**: Managed through **[[durable-execution]]** to ensure that tasks are not lost if the agent service restarts.

## Related Concepts
- **[[agent-cron-scheduler]]**: The underlying component that manages the timing of these tasks.
- **[[proactive-automation]]**: The design philosophy that enables scheduled work.
- **[[automated-workflows]]**: The complex series of actions often contained within a single scheduled task.
