# Setup: 03 — Node.js with fnm + pnpm

**Date:** 2026-10-11  
**Lesson:** [Dev Environment](https://aiengineeringfromscratch.com/lesson?path=phases%2F00-setup-and-tooling%2F01-dev-environment&learningPath=software-engineering-fundamentals)  
**Status:** `done`

## Machine

- OS: macOS 15.7.9 (Intel x86_64)
- `fnm`: 1.39.0 via Homebrew → `/usr/local/bin/fnm`
- Node (fnm): v22.23.3 (default)
- `pnpm`: 11.2.2 (already present under the previous nvm Node toolchain)
- Also present: nvm with Node v22.22.3 and older versions (fnm takes precedence after shell setup)

## Commands

```bash
curl -fsSL https://fnm.vercel.app/install | bash
# installer appended fnm env block to ~/.zshrc and installed Node 22

source ~/.zshrc
fnm install 22    # already done; installs v22.23.3
fnm use 22
npm install -g pnpm   # optional if pnpm already exists
node -e "console.log('Node', process.version)"
pnpm -v
```

## Result

After `source ~/.zshrc` / `eval "$(fnm env --shell zsh)"`:

```text
fnm 1.39.0
* v22.23.3 default
Node v22.23.3
pnpm 11.2.2
```

## Gotchas

1. **`fnm use` before shell setup.** Right after the installer, `fnm use 22` failed with *We can't find the necessary environment variables…* because the new `~/.zshrc` block had not been sourced yet. Fix: `source ~/.zshrc`, then `fnm use 22`.
2. **`npm install -g pnpm` EEXIST.** `pnpm` already existed at `~/.nvm/versions/node/v22.22.3/bin/pnpm`. Not a blocker — `pnpm -v` works. Only use `npm install -g pnpm --force` if you need to overwrite.
3. **nvm still on the machine.** Before sourcing fnm env, `node` reported v22.22.3 (nvm). After fnm env, active Node is v22.23.3. Prefer one manager long-term; for this lesson, fnm + existing pnpm satisfies the check.
4. **Intel Homebrew warning.** Same Tier-3 / no-bottles notice as Step 1; fnm itself poured a Sonoma bottle successfully.

## Related

- Lesson log: [lessons/phase-00-setup-and-tooling/01-dev-environment.md](../lessons/phase-00-setup-and-tooling/01-dev-environment.md)
- Progress: [PROGRESS.md](../PROGRESS.md)
