---
title: Automated Workflows
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["automation", "claude", "workflow", "concept"]
sources: ["raw/articles/claude-cowork-2026.md", "raw/articles/symphony-service-spec-2026.md", "raw/articles/agent-network-protocol-2026.md"]
---

# Automated Workflows

Automated workflows in the agentic era represent the transition from manual, script-based task execution to autonomous, long-running agent processes that handle complex, multi-step operations without constant human intervention.

## Key Characteristics
- **Proactive Execution**: Agents move from reactive chat bots to proactive systems that trigger tasks based on time ([[agent-cron-scheduler]]) or external events ([[automated-workflows]]).
- **Task Planning**: Uses built-in mechanisms for decomposing high-level goals into actionable steps (see [[task-planning]]).
- **Persistence**: Workflows leverage [[durable-execution]] to ensure progress is not lost during transient failures or long-running tasks.

## Implementation Examples
- **[[claude-cowork]]**: Features "Scheduled tasks" for weekly reporting, daily briefings, and automated metric pulls across platforms like Slack and Notion.
- **[[symphony]]**: Implements a "Daemon workflow" that continuously polls issue trackers ([[linear]]) and runs isolated coding sessions in dedicated [[isolated-workspace]] environments.
- **[[agent-network-protocol]]**: Facilitates "Automatic-organization," where agents dynamically negotiate and form networks to complete collaborative tasks.

## Control & Safety
Modern automated workflows typically incorporate [[human-in-the-loop]] approval gates, allowing users to review and refine plans before significant actions are taken.
