# github-actions

Shared reusable GitHub Actions workflows for the Apixis family. One source of
truth for CI — no copy-pasted workflow files across repos.

## Available workflows

- `.github/workflows/node-ci.yml` — Node.js: checkout, setup-node 20 (npm cache),
  `npm ci`, `npm run build --if-present`, `npm test --if-present`. Skips gracefully
  when the repo has no `package.json`.
- `.github/workflows/python-ci.yml` — Python: checkout, setup-python 3.12,
  `pip install -r requirements.txt` (if present), `compileall`, `pytest` (if tests exist).

## How a repo consumes them

Add `.github/workflows/ci.yml` in the repo:

```yaml
name: CI

on:
  push:
    branches: [main]
  pull_request:

jobs:
  ci:
    uses: 313aidaroos/github-actions/.github/workflows/node-ci.yml@main
```

Use `python-ci.yml@main` for Python repos. Merge this repo's setup PR first, then the
caller lights up on the next push.
