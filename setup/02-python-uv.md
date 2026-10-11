# Setup: 02 — Python with uv

**Date:** 2026-10-11  
**Lesson:** [Dev Environment](https://aiengineeringfromscratch.com/lesson?path=phases%2F00-setup-and-tooling%2F01-dev-environment&learningPath=software-engineering-fundamentals)  
**Status:** `done`

## Machine

- OS: macOS 15.7.9 (Intel x86_64)
- `uv`: 0.13.0 → `/Users/apple/.local/bin/uv`
- Python: 3.12.15 (via uv)
- Packages: NumPy 2.5.4, plus matplotlib and jupyter (installed with uv pip)
- Venv location: `/Users/apple/.venv` (created from home directory)

## Commands

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
source ~/.zshrc   # required in the same terminal after install

uv python install 3.12
uv venv
source .venv/bin/activate
uv pip install numpy matplotlib jupyter
```

Verify (Python REPL — do **not** paste this into zsh):

```python
import sys
print(f"Python {sys.version}")

import numpy as np
print(f"NumPy {np.__version__}")
a = np.array([1, 2, 3])
print(f"Vector: {a}, dot product with itself: {np.dot(a, a)}")
```

## Result

```text
Python 3.12.15 (main, Oct  9 2026, 15:10:54) [Clang 22.1.3 ]
NumPy 2.5.4
Vector: [1 2 3], dot product with itself: 14
```

## Gotchas

1. **PATH after install.** Installer puts binaries in `~/.local/bin`. Until you `source ~/.zshrc` (or open a new terminal), `uv` is `command not found` even though install succeeded. `.zshrc` already sources `$HOME/.local/bin/env`.
2. **Python vs shell.** Pasting `import sys` into zsh fails with `command not found: import`. Run `python` first, then paste, or use `python -c '...'`.
3. **Venv created in home.** Commands were run from `~`, so the venv is `~/.venv`, not under this journal. Prefer project dirs next time, e.g. `cd ~/Desktop/work/personal/ai-from-scratch` before `uv venv`. Activate with `source ~/.venv/bin/activate` until a project-local venv exists.
4. **Prompt `(apple)`.** That was an earlier conda/env prompt; after a clean `source ~/.zshrc`, the normal prompt returned with `uv` on PATH.

## Related

- Lesson log: [lessons/phase-00-setup-and-tooling/01-dev-environment.md](../lessons/phase-00-setup-and-tooling/01-dev-environment.md)
- Progress: [PROGRESS.md](../PROGRESS.md)
