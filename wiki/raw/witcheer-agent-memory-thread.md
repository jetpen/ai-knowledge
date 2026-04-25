---
name: witcheer-agent-memory-thread-2026
---
# Witcheer: The Two Paradigms of AI Memory Tools

- **Source**: [https://x.com/i/status/2044456778843238689](https://x.com/i/status/2044456778843238689)
- **Author**: witcheer ☯︎
- **Date**: 2026-04-15 (Approx)

## Summary
The thread categorizes 450+ "agent-memory" and 460+ "context-management" GitHub repositories into two fundamental architectural paradigms.

## The Two Camps
1.  **Camp 1: Memory Backends**
    *   **Loop**: Conversation → Extraction/Storage → Vector/Graph DB → Retrieval.
    *   **Focus**: Fact recall, "What should the AI remember?"
    *   **Examples**: `[[mem0]]`, `[[mempalace]]`, `[[supermemory]]`, `[[honcho]]`, `[[cognee]]`, `[[memori]]`.
    *   **Constraint**: Intelligent but opaque; often relies on LLM-based extractions; doesn't evolve well over multi-session contexts.

2.  **Camp 2: Context Substrates**
    *   **Loop**: Continuous human-readable context modification. Nothing is "extracted"; the files are the context.
    *   **Focus**: Multi-session reasoning, "What context should the AI work inside?"
    *   **Examples**: `[[openclaw]]`.
    *   **Mechanism**: Uses structured, human-readable files (markdown) as the storage engine. No hidden state.

## Key Insights
- Camp 1 is best for factual lookup.
- Camp 2 scales better for multi-session, multi-project continuity.
- The industry terminology is still emerging; "memory" is often conflated with "context."
