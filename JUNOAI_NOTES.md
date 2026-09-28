# JunoAI Notes

## 2026-09-28 — JunoAI
- Added `.github/workflows/node-ci.yml`: reusable CI workflow (checkout, node 20, npm ci, lint/typecheck/test/build each --if-present). (PR: https://github.com/313aidaroos/github-actions/pull/3)
- Why: single shared CI definition for all family repos; callers reference it instead of duplicating workflow files.
