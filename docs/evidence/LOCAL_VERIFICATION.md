# Local verification — PA#2 submission candidate

Verified on 2026-11-10 with Node.js 22 and npm 10.

## Fresh-install quality gate

```bash
npm ci
npm run lint
npm run format:check
npm run typecheck
npm test
npm run build
npm audit --audit-level=low
```

Expected result:

- lint: zero warnings and errors;
- format check: every tracked source/document matches Prettier;
- type check: strict TypeScript succeeds;
- tests: 17/17 pass across two files;
- coverage: 98% statements, 97.14% branches, 100% functions, 97.91% lines;
- production build: succeeds;
- dependency audit: zero known vulnerabilities.

## Secret/history review

The submitted tree contains no `.env` file. `.env.example` contains variable names with empty values. The complete local Git history was searched for common private-key, GitHub-token, provider-token, and credential assignment patterns; no live secret was found.

Re-run before packaging:

```bash
git ls-files | grep -E '(^|/)\.env($|\.)' || true
git log -p --all -- . ':!package-lock.json' | rg -n 'BEGIN (RSA|OPENSSH|EC) PRIVATE KEY|gh[pousr]_[A-Za-z0-9]{20,}|(API_KEY|TOKEN|PASSWORD|SECRET)\s*[:=]\s*[^[:space:]<]+'
```

The expected tracked environment file is only `.env.example`; the history search should return no matches. GitHub's public-repository secret scanning remains an additional remote control, not a substitute for this check.

## Remote evidence status

`main` was protected before the evidence branches were pushed. The exported rule in `branch-protection.json` requires the `quality-gate` status, an up-to-date branch, a pull request and one approval; it applies to administrators and disables force pushes/deletion.

GitHub Actions currently cannot allocate a runner because the owner's account has an account-level billing lock. The GitHub Support ticket is outside the repository and contains no project secret. `PA2.md` deliberately leaves every CI-dependent rubric link pending until an actual workflow runs.

## Remaining remote-only steps

1. Re-run PR #1 after GitHub removes the billing lock and record the red run for its intentional lint failure plus the green run for commit `eea25c7`.
2. Push/open the prepared `evidence/contract-break` branch and record the failing contract-test run; close it without merging.
3. Open the final submission PR, obtain the required teammate approval, merge it, tag that commit `pa2`, push the tag, and link its green run.
4. Update `PA2.md` and `SELF_ASSESSMENT_REPORT.md`, recalculate the total, then regenerate the ZIP with the same number in its filename.
