# AI-LOG.md — CSC13114

## 2026-11-10 — PA#2 rubric audit and harness design

Tool: OpenAI Codex.
Asked for: read the attached brief, rubric and template, identify every PA#2 requirement, and build the initial LeeTKOB harness.
Kept: the Node.js/TypeScript quality-gate structure and the choice of the irreversible Publish endpoint.
Changed: narrowed the generated system to an honest PA#2 in-memory contract harness; sandbox, LLM and persistence claims were moved to later milestones because they are not PA#2 deliverables.
Rejected: claiming full-system or sandbox completion from only an endpoint harness; the class brief makes that PA#3–PA#5 work.

## 2026-11-10 — Publish contract and contract tests

Tool: OpenAI Codex.
Asked for: specify and test `POST /labs/{labId}/publish` against the class brief and product-owner FAQ.
Kept: role/ownership checks, deadline and pending-review conflicts, RFC 9457 errors, and idempotent retry tests.
Changed: cross-class access returns the same `404 lab-not-found` as an unknown lab so callers cannot enumerate another class's data; tests now assert both cases.
Rejected: requiring an idempotency key for Publish; FAQ-12 says pressing Publish again changes nothing, so the resource state itself supplies natural idempotency and preserves the first audit fields.

## 2026-11-10 — CI, permissions and secret policy

Tool: OpenAI Codex.
Asked for: create matching local/CI commands plus written three-tier assistant permissions and secret controls.
Kept: separate lint, format-check, type-check and test commands used verbatim by GitHub Actions.
Changed: added coverage thresholds so the test command can fail on weak tests, and made the future model cost fields explicit but empty in `.env.example`.
Rejected: a fake API key and a guessed model price; PA#2 makes no model calls, and values must be selected and measured honestly in PA#3.

## 2026-11-10 — dependency security audit

Tool: OpenAI Codex.
Asked for: verify the locked dependency tree before committing the PA#2 baseline.
Kept: exact versions and the reproducible `npm ci` workflow.
Changed: `npm audit` found newly published high/critical advisories in the initially selected Fastify 5.6 and Vitest 4.0 releases; upgraded to patched Fastify 5.12 and Vitest 5.1, then reran the complete gate.
Rejected: submitting merely because lint/types/tests were green; those checks do not prove the dependency tree has no known vulnerability.
