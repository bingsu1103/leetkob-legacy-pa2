# Self-assessment — PA#2

Submitted by:

- 23120205 — Ngô Gia An (34%)
- 23120207 — Nguyễn Bảo An (33%)
- 23120231 — Trương Nhật Đạt (33%)

Total I claim: 75 / 100

| Criterion                      |     Max | I claim | Evidence                                                                                                                                                               |
| ------------------------------ | ------: | ------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. Rules file                  |      15 |      15 | `AGENTS.md` has stack, commands, conventions and product-specific never rules; two refinements are traced to `AI-LOG.md` dated 2026-11-10.                             |
| 2. Permissions and secrets     |      10 |      10 | `SECURITY.md` records allowed/ask-first/never tiers; `.env.example` lists empty variables; `.gitignore` excludes secrets; `README.md` documents the spending-cap gate. |
| 3. One command for every check |      10 |      10 | `README.md` and `package.json`: `npm run lint`, `npm run format:check`, `npm run typecheck`, `npm test`; `.github/workflows/ci.yml` invokes the same commands.         |
| 4. CI that blocks a merge      |      20 |       0 | Not claimed until public branch protection and real red-to-green PR evidence are linked in `PA2.md`.                                                                   |
| 5. One endpoint contract       |      25 |      25 | `docs/contract/publish-lab.md`: role and class ownership, request/response fields, RFC 9457 error types, natural idempotency, concurrency, and observable effects.     |
| 6. Contract tests that bite    |      15 |      10 | `test/publish-contract.test.ts` covers success, every error, ownership and idempotency in CI; deliberate failing-CI URL is not yet available.                          |
| 7. AI-LOG.md                   |       5 |       5 | `AI-LOG.md` names the tool/tasks and records concrete kept/changed/rejected decisions and checks.                                                                      |
| **Total**                      | **100** |  **75** | The ZIP name must end in `_75.zip` unless this table is updated after GitHub evidence is completed.                                                                    |

## What we did not manage

At the time this report was generated, the workspace had no Git repository or authenticated GitHub access. Therefore we do not claim the 20 branch-protection points or the final 5 contract-test evidence points. Before submission, the team must create a public repository, establish branch protection before normal work continues, produce real red-to-green and deliberate-contract-break CI history, link it in `PA2.md`, tag the submitted commit `pa2`, push the tag, and then update this score honestly.

The C++ sandbox and LLM constraint-review pipeline are intentionally not implemented in PA#2; the brief schedules those capabilities for later checkpoints.

## What we would do differently

Create and protect the public repository before implementation so every meaningful change, including the first deliberately failing contract test, is preserved as authentic pull-request evidence instead of being reconstructed near the deadline.
