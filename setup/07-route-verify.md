# Setup: 07 — Route verify

**Date:** 2026-10-11  
**Lesson:** [Dev Environment](https://aiengineeringfromscratch.com/lesson?path=phases%2F00-setup-and-tooling%2F01-dev-environment&learningPath=software-engineering-fundamentals)  
**Status:** `done`

## Machine

- Official course clone: `~/Desktop/work/personal/ai-engineering-from-scratch`  
  (sibling of this journal — not inside it)
- Active Python: `/Users/apple/.venv/bin/python3` (3.12.15)
- Git: 2.56.0 at `/usr/local/bin/git`
- Node (when checked): v22.23.3 via fnm

## Commands

```bash
cd ~/Desktop/work/personal
git clone https://github.com/rohitg00/ai-engineering-from-scratch.git
cd ai-engineering-from-scratch

source ~/.venv/bin/activate

python3 phases/00-setup-and-tooling/01-dev-environment/code/verify.py --route beginner
# also ran: ml-foundations, llm-engineering, agents, mcp, agent-skills, certification
```

## Result

| Route | Required checks | Ready |
|-------|-----------------|-------|
| beginner | 2/2 | yes → `phases/01-math-foundations/01-linear-algebra-intuition/code/vectors.py` |
| ml-foundations | 3/3 (incl. NumPy) | yes → same vectors.py |
| llm-engineering | 2/2 | yes |
| agents | 2/2 | yes |
| mcp | 2/2 | yes |
| agent-skills | 4/4 (+ manual host/scope) | yes |
| certification | 2/2 (+ manual tutor host) | yes |

Beginner preflight excerpt:

```text
Result: 2/2 required checks passed
Ready to start Beginner course.
Next: python3 phases/01-math-foundations/01-linear-algebra-intuition/code/vectors.py
```

## Gotchas

1. **Two repos.** Journal = `ai-from-scratch` (notes/progress). Curriculum = `ai-engineering-from-scratch` (run lessons here).
2. **Activate venv** before `verify.py` so checks use Python 3.12 + NumPy from `~/.venv`.
3. **`--show-later`** inspects optional tools; missing later tools do not block the selected route.
4. **Path note:** learning-path UI “Software Engineering Fundamentals” still uses these same preflight routes (`beginner` / others); there is no separate `--route software-engineering-fundamentals` in the script output we ran.

## Related

- Lesson log: [lessons/phase-00-setup-and-tooling/01-dev-environment.md](../lessons/phase-00-setup-and-tooling/01-dev-environment.md)
- Progress: [PROGRESS.md](../PROGRESS.md)
