# CLAUDE.md

## What This Repo Is

Public GitHub repo for the **me-review** Claude Code plugin. Published at `monitoringevaluationstudio/me-review`. Contains 12 MEAL review skills + 12 commands. No code, no build step, pure markdown + JSON.

## Git Identity (CRITICAL)

This repo belongs to the **monitoringevaluationstudio** GitHub account, NOT Logic-Lab-HQ.

**Local git config (already set):**
- `user.name` = `MEStudio`
- `user.email` = `Ben@monitoringevaluationstudio.com`

**SSH remote:** `git@github.com-mestudio:monitoringevaluationstudio/me-review.git`

**Rules:**
- NEVER add `Co-Authored-By` lines to commits. No AI attribution, ever.
- NEVER use the global git identity (Logic-Lab-HQ). The local config overrides it.
- Commit author must always be `MEStudio <Ben@monitoringevaluationstudio.com>`.
- Push only via SSH using the mestudio key (`~/.ssh/id_ed25519_mestudio`).
- Only push when Ben explicitly asks.

## What to Commit

**Include:** plugin.json, LICENSE, README.md, skills/, commands/

**Never commit:** test files, session summaries, dev docs (EXECUTION-CHECKLIST, INTEGRATION-STATUS, TEST-GUIDE, TEST-RESULTS, test-inputs/, SESSION-SUMMARY-*, etc.)

## Plugin.json Schema

**Corrected 2026-09-09.** This section previously said only three fields were allowed and
that unknown fields "break skill registration silently." That was wrong. The live spec at
`code.claude.com/docs/en/plugins-reference` states: "Claude Code ignores top-level fields it
does not recognize... A plugin with only unrecognized-field warnings still passes validation
and loads at runtime." Verified against `claude plugin validate` on v2.1.251.

`name` is the only required field. Everything below is optional and supported:

```json
{
  "name": "me-review",
  "displayName": "M&E Review",
  "version": "1.3.0",
  "description": "...",
  "author": { "name": "MEStudio", "email": "...", "url": "..." },
  "homepage": "https://www.monitoringevaluationstudio.com/plugins",
  "repository": "https://github.com/monitoringevaluationstudio/me-review",
  "license": "MIT",
  "keywords": ["monitoring-evaluation", "meal", "..."]
}
```

`homepage` matters: plugin directories and marketplaces build their listings from this
manifest, and without it a listing carries no link back to the site.

Bump `version` on every release. Users only receive updates when it changes.

Run `claude plugin validate .` before any push. Warnings do not fail validation; the
community-marketplace review pipeline runs the same check. Two warnings are expected and
accepted: none currently, once `version` is set, apart from the `CLAUDE.md at the plugin
root` notice, which is this file and is intentional.

## History Policy

Keep the git history minimal. One clean commit per release is preferred. Squash before pushing if multiple intermediate commits accumulated.
