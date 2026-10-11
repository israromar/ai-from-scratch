# Setup: 06 — PyTorch (CPU on Intel Mac)

**Date:** 2026-10-11  
**Lesson:** [Dev Environment](https://aiengineeringfromscratch.com/lesson?path=phases%2F00-setup-and-tooling%2F01-dev-environment&learningPath=software-engineering-fundamentals)  
**Status:** `done`

## Machine

- OS: macOS 15.7.9 (Intel x86_64)
- Venv: `/Users/apple/.venv`
- torch: 2.2.2
- torchvision: 0.17.2
- torchaudio: 2.2.2
- NumPy: 1.26.4 (pinned `<2` for compatibility)

## Commands

```bash
source ~/.venv/bin/activate

# Mac: plain wheels only — do NOT use --index-url .../cuXXX
uv pip install torch torchvision torchaudio

# Required on Intel Mac: latest torch has no x86_64 macOS wheels,
# and torch 2.2.2 was built against NumPy 1.x
uv pip install 'numpy<2'
```

Verify (inside `python` REPL or via `-c`):

```python
import torch
print(f"CUDA available: {torch.cuda.is_available()}")
print(f"MPS available:  {torch.backends.mps.is_available()}")
print(f"torch {torch.__version__}")
```

## Result

```text
NumPy 1.26.4
torch 2.2.2
CUDA available: False
MPS available:  False
tensor sum: 6.0
```

## Gotchas

1. **No CUDA index on Mac.** `--index-url https://download.pytorch.org/whl/cu124` is Linux/Windows only.
2. **No MPS on Intel.** `torch.backends.mps` is Apple Silicon only. Both CUDA and MPS `False` is expected; CPU works.
3. **NumPy 2 vs torch 2.2.2.** Fresh `uv pip install numpy` pulled 2.5.4; importing torch then warned `_ARRAY_API not found` / “compiled using NumPy 1.x”. Fix: `uv pip install 'numpy<2'` → 1.26.4.
4. **Cannot upgrade torch on Intel Mac.** e.g. torch 2.6.0 has wheels for `macosx_*_arm64` but not `macosx_*_x86_64`. Stay on 2.2.2 + NumPy 1.x for this machine.
5. **Restart the REPL** after changing packages (`exit()` then `python` again).

## Related

- Lesson log: [lessons/phase-00-setup-and-tooling/01-dev-environment.md](../lessons/phase-00-setup-and-tooling/01-dev-environment.md)
- Progress: [PROGRESS.md](../PROGRESS.md)
