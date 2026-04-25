---
title: Conversation Compaction
created: 2026-04-12
updated: 2026-04-12
type: concept
tags: ["memory", "token-optimization", "concept", "deepagents"]
sources: ["raw/articles/deepagents-api-ref-2026.md"]
---

# Conversation Compaction

Conversation Compaction is a memory management technique used to maintain long-running agent sessions by reducing the size of the message history. This prevents the agent from exceeding the model's context window limits and optimizes token usage.

## Mechanisms in Deep Agents
Within the **[[deep-agents-sdk]]**, compaction is handled via specialized middleware:

- **SummarizationMiddleware**: Automatically compresses older parts of the conversation into high-level summaries while preserving the most recent context.
- **Compact_conversation Tool**: A manual tool that allows the agent or the system prompt to trigger a compaction event proactively.
- **TruncateArgsSettings**: Configures the system to truncate large tool-call arguments in historical messages to save space without losing the narrative flow of the conversation.

## Operational Logic
1. **Event Selection**: The system identifies messages or tool outputs that are older than a specific threshold or that exceed a token count.
2. **Summarization**: An LLM is used to generate a concise summary of the selected messages (see ****SummarizationEvent****).
3. **State Update**: The original detailed messages are replaced by the summary in the ****MemoryState****, freeing up context for new inputs.

## Benefits
- **Sustainability**: Enables truly long-term sessions spanning hundreds of turns.
- **Cost Efficiency**: Reduces the number of input tokens sent to the LLM in each turn.
- **Focus**: Keeps the "active" context window focused on relevant, recent information while maintaining a "lossy" long-term memory.

## Related Concepts
- **[[durable-execution]]**: Ensures that the compacted state is persisted across interruptions.
- **[[procedural-memory]]**: Complements compaction by storing specific learned skills outside the active chat context.
