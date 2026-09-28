# JunoAI Notes

## 2026-09-28 — Shared CI repo created
Created public repo `313aidaroos/github-actions` ("Shared reusable GitHub Actions
workflows for the Apixis family") so all family repos consume one reusable CI
definition instead of copy-pasting workflow files. Added `node-ci.yml` and
`python-ci.yml` reusable workflows (`workflow_call`) plus a README with consumption
instructions. Branch: `junoai/setup`. Why: 17 of 20 family repos had zero CI; shared
callers fix that without duplicates.
