# Workflow (for this journal)

Rules for how I (and the agent helping me) update this repo.

## Commit cadence

One commit per finished milestone:

- A completed setup step under `setup/`
- A completed lesson (or a clear mid-lesson checkpoint)
- A meaningful exercise under `code/`

Do not batch unrelated lessons into one commit.

## Commit message style

```text
docs(setup): system foundation
docs(lesson): complete 00-01 verify beginner
feat(code): python hello world for phase 00
chore: update progress after uv install
```

Prefer `docs` for journal/setup logs, `feat`/`fix` for code under `code/`, `chore` for progress-only tweaks.

## Checklist before each commit

1. Lesson or setup note updated with commands and verify output
2. `PROGRESS.md` status ticks match reality
3. No secrets (`.env`, API keys, tokens) staged
4. Links to the official course lesson still correct

## GitHub

- Public repo
- Push after a commit when the milestone is worth sharing
- Default branch: `main`
