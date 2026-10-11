# Setup: 01 — System Foundation

**Date:** 2026-10-11  
**Lesson:** [Dev Environment](https://aiengineeringfromscratch.com/lesson?path=phases%2F00-setup-and-tooling%2F01-dev-environment&learningPath=software-engineering-fundamentals)  
**Status:** `done`

## Machine

- OS: macOS 15.7.9 (Build 24G830)
- Arch: Intel x86_64
- Homebrew prefix: `/usr/local`
- Xcode Command Line Tools: already installed (full Xcode present); Homebrew warned a newer CLT (Xcode 26.3) is available — not blocking

## Commands

```bash
# macOS
xcode-select --install
brew install git curl wget
```

`xcode-select` reported CLT already installed. Homebrew upgraded outdated `git`, `curl`, and `wget` (and built several dependencies from source).

## Result

```text
$ git --version && curl --version | head -1 && wget --version | head -1

git version 2.56.0
curl 8.7.1 (x86_64-apple-darwin24.0) libcurl/8.7.1 (SecureTransport) LibreSSL/3.3.6 zlib/1.2.12 nghttp2/1.64.0
GNU Wget 1.25.0 built on darwin24.6.0.
```

Homebrew package versions after install:

| Formula | Cellar version | On PATH |
|---------|----------------|---------|
| git | 2.56.0_1 | `/usr/local/bin/git` |
| wget | 1.25.0_2 | `/usr/local/bin/wget` |
| curl | 8.22.0_1 (keg-only) | system `/usr/bin/curl` 8.7.1 stays first |

## Gotchas

1. **Intel Mac / no bottles.** Homebrew no longer builds bottles for Intel x86_64. Upgrades compile from source. `cmake` (a `curl` dependency) took a long time with little terminal output on `==> make` — that was progress, not a hang.
2. **`curl` is keg-only on macOS.** Homebrew installs it but does not symlink into `/usr/local/bin` so it does not shadow Apple’s curl. Seeing 8.7.1 from `curl --version` is expected. To prefer Homebrew curl: `export PATH=/usr/local/opt/curl/bin:$PATH`.
3. **CLT update nag.** Homebrew repeatedly suggested updating Command Line Tools; optional for this step.
4. **Untrusted taps.** Homebrew ignored `facebook/fb` and `supabase/tap` until trusted — unrelated to this install.

## Related

- Lesson log: [lessons/phase-00-setup-and-tooling/01-dev-environment.md](../lessons/phase-00-setup-and-tooling/01-dev-environment.md)
- Progress: [PROGRESS.md](../PROGRESS.md)
