---
title: Roots
---

Folders (as `file://` URIs) that an MCP client tells a server it may work in. Roots are advisory: the client declares them, and only the server's own code can enforce them. A well-behaved server narrows its access to them; a malicious one ignores them.

Roots are deprecated as of MCP 2026-07-28 (SEP-2577); servers take the folders they may use from their own configuration instead.
