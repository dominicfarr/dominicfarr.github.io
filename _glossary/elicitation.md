---
title: Elicitation
---

An MCP feature that lets a server ask the user for structured input in the middle of a tool call (`elicitation/create`). The server sends a message and a JSON schema; the client shows a form and returns the user's answer, or a decline or cancel. The question goes to the client rather than to whatever made the call, so it reaches a person only if the client shows it to one. Nothing in the protocol stops a host from letting its AI model answer.

On MCP 2026-07-28 the question is no longer a mid-call request: it travels inside an `input_required` result, and the answer comes back on the retried call (see [MRTR](/glossary/mrtr/)).
