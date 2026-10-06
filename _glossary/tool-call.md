---
title: Tool call
---

A request from an MCP client to a server to run one named tool with arguments (`tools/call`). The server does the work and returns a result or an error. In an AI application the model usually chooses the call, which is why the client checks it before sending.
