# GitHub issue draft: Prime Intellect owned optimization loop — no-adoption feasibility audit

## Title
Prime Intellect owned-optimization-loop source packet follow-up: no-adoption bounded feasibility + policy mapping

## Type
- Proposal / Follow-up task issue

## Summary
Create a follow-up audit path for Prime Intellect claims around owned optimization loops that preserves current `DO_NOT_ADOPT_YET` posture and avoids dependency adoption.

## Context
- `docs/intelligence/prime-intellect-series-a-2026-07-08.md` (source-claim packet with posture labels)
- `docs/architecture/owned-optimization-loops-prime-intellect-map.md` (candidate concept mapping)
- `docs/audits/prime-intellect-verifiers-prime-rl-no-adoption-audit.md` (feasibility/risk stub)
- Unverified local feasibility remains flagged as `LOCAL_AUDIT_REQUIRED`

## Requested follow-up (candidate issues)
1. `EnvironmentContract v0.1` — define candidate dataset + harness + rubric boundary and receipt linkages.
2. `EvalReceipt v0.1` — add local/hosted eval provenance schema.
3. `TrainingRunReceipt v0.1` — enforce `no-claim-without-run-record` checks for training-derived claims.
4. `Specialist Subagent Assurance Profile v0.1` — formalize specialist subagent validation and boundary.
5. `Ownward Voice Runtime Training/Eval Boundary v0.1` — encode consent + no-continual-learning-without-governance rule.
6. `RuntimeVendor Watchlist v0.1` — include Prime Intellect, OpenAI GPT-Live, Anthropic, local NIM with governance posture.

## Acceptance criteria
- Keep Prime Intellect terminology as SOURCE_CLAIM or external report only; no canonized HUMMBL/BaseN/Ownward claims.
- Add minimal local smoke-test notes for `prime-rl` GPU-path feasibility and `verifiers` eval offline/hosted boundary.
- Preserve explicit “DO NOT USE PRIVATE STRATEGY IN PUBLIC REPO” and boundary clauses in issue resolution docs.
- Ensure no external dependency adoption without explicit operator authorization.

## Non-goals
- No dependency installation or GPU training in this issue.
- No operator credential use.
- No public/private boundary expansion.

## Proposed next action
- Open this as a tracking issue after final review and assign local owner for each candidate section; keep outputs in `docs/` + `receipts/`.
