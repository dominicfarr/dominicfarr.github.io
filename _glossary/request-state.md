---
title: Request state
---

The opaque string an [MRTR](/glossary/mrtr/) server hands the client between rounds and gets back on the retry. It passes through the client, so the server must treat it as attacker-controlled and protect its integrity, and should bind it to the user, the request and an expiry. fastmcp also encrypts it. The client must echo it back exactly, without reading or changing it.
