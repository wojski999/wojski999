# Maciej Wojciechowski

Software engineer building with AI coding agents: specs before code, tests that must fail first, and a person who decides and merges.
2.5+ years at a Polish road-freight carrier (39 trucks); since January 2026 the sole engineer of its data and automation platform.

## Projects

### [fleet-platform](https://github.com/fleet-systems-org/fleet-platform) · public
Micro-ERP for trading and transport companies; the first module is trip profitability.
TypeScript · Next.js · React · PostgreSQL + MikroORM · Docker Compose · pnpm monorepo
- Every PR passes lint, typecheck, **100% unit coverage** and build; CI adds integration tests on a real PostgreSQL (Testcontainers) with browser screenshots as evidence.
- Agent PR pipeline: spec → implementation in an isolated worktree → code review with a backward-compatibility check → merge by the owner.
- One-command local setup: `pnpm bootstrap`.

### fleet-systems · private (company data)
Spec-driven rebuild of the carrier's platform in Python, 29 Sep – 18 Oct 2026: **188 merged PRs, 4,398 tests, 72 specifications, a 259-entry decision register**.
- Core: money to the cent, exchange rates, durable jobs with retry and idempotency, backup and restore, an AI model gateway that routes by data sensitivity.
- Integrations: GPS telematics, fuel cards, KSeF e-invoices and an ERP on MS SQL Server — cursors, backfill, deduplication, schema migrations.
- Agent factory: rules as Always / Ask First / Never, a claim protocol so two agents never take the same task, cross-provider review.

### Production system · private (company data)
First generation, Jul – Oct 2026: 968 commits, still serving the company.
- Fuel audit: losses measured at **0.15% of fuel bought** (industry norm 3–10%).
- Monthly closing per truck from GPS, fuel cards and invoices; closing checks pass **18/18 and 19/19**.

### TraceFixMaintenance · private
Incident-diagnosis agent for an online store: replays logs, metrics and traces, investigates the cause with evidence and prepares a fix verified by reproducing the failure first and a regression test after. Evaluated on 120 controlled failure cases from RCAEval.

## Open source
- [open-mercato #6435](https://github.com/open-mercato/open-mercato/pull/6435) — attachments report OCR timeouts and aborts instead of blaming a missing `OPENAI_API_KEY` (open, in review)
- [open-mercato #7867](https://github.com/open-mercato/open-mercato/pull/7867) — the variant form loads when there are no price kinds (open, in review)

## How I build software
- Work starts from a ready issue or an approved spec with acceptance criteria; agents flag open questions instead of inventing requirements.
- Claude Code and Codex work in isolated Git worktrees; every autonomous run is logged with checks passed, failed or not run.
- Bugs are reproduced first, then fixed with a regression test. Money never uses floating point.
- Corrections become lessons; a lesson becomes a rule only with my approval. I decide scope and only I merge.

[LinkedIn](https://linkedin.com/in/maciek-wojciechowski-eng) · Poland · remote
