# CLAUDE.md

## What This Repo Is

Public GitHub repo for the **me-review** Claude Code plugin. Published at `monitoringevaluationstudio/me-review`. Contains 12 MEAL review skills. No separate commands/ directory: each skill carries its own input handling, criteria and output template. No code, no build step, pure markdown + JSON.

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

**Include:** .claude-plugin/plugin.json, .claude-plugin/marketplace.json, LICENSE, README.md, skills/

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
  "version": "1.4.0",
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
community-marketplace review pipeline runs the same check.

## Marketplace Manifest

`.claude-plugin/marketplace.json` makes this repository its own single-plugin marketplace.
That is what lets users install with:

```
/plugin marketplace add monitoringevaluationstudio/me-review
/plugin install me-review@me-review
```

Without it there is no install path at all, because `/plugin marketplace add` reads that
file. The README carried a non-existent `/install-plugin` command from March 2026 until
2026-09-09, so nobody could install the plugin during that period.

Keep the `version` in `marketplace.json` in step with `plugin.json` on every release.

## No commands/ Directory

Each review is one skill under `skills/<name>/SKILL.md`, carrying its own input handling,
review criteria, output template and output rules. A parallel `commands/` directory existed
until 2026-09-09 and was removed: every command shared a name with a skill, which made the
namespace ambiguous, and the current docs say to use `skills/` for new plugins. Slash
invocation is unchanged, still `/me-review:<name>`.

Do not reintroduce `commands/`.

## History Policy

Keep the git history minimal. One clean commit per release is preferred. Squash before pushing if multiple intermediate commits accumulated.
