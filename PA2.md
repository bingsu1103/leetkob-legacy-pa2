# PA#2 — Harness and quality gate

## Team

| Student ID | Full name       | Contribution |
| ---------- | --------------- | -----------: |
| 23120205   | Ngô Gia An      |          34% |
| 23120207   | Nguyễn Bảo An   |          33% |
| 23120231   | Trương Nhật Đạt |          33% |

The split is the agreed ownership target for PA#2. Each member must be able to explain the full submission at the oral.

## Evidence links

The public repository and branch rule exist. GitHub Actions is temporarily unable to start because GitHub has placed an unrelated billing lock on the repository owner's account. Rows marked `PENDING` must be replaced only by real successful evidence after GitHub Support removes the lock; the failed infrastructure run is explicitly not claimed as a code-quality failure.

| Required evidence                                                 | Link                                                                                                                                    |
| ----------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Public repository                                                 | https://github.com/bingsu1103/leetkob                                                                                                   |
| Protected `main` settings (URL or screenshot in `docs/evidence/`) | Owner settings: https://github.com/bingsu1103/leetkob/settings/branches; exported configuration: `docs/evidence/branch-protection.json` |
| Pull request where a red required check blocked merge             | PENDING — PR #1 exists, but its current failure is a GitHub billing lock and is not valid rubric evidence.                              |
| Commit that turned that pull request green                        | PENDING — prepared local fix commit `eea25c7`; link only after its CI run succeeds.                                                     |
| Green pull request                                                | PENDING                                                                                                                                 |
| CI run for submitted `pa2` tag                                    | PENDING                                                                                                                                 |
| Deliberate contract break caught by CI                            | PENDING — local branch `evidence/contract-break` is prepared separately.                                                                |

Infrastructure incident for transparency: https://github.com/bingsu1103/leetkob/actions/runs/42834599746. Its annotation says the job never started because the account is billing-locked; it is not presented as proof that the gate caught code.

## Reproduce the gate

```bash
npm ci
npm run lint
npm run format:check
npm run typecheck
npm test
```

The required GitHub status check is named `quality-gate`.

Local verification results and the exact commands used are recorded in `docs/evidence/LOCAL_VERIFICATION.md`.

## Endpoint under contract

`POST /labs/{labId}/publish` is specified in `docs/contract/publish-lab.md`. It follows FAQ-01 for ownership and FAQ-12 for the publication preconditions and retry behavior.
