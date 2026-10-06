---
layout: post
title: "MCP Security"
date: 2026-10-01
tags: [agentic, tooling, security]
---

[MCP](/glossary/mcp/) gives an AI application a standard way to call tools on other programs. Read a file, write a file, run a query. That is useful, and it is also the attack surface: every [tool call](/glossary/tool-call/) is something happening on someone's machine because a model, or a server, or a web page the model read, asked for it.

The question I wanted answered is simple. When an MCP tool call is about to happen, who gets to stop it, and where is that code?

<div style="text-align:center; margin: 2rem 0;">
  <img src="/assets/mcp-security.svg" alt="MCP Security through Client Policies and Server Elicitation" style="max-width:100%;" />
</div>

## The reference implementation

I built a small [reference repo](https://github.com/dominicfarr/mcp-secuirty-working-notes-example) to find out. One [MCP client](/glossary/mcp-client/), one [MCP server](/glossary/mcp-server/), four tools (three of them on files), connected over the [stdio transport](/glossary/stdio-transport/). A Gradio app shows each request, the client's decision, the server's questions and both [audit logs](/glossary/audit-log/).

There is no LLM in it yet. That is deliberate. The controls in this series are deterministic: they hold whoever makes the request, a person clicking a button or a model that has been [prompt-injected](/glossary/prompt-injection/). If a control only works when the model behaves, it isn't a control. Putting a model in the loop is the next part of the repo, and its own series.

Every claim in these posts links to the code or the test that backs it, pinned to one commit so the line numbers stay right.

## The series

1. [Allow, ask, deny: the client decides]({% post_url 2026-10-02-mcp-security-client-permissions %}). Per-tool policy, and an approval that can't be redirected.
2. [Roots are a request, not a wall]({% post_url 2026-10-03-mcp-security-roots %}). What the client can declare, and why only the server can enforce it.
3. [Ask the human, not the caller]({% post_url 2026-10-04-mcp-security-elicitation %}). Elicitation: the server asking the user mid-call.
4. [One delete, every check]({% post_url 2026-10-05-mcp-security-delete-end-to-end %}). One `delete_file` traced through every layer.
5. [Proving it: tests as the security spec]({% post_url 2026-10-06-mcp-security-proving-it %}). Tests named as guarantees, and how they run.

## Run it

```bash
python3 -m venv mcp_security_env && source mcp_security_env/bin/activate
pip install -r requirements-dev.txt
python3 client/app.py server/server.py
```

Open the local URL it prints. Set `delete_file` to `ask` on the Permissions tab, then try deleting something.
