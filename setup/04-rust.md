# Setup: 04 — Rust

**Date:** 2026-10-11  
**Lesson:** [Dev Environment](https://aiengineeringfromscratch.com/lesson?path=phases%2F00-setup-and-tooling%2F01-dev-environment&learningPath=software-engineering-fundamentals)  
**Status:** `done`

## Machine

- OS: macOS 15.7.9 (Intel x86_64)
- Toolchain: rustup (default install)
- `rustc`: 1.99.0 (b940084d7 2026-09-28)
- `cargo`: 1.99.0 (5f94df478 2026-08-27)

## Commands

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
# choose option 1 (default) if prompted

source ~/.cargo/env
rustc --version
cargo --version
```

## Result

```text
rustc 1.99.0 (b940084d7 2026-09-28)
cargo 1.99.0 (5f94df478 2026-08-27)
```

## Gotchas

1. **PATH.** New terminals need `~/.cargo/env` (usually already sourced from `~/.zshrc`). If `rustc` is missing, run `source ~/.cargo/env`.
2. **Apple Silicon fnm block is N/A.** The lesson’s `arch -arm64 brew install fnm` path is for M-series Macs only; on Intel it fails with `Unknown architecture: arm64`. Skip it.

## Related

- Lesson log: [lessons/phase-00-setup-and-tooling/01-dev-environment.md](../lessons/phase-00-setup-and-tooling/01-dev-environment.md)
- Progress: [PROGRESS.md](../PROGRESS.md)
