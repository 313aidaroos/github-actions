# Claude notes (github-actions)

Dated notes from Claude (Claude Code): what Claude checked or changed here, what it found, what is still open. The one family status board is `ApixisWallet/docs/FAMILY_STATUS.md`.

## 2026-10-04 (UTC) — Claude: full-portfolio review (read-only; this note and the AI_CHANGELOG line are the only changes)

- `main` @ `b15d421`: one reusable workflow, `node-ci.yml` (Node 22; `npm ci`; `lint` / `typecheck` / `test` / `build`, each `--if-present`). Called by 12 family repos; ApixisWallet, Rawixis, Socixis, Pinixis, AwadBot (dashboard) and Geoxis run their own copies.
- Gap: `--if-present` lets a repo with no `test` or `typecheck` script pass with nothing run. Today that is Deduxis (2 test files, no script), Halaxis (no tests), Nursery Toons (no `package.json` at all), and `typecheck` is absent on Launchixis and Apixis.dev (JS projects — fine).
- Not covered: pnpm (awad-command has no CI at all) and Python (AwadBot's bot is tested by its own `trading.yml`).

### Open — Claude can do on your go
- Add a guard step that fails when both `test` and `typecheck` are missing (or prints a loud warning), a `pnpm` variant, and a Python variant.
