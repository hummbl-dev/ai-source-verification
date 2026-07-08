# No-adoption audit stub: Prime Intellect `verifiers` + `prime-rl` (2026-07-08)

Date observed: `2026-07-08`  
Scope: source packet and bounded feasibility/audit posture for Prime Intellect GitHub artifacts.

## Stance

- `DO_NOT_ADOPT_YET`: no mapped term is canonical without operator approval.
- `DO_NOT_ADOPT_YET`: no dependency migration to Prime Intellect tooling, hosted services, or private customer data.
- `SOURCE_CLAIM`: claims are source-recorded only.
- `LOCAL_AUDIT_REQUIRED`: implementation feasibility and compatibility checks remain unverified locally.
- `HUMMBL_INTERPRETATION`: all mapping entries are hypothesis-only.

## Artifact audit matrix

| artifact | claim_id | claim summary | posture | open risk | no-adoption lock |
| --- | --- | --- | --- | --- | --- |
| PrimeIntellect-ai/verifiers | PI-VER-001 | Environment primitives include dataset inputs, harnesses, tools/sandboxes/context, and reward/rubric surfaces | `SOURCE_CLAIM` + `HUMMBL_INTERPRETATION` | No canonical `EnvironmentContract` schema in HUMMBL boundary yet | No adoption until contract and receipt schema are bounded in-repo |
| PrimeIntellect-ai/verifiers | PI-VER-002 | Environments are used for RL training, evals, synthetic data, and harness experiments | `SOURCE_CLAIM` + `HUMMBL_INTERPRETATION` | No enforceable provenance chain for RL/eval reuse | No operational mapping without trace/reproducibility receipts |
| PrimeIntellect-ai/prime-rl | PI-RL-001 | At least one NVIDIA GPU required; hardware list includes 3090/4090/5090/A100/H100/H200/B200 | `SOURCE_CLAIM` + `LOCAL_AUDIT_REQUIRED` | No local compatibility manifest or feasibility evidence | No deployment inference until local audit manifest exists |
| PrimeIntellect-ai/prime-rl | PI-RL-002 | RTX 3080 Ti feasibility unverified locally | `LOCAL_AUDIT_REQUIRED` | No local support assertion with reproducible evidence | No feasibility claim until bounded local test evidence is added |

## No-adoption gates

1. Candidate concepts only (`EnvironmentContract`, `HarnessContract`, `EvalReceipt`, `TrainingRunReceipt`, `TraceReceipt`, etc.) until local or operator-approved review.
2. No `no-claim-without-run` enforcement is established in this packet; close claims only as `recorded` until run receipts exist.
3. No operator or infrastructure migration should be inferred from these source claims.
4. No benchmarks in this packet are treated as independently validated.

## Required follow-through

- Add explicit access-date-backed source links for each claim.
- Produce bounded repository-only compatibility checks (environment/hardware) before any feasibility assertions.
- Draft minimal candidate schemas for `ReceiptPolicy`, `EvalReceipt`, and `TrainingRunReceipt` if and only as part of mapping work.
- Require explicit operator review + review receipts for any future claim-to-action transitions.

## The audit should answer

1. Can source claims for `verifiers` and `prime-rl` be used for operational adoption?
   - Current answer: No. `DO_NOT_ADOPT_YET` on all claim-to-action mappings.
2. Are `PI-VER-001` and `PI-VER-002` sufficient to define a canonical `EnvironmentContract`/`EvalReceipt`?
   - Current answer: Not yet. `SOURCE_CLAIM` only; no canonical schema or enforcement rules proven in-repo.
3. Is PRIME-RL’s NVIDIA/GPU requirement independently auditable from local repo evidence?
   - Current answer: No. `LOCAL_AUDIT_REQUIRED`; local feasibility evidence is missing.
4. Is RTX 3080 Ti support claim valid for local deployment?
   - Current answer: No evidence in this packet. `LOCAL_AUDIT_REQUIRED`.
5. Can any candidate controls (`OperatorAuthority`, `Review`, `ReceiptPolicy`, `TraceReceipt`, etc.) be treated as adopted constraints now?
   - Current answer: No. All are candidate-only mappings awaiting explicit governance review.
