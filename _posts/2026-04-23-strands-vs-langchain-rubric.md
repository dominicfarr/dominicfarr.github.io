---
layout: post
title: "Strands or LangChain: a simple rubric"
date: 2026-04-23
tags: [agentic, python, tooling]
---

Two Python orchestration tools. Different bets.

LangChain has been the default since 2022. Large ecosystem, integrations for most models and vector stores, active community. If something exists in the LLM space, there is probably a LangChain wrapper for it. That breadth comes with accumulated abstractions — LCEL, LangGraph, chains — and you spend time learning which layer applies before you get to the actual problem.

Strands is AWS's agent SDK, open-sourced in 2025. The model is simpler: tools are Python functions decorated with `@tool`, you point it at a Bedrock model, and the runtime handles the loop. No graph definitions. No chain configuration. A working agent is around twenty lines.

<div style="text-align:center; margin: 2rem 0;">
  <img src="/assets/strands-vs-langchain-rubric.svg" alt="Rubric comparing Strands and LangChain across six dimensions" style="max-width:100%;" />
</div>

The rubric surfaces two clear splits.

Setup speed, agent-first design, and AWS fit all go to Strands. The surface area is small by design. Bedrock is the intended path and it works well if you're already there.

Model flexibility and ecosystem go to LangChain. Dozens of providers, connectors for most databases and retrieval systems, and LangSmith for tracing. If your stack isn't AWS or you need integrations Strands doesn't have, LangChain is the safer choice.

Production simplicity is close. Strands wins on fewer moving parts. LangChain's observability tooling is better, but it adds setup.

The decision reduces to two questions. Are you AWS-native? Do you need integrations Strands doesn't cover?

If neither applies, start with Strands. You can always migrate out when you hit the ceiling.
