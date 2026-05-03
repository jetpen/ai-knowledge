---
title: Agent Cron Scheduler
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["automation", "scheduling", "concept", "hermes", "openclaw"]
sources: ["raw/articles/hermes-agent-readme-2026.md", "raw/articles/openclaw-2026.md"]
---

# Agent Cron Scheduler

The Agent Cron Scheduler is a proactive automation component that allows AI agents to execute tasks based on time-defined cadences (e.g., daily, weekly, or at specific intervals). Unlike reactive agents that require a user trigger, a scheduled agent initiates work autonomously.

## Evolution and Implementation

### In [[openclaw]]
As one of the core "proactive automation" features of the OpenClaw assistant, the scheduler was designed to help users manage personal workflows.
- **Flight Check-ins**: Automatically checking in for flights at the T-24 hour mark.
- **Inbox Clearing**: Periodic sweeps of email to prioritize or summarize messages.
- **Daily Heartbeats**: Sending status updates to the user via chat apps like WhatsApp or Telegram.

### In [[hermes-agent]]
Building on the OpenClaw foundation, the Hermes Agent cron scheduler unifies proactive automation with a cross-platform gateway.
- **Natural Language Scheduling**: Users can define cadences in plain English (e.g., "Check my email every morning and DM me a summary").
- **Unattended Execution**: Runs reports, nightly backups, and weekly audits entirely in the background.
- **Multi-Platform Delivery**: Results of scheduled tasks can be delivered to CLI, Telegram, Discord, Slack, or Email via a single gateway process.

## Key Capabilities
- **Cross-Session Persistence**: Scheduled tasks survive agent restarts and are often coupled with [[durable-execution]].
- **Context Integration**: Tasks have access to the agent's [[procedural-memory]] and persistent user profile.
- **Loop Integration**: Actions taken during a scheduled run can feed back into the [[agent-learning-loop]] to improve future performance.

## Related Concepts
- **[[proactive-automation]]**: The broader design philosophy of agents acting without a direct human prompt.
- **[[scheduled-tasks]]**: The specific instances of work managed by the scheduler.
- **[[automated-workflows]]**: Complex agent pipelines often triggered by the cron system.
