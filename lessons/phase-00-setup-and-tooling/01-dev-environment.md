# Lesson: [Phase 00] Dev Environment

**Path:** Software Engineering Fundamentals  
**Official:** https://aiengineeringfromscratch.com/lesson?path=phases%2F00-setup-and-tooling%2F01-dev-environment&learningPath=software-engineering-fundamentals  
**Status:** `done`  
**Started:** 2026-10-11  
**Finished:** 2026-10-11

## Goal

Set up the four-layer AI engineering stack (system → packages → runtimes → AI libraries) so later lessons do not fight tooling. Languages in this lesson: Python, Node.js, Rust (Julia optional).

## What I did

- [x] Step 1 — System Foundation (`git`, `curl`, `wget` via Homebrew)
- [x] Step 2 — Python with `uv` (3.12.15; NumPy later pinned for torch)
- [x] Step 3 — Node.js with `fnm` + `pnpm` (Node v22.23.3, pnpm 11.2.2)
- [x] Step 4 — Rust (`rustc`/`cargo` 1.99.0)
- [x] Step 5 — Julia 1.13.1 (optional)
- [x] Step 6 — PyTorch 2.2.2 + NumPy 1.26.4 (CPU; CUDA/MPS false on Intel)
- [x] Step 7 — Route verify (all listed routes passed)

## Commands

Steps 1–6: see `setup/01` … `setup/06`.

Step 7 (done):

```bash
cd ~/Desktop/work/personal
git clone https://github.com/rohitg00/ai-engineering-from-scratch.git
cd ai-engineering-from-scratch
source ~/.venv/bin/activate

python3 phases/00-setup-and-tooling/01-dev-environment/code/verify.py --route beginner
# also: ml-foundations, llm-engineering, agents, mcp, agent-skills, certification
```

Full notes: [setup/07-route-verify.md](../../setup/07-route-verify.md).

## Verify

Step 7 (beginner):

```text
Result: 2/2 required checks passed
Ready to start Beginner course.
Next: python3 phases/01-math-foundations/01-linear-algebra-intuition/code/vectors.py
```

All other routes run in the same session also passed their required checks (see setup/07).

## Notes / blockers

- Two repos: journal `ai-from-scratch` vs curriculum `ai-engineering-from-scratch`.
- Intel Mac tooling gotchas documented across setup/01–06 (Homebrew source builds, keg-only curl, NumPy pin for torch, skip arm64 fnm block).
- Venv at `~/.venv`; activate before course scripts.

## Artifacts

- Setup: [01](../../setup/01-system-foundation.md) … [07](../../setup/07-route-verify.md)
- Code: (none yet)

## Next

1. Phase 00 next lesson: Git & Collaboration (official course)
2. Or begin Math foundations: `python3 phases/01-math-foundations/01-linear-algebra-intuition/code/vectors.py` from the curriculum clone
