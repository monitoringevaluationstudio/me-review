# CLAUDE.md

## What This Repo Is

Public GitHub repo for the **me-review** Claude Code plugin. Published at `monitoringevaluationstudio/me-review`. Contains 6 MEAL review skills + 6 commands. No code, no build step, pure markdown + JSON.

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

Only three fields allowed. Unknown fields break skill registration silently.

```json
{
  "name": "me-review",
  "description": "...",
  "author": {
    "name": "MEStudio",
    "email": "Ben@monitoringevaluationstudio.com"
  }
}
```

No `version`, `displayName`, `repository`, `license`, `keywords`, or `author.url`.

## History Policy

Keep the git history minimal. One clean commit per release is preferred. Squash before pushing if multiple intermediate commits accumulated.
