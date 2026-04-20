---
layout: post
title: "Stop Thinking About Python Tooling"
date: 2026-04-20
tags: [python, tooling, automation]
---

Good Python repos in 2026 run [ruff](https://docs.astral.sh/ruff/), [pyright](https://github.com/microsoft/pyright), and [uv](https://docs.astral.sh/uv/). Ruff handles linting and formatting, replacing flake8, black, and isort in one tool. Pyright does static type checking. uv replaces pip and virtualenv and is fast enough that you stop noticing it.

Most teams already know these exist. The issue is remembering to run them.

<div style="text-align:center; margin: 2rem 0;">
  <img src="/assets/git-commit-pre-commit.svg" alt="Git pre-commit hook flow" style="max-width:100%;" />
</div>

A pre-commit hook fires on `git commit`, before anything is recorded. Failed check, commit stops. Style problems surface in your working directory rather than CI.

Drop this into `.git/hooks/pre-commit`:

```bash
#!/bin/sh
set -e
uv run ruff check . --fix
uv run ruff format .
uv run pyright
```

`set -e` exits on the first failure. `--fix` lets ruff correct what it can automatically. Make it executable:

```bash
chmod +x .git/hooks/pre-commit
```

For shared repos, version-control the hooks using [pre-commit](https://pre-commit.com/) and a `.pre-commit-config.yaml`. Then everyone runs the same checks on every commit without a manual setup step.

```yaml
repos:
  - repo: https://github.com/astral-sh/ruff-pre-commit
    rev: v0.9.0
    hooks:
      - id: ruff
        args: [--fix]
      - id: ruff-format
  - repo: https://github.com/RobertCraigie/pyright-python
    rev: v1.1.390
    hooks:
      - id: pyright
```

Run `pre-commit install` once per clone.

The checks run when the commit runs. You stop scheduling them.
