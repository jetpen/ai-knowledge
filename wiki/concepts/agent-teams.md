---
title: Agent Teams
created: 2026-04-24
updated: 2026-05-05
type: concept
tags: [agents, multi-agent-systems, claude, collaboration, coordination, google-deepmind]
sources: [raw/articles/suryansh-tiwari-sub-agents-vs-agent-teams-2026-04-24.md, raw/twitter/philipp-schmid-agent-team-post-2026-05-05.md]
author: auto
---

# Agent Teams

Collaborative groups of agents with shared context, real-time communication, and adaptive coordination led by a central agent.

## Characteristics
- **Persistent**: Maintain state across interactions.
- **Interactive**: Agents communicate and adapt dynamically.
- **Context-Sharing**: Shared task layer for progress tracking.
- **Peer-to-Peer Elements**: Via lead agent synthesis.

## Components
- Lead agent: Assigns tasks, synthesizes outputs, steps back awaiting final report (per [[philipp-schmid]]).
- Teammates: Execute specialized roles.
- Shared task layer: Dependency management.
- Tools: Status checks, periodic monitoring.

## Use Cases
- Complex, interdependent workflows (e.g., full-stack development).
- Real-time adaptation and signaling between components.

## Related
- [[sub-agents]] (isolated alternative).
- [[multi-agent-systems]]
- [[deep-agents]] (persistent multi-agent framework).
- [[philipp-schmid]] (2026 post on delegation model)