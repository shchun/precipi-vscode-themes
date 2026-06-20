# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A VS Code **color theme extension** — no application source code, no tests, no lint/build step. The "code" is a set of theme definition files plus the extension manifest. Published to the VS Code Marketplace as `precipi.precipi-themes`.

## Commands

```bash
npm run package      # build the .vsix (vsce package --allow-missing-repository)
npm run deploy       # build .vsix, then uninstall + reinstall locally via the `code` CLI
node scripts/deploy.mjs --no-package   # reinstall an existing .vsix without rebuilding
```

`scripts/deploy.mjs` is the cross-platform (Windows/macOS/Linux) build+install driver used by both npm scripts. It locates the `code` CLI; if not on PATH it builds the `.vsix` and skips the install steps.

### Publishing (Marketplace)

Two paths, both manual — publishing never happens automatically on push:

- **GitHub Actions (preferred):** Actions tab → "Publish to Marketplace" → Run workflow → pick the version bump. Defined in `.github/workflows/publish.yml` (`workflow_dispatch` only). Uses the `VSCE_PAT` repo secret and pushes the version-bump commit/tag back.
- **Local:** load `VSCE_PAT` from `.env`, then `vsce publish patch --no-dependencies -p "$VSCE_PAT"`.

The Marketplace rejects re-publishing the same version, so every publish must bump `version` in `package.json` (`patch`/`minor`/`major`).

## Theme architecture

6 themes = **3 color families** (Synthwave / Solar / Emerald) × **light + dark**. Each family's dark variant is the dark-mode counterpart of its light variant, sharing the same accent hues.

Each theme is a single file `themes/precipi-{name}-color-theme.json`, written as **JSONC (comments allowed)** — do not parse these with `JSON.parse`/`require`. Structure:
- `name`, `type` (`"dark"` | `"light"`)
- `colors` — workbench UI colors (editor, activity bar, gutter, etc.)
- `tokenColors` — TextMate syntax highlighting scopes

## Adding or renaming a theme

A theme requires **two coordinated edits** — the loose file alone does nothing:
1. Add/rename `themes/precipi-{name}-color-theme.json`.
2. Add/update the matching entry in `contributes.themes` in `package.json`, where `label` is the user-facing theme name, `uiTheme` is `vs` (light) or `vs-dark` (dark), and `path` points at the file.

The `label` in `package.json` is what users select and what the README's auto-switch settings reference — keep them consistent.

## Secrets

`VSCE_PAT` (Azure DevOps Personal Access Token, scope Marketplace › Manage) lives in `.env` locally and as a GitHub Actions secret. `.env` is gitignored and excluded from the package via `.vscodeignore`; `.env.example` is the template.
