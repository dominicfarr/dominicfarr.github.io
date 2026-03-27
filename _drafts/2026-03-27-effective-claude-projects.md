---
layout: post
title: "Effective use of Claude Projects"
date: 2026-03-27
tags: [claude]
---

When I work with local businesses, and we review their usage LLMs like Claude or ChatGPT I see a common pattern. A back and forth chat with the service.

Most LLMs greets everyone with a friendly welcome and asked, "How can I help you today?" They start chating on a topic they need, back and forth until a solution or answer is good enough. It's great for quick tasks like recipes or explaining something.

For more complex goals this chat loop has limits and can quickly become ineffective. Depending on the length of these back and forth, context rot[^1] will start to degrade the outputs. Each chat is independant, and prior understanding isn't automatically available. This is where Projects can really make the difference. Projects create a specialized workspace for your task.

Projects create a specialized workspace with a persistent context for each new chat within the project. This persisten context is created using, Project instructions and associated files.

[^1]: [Context rot]({% link _glossary/context-rot.md %}) — degradation of output quality as context length grows.
