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
- [x] Step 3 — Node.js with `fnm` + `pnpm` (Node v22.23.3, pnpm 11.2.2)
- [x] Step 4 — Rust (`rustc`/`cargo` 1.99.0)
- [x] Step 5 — Julia 1.13.1 (optional)
- [x] Step 6 — PyTorch 2.2.2 + NumPy 1.26.4 (CPU; CUDA/MPS false on Intel)
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

Step 3 (done):

```bash
curl -fsSL https://fnm.vercel.app/install | bash
source ~/.zshrc
fnm use 22
node -e "console.log('Node', process.version)"
pnpm -v
```

Full notes: [setup/03-nodejs-fnm-pnpm.md](../../setup/03-nodejs-fnm-pnpm.md).

Step 4 (done):

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source ~/.cargo/env
rustc --version
cargo --version
```

Full notes: [setup/04-rust.md](../../setup/04-rust.md).

Step 5 (done):

```bash
julia -e 'println("Julia ", VERSION)'
```

Full notes: [setup/05-julia.md](../../setup/05-julia.md).

Step 6 (done):

```bash
source ~/.venv/bin/activate
uv pip install torch torchvision torchaudio
uv pip install 'numpy<2'   # Intel Mac: torch 2.2.2 needs NumPy 1.x
```

Full notes: [setup/06-pytorch.md](../../setup/06-pytorch.md).

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
NumPy 2.5.4   # later pinned to 1.26.4 for torch — see Step 6
Vector: [1 2 3], dot product with itself: 14
```

Step 3:

```text
fnm 1.39.0
Node v22.23.3
pnpm 11.2.2
```

Step 4:

```text
rustc 1.99.0 (b940084d7 2026-09-28)
cargo 1.99.0 (5f94df478 2026-08-27)
```

Step 5:

```text
Julia 1.13.1
```

Step 6:

```text
NumPy 1.26.4
torch 2.2.2
CUDA available: False
MPS available:  False
```

## Notes / blockers

- Working on Intel macOS; Homebrew source builds make Step 1 slow but succeeded.
- Step 2 venv landed in `~/.venv` because commands ran from home; activate with `source ~/.venv/bin/activate`. Prefer project-local venvs later.
- Do not paste Python into zsh — enter `python` first.
- Step 3: `fnm use` failed until `source ~/.zshrc`; `npm i -g pnpm` hit EEXIST because pnpm already existed via nvm — ignore and use existing pnpm.
- Skip the lesson’s `arch -arm64 brew install fnm` block on Intel.
- Step 6: torch 2.2.2 is the newest wheel for macOS x86_64; keep `numpy<2`. CUDA/MPS false is expected.
- Step 7 assumes the official curriculum repo (with `phases/…/verify.py`). This journal does not clone it; clone that repo separately when ready to run the preflight.

## Artifacts

- Setup: [setup/01-system-foundation.md](../../setup/01-system-foundation.md), [setup/02-python-uv.md](../../setup/02-python-uv.md), [setup/03-nodejs-fnm-pnpm.md](../../setup/03-nodejs-fnm-pnpm.md), [setup/04-rust.md](../../setup/04-rust.md), [setup/05-julia.md](../../setup/05-julia.md), [setup/06-pytorch.md](../../setup/06-pytorch.md)
- Code: (none yet)

## Next

1. Step 7 — clone official course repo and run route verify
2. Update this log + `PROGRESS.md`; commit once per step
