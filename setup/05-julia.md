# Setup: 05 — Julia (optional)

**Date:** 2026-10-11  
**Lesson:** [Dev Environment](https://aiengineeringfromscratch.com/lesson?path=phases%2F00-setup-and-tooling%2F01-dev-environment&learningPath=software-engineering-fundamentals)  
**Status:** `done`

## Machine

- OS: macOS 15.7.9 (Intel x86_64)
- Julia: 1.13.1

## Commands

```bash
# if not already installed:
# curl -fsSL https://install.julialang.org | sh

julia -e 'println("Julia ", VERSION)'
```

## Result

```text
Julia 1.13.1
```

## Gotchas

- Optional for the Software Engineering Fundamentals path; useful later for math-heavy Phase 1 lessons.
- If `julia` is missing in a new terminal, ensure juliaup/PATH from the installer is loaded (`source ~/.zshrc`).

## Related

- Lesson log: [lessons/phase-00-setup-and-tooling/01-dev-environment.md](../lessons/phase-00-setup-and-tooling/01-dev-environment.md)
- Progress: [PROGRESS.md](../PROGRESS.md)
