---
title: Multi round-trip requests (MRTR)
---

How an MCP server asks the client for input on protocol 2026-07-28. Instead of sending a request mid-call and waiting, the server ends the call with an `input_required` result holding its questions and an opaque [request state](/glossary/request-state/). The client gets the answers and sends the call again, as a new request, with the answers and the state unchanged. No request stays open while a person thinks.
