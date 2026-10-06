---
title: TOCTOU
---

Time-of-check to time-of-use. A bug where a program checks something (a path, a file, a permission), then acts on it later, and the thing changes in between. The real fix is to act on the object you checked: open the file once and use that handle, or work relative to a directory handle you already hold (`openat`, with `O_NOFOLLOW` to refuse a symlink). Checking again just before use is a mitigation: it shrinks the window but doesn't close it.
