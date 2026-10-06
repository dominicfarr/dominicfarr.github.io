---
title: Path traversal
---

An attack that uses a file path such as `../../etc/passwd` to reach files outside the folder a program meant to allow. The fix is to resolve the full path (following `..` and symlinks) and then check it is still inside the allowed folder.
