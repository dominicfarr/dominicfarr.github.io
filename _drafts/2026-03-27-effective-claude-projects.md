---
layout: post
title: "Effective use of LLM models"
date: 2026-03-27
tags: [claude]
---

[Draft post, needs expanding with better example and references. Check for accuracy. Flow and goal seems weak]

When I speak with local businesses or vibe coders, and ask them how they use the AI, many still use it in chat forum. Copying code

Most LLMs greets everyone with a friendly welcome and asked, "How can I help you today?" They start chating on a topic they need, back and forth until a solution or answer is good enough. It's great for quick tasks like recipes or explaining something.

For more complex goals [add an example] this chat loop has limits and can quickly become ineffective. [find reference] The length of these back and forth conversations can get very long, and the quality starts to degrade, leading to longer conversations, which degrades the quality further. The Context[link to glossary] rots[^1] will start to degrade the outputs. [Connect these sentenses] Each chat is independant, and prior understanding isn't automatically available. This is where Projects, Skills, Plugins, and Connectors [link each to glossary] can really make the difference.

Projects create a specialized workspace with a persistent context for each new chat within the project. Project have instructions[glossary] and associated files [give examples].

Skills [expand with examples]

Plugins [expand ith examples]

Connectors [expand with examples]

[^1]: [Context rot]({% link _glossary/context-rot.md %}) — degradation of output quality as context length grows.
