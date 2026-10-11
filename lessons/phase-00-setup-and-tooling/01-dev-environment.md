# Lesson: [Phase 00] Dev Environment

**Path:** Software Engineering Fundamentals  
**Official:** https://aiengineeringfromscratch.com/lesson?path=phases%2F00-setup-and-tooling%2F01-dev-environment&learningPath=software-engineering-fundamentals  
**Status:** `doing`  
**Started:** 2026-10-11  
**Finished:** —

## Goal

Set up the four-layer AI engineering stack (system → packages → runtimes → AI libraries) so later lessons do not fight tooling. Languages in this lesson: Python, Node.js, Rust (Julia optional).

## What I did

- [x] Step 1 — System Foundation (`git`, `curl`, `wget` via Homebrew)
- [x] Step 2 — Python with `uv` (3.12.15, NumPy 2.5.4)
- [ ] Step 3 — Node.js with `pnpm` (via `fnm`)
- [ ] Step 4 — Rust (`rustup`)
- [ ] Step 5 — Julia (optional)
- [ ] Step 6 — GPU / PyTorch (MPS notes for Apple; CPU OK if no GPU)
- [ ] Step 7 — Route verify (`verify.py --route …`) — needs the official course repo cloned separately when we get there

## Commands

Step 1 (done): see [setup/01-system-foundation.md](../../setup/01-system-foundation.md).

Step 2 (done):

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
source ~/.zshrc
uv python install 3.12
uv venv
source .venv/bin/activate
uv pip install numpy matplotlib jupyter
python   # then paste the verify snippet inside the REPL
```

Full notes: [setup/02-python-uv.md](../../setup/02-python-uv.md).

## Verify

Step 1:

```text
git version 2.56.0
curl 8.7.1 (x86_64-apple-darwin24.0) ...   # system curl; Homebrew curl is keg-only
GNU Wget 1.25.0 built on darwin24.6.0.
```

Step 2:

```text
Python 3.12.15 (main, Oct  9 2026, 15:10:54) [Clang 22.1.3 ]
NumPy 2.5.4
Vector: [1 2 3], dot product with itself: 14
```

## Notes / blockers

- Working on Intel macOS; Homebrew source builds make Step 1 slow but succeeded.
- Step 2 venv landed in `~/.venv` because commands ran from home; activate with `source ~/.venv/bin/activate`. Prefer project-local venvs later.
- Do not paste Python into zsh — enter `python` first.
- Step 7 assumes the official curriculum repo (with `phases/…/verify.py`). This journal does not clone it; clone that repo separately when ready to run the preflight.

## Artifacts

- Setup: [setup/01-system-foundation.md](../../setup/01-system-foundation.md), [setup/02-python-uv.md](../../setup/02-python-uv.md)
- Code: (none yet)

## Next

1. Step 3 — Node.js with `fnm` + `pnpm`
2. Continue Steps 4–7
3. Update this log + `PROGRESS.md` after each step; commit once per step
