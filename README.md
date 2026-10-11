# AI From Scratch — Learning Journal

Personal journal for upskilling with [AI Engineering from Scratch](https://aiengineeringfromscratch.com/).

This is **not** a fork of the curriculum. Official lessons stay upstream; this repo tracks what I set up, what I learned, and the code I write.

## Path

**Software Engineering Fundamentals**

Course: https://aiengineeringfromscratch.com/  
Current lesson: [Dev Environment](https://aiengineeringfromscratch.com/lesson?path=phases%2F00-setup-and-tooling%2F01-dev-environment&learningPath=software-engineering-fundamentals)

## How this repo works

| Folder | Purpose |
|--------|---------|
| `PROGRESS.md` | Single checklist — current lesson and status |
| `setup/` | Environment milestones (Homebrew, uv, Node, etc.) |
| `lessons/` | Per-lesson logs linked to the official course |
| `notes/` | Freeform concept notes |
| `code/` | Exercises and hello-worlds |
| `templates/` | Copy these when starting a new lesson or setup step |

## Workflow

1. Do the work in the official lesson.
2. Update the lesson log under `lessons/` and any `setup/` note.
3. Tick `PROGRESS.md`.
4. Put runnable artifacts in `code/` when relevant.
5. Commit once per finished step (see `CONTRIBUTING.md`).
6. Push to GitHub.

## Machine notes

- macOS 15.7.9 (Intel x86_64)
- Homebrew at `/usr/local` (source builds; no bottles for Intel)
- System `curl` stays on PATH; Homebrew `curl` is keg-only
