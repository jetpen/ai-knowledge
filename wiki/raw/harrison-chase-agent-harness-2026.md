---
name: harrison-chase-agent-harnesses-2026
---
# Harrison Chase: The Intimacy of Agent Harnesses and Memory

- **Source**: [https://x.com/hwchase17/status/2042978500567609738](https://x.com/hwchase17/status/2042978500567609738)
- **Author**: Harrison Chase
- **Date**: 2026-04-11

## Summary
The post argues that **agent harnesses**—not standalone memory plugins—are the defining evolution in agent architecture. As models gain native capabilities, scaffolding (the "harness") persists but changes form, and that harness is fundamentally responsible for managing [[agent-memory-architecture|agent memory]].

## Key Concepts
- **Agent Harness**: The systemic scaffolding surrounding an LLM, managing its interactions with tools and data (e.g., `LangGraph`, `Claude Code`, `OpenClaw`).
- **Memory-as-a-Harness Core**: Memory is context, and handling context is a core responsibility of the harness.
    * Short-term memory (conversation state, tool results) is managed by the harness.
    * Long-term memory (cross-session state) is governed by how the harness reads/writes state.
- **Lock-in Risk**: Using proprietary, closed-source harnesses (often tied to proprietary models) results in memory lock-in. Owning the harness = owning the agent's memory.

## Notable Mentions
- **[[Agent Harnesses]]**: Examples include `[[claude-code]]`, `[[deep-agents-cli]]`, `[[openclaw]]`, `[[codex]]`, `[[letta-code]]`.
- **[[agent-harness-architecture]]**: The evolution from simple RAG chains to complex loop-based orchestration.
- Reference to Sarah Wooders: "Memory isn't a plugin, it's the harness."
