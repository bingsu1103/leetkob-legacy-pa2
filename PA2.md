# PA#2 — Harness and quality gate

## Team

| Student ID | Full name       | Contribution |
| ---------- | --------------- | -----------: |
| 23120205   | Ngô Gia An      |          34% |
| 23120207   | Nguyễn Bảo An   |          33% |
| 23120231   | Trương Nhật Đạt |          33% |

The split is the agreed ownership target for PA#2. Each member must be able to explain the full submission at the oral.

## Evidence links

Replace every `TODO` only with a real public URL after the repository and evidence PRs exist. Do not submit placeholders.

| Required evidence                                                 | Link |
| ----------------------------------------------------------------- | ---- |
| Public repository                                                 | TODO |
| Protected `main` settings (URL or screenshot in `docs/evidence/`) | TODO |
| Pull request where a red required check blocked merge             | TODO |
| Commit that turned that pull request green                        | TODO |
| Green pull request                                                | TODO |
| CI run for submitted `pa2` tag                                    | TODO |
| Deliberate contract break caught by CI                            | TODO |

## Reproduce the gate

```bash
npm ci
npm run lint
npm run format:check
npm run typecheck
npm test
```

The required GitHub status check is named `quality-gate`.

## Endpoint under contract

`POST /labs/{labId}/publish` is specified in `docs/contract/publish-lab.md`. It follows FAQ-01 for ownership and FAQ-12 for the publication preconditions and retry behavior.
