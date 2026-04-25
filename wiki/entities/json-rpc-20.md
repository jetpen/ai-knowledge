---
title: "JSON-RPC 2.0"
created: 2026-04-19
updated: 2026-04-19
type: protocol
author: auto
tags: ['protocol', 'rpc', 'json-rpc', 'agentic-protocols']
---

# JSON-RPC 2.0

JSON-RPC 2.0 is a stateless, light-weight remote procedure call (RPC) protocol. It is transport agnostic and uses JSON for encoding requests and responses.

## Request Format
```json
{
  \"jsonrpc\": \"2.0\",
  \"method\": \"subtract\",
  \"params\": [42, 23],
  \"id\": 1
}
```

## Response Format
- Success: `{\"jsonrpc\": \"2.0\", \"result\": 19, \"id\": 1}`
- Error: `{\"jsonrpc\": \"2.0\", \"error\": {\"code\": -32600, \"message\": \"Invalid Request\"}, \"id\": 1}`

## Key Features
- Supports notifications (no id).
- Batch requests (array of objects).
- Error codes standardized.

## In Agentic Contexts
Used for inter-agent communication in [[agent-network-protocol]], [[a2a]]. See [[entities-index#Protocols & Standards]].

Sources:
- https://www.jsonrpc.org/specification
