# No-adoption audit stub: `verifiers` + `prime-rl` (2026-07-08)

Date observed: `2026-07-08`  
Scope: source-only, non-adoptive mapping and verification posture for Prime Intellect GitHub artifacts.

## Stance

- `DO_NOT_ADOPT_YET`: none of the mapped terms are canon until operator-approved verification.
- `DO_NOT_ADOPT_YET`: no runtime dependency on Prime Intellect tooling, hosted services, or private data.
- `SOURCE_CLAIM`: all behavioral claims below are recorded from public sources only.
- `LOCAL_AUDIT_REQUIRED`: implementation feasibility and local compatibility are unverified in-repo.
- `HUMMBL_INTERPRETATION`: all architecture mappings are mapping hypotheses only.

## Artifact audit matrix

| artifact | claim_id | source claim summary | stance | open risk | no-adoption condition |
| --- | --- | --- | --- | --- | --- |
| PrimeIntellect-ai/verifiers | PI-VER-001 | Environments include dataset inputs, harnesses, tool/sandbox/context, and reward/rubric surfaces | `SOURCE_CLAIM` + `HUMMBL_INTERPRETATION` | No evidence of formal `EnvironmentContract` schema in HUMMBL context | Do not treat as canonical environment contract until local schema mapping and signed receipts are in place |
| PrimeIntellect-ai/verifiers | PI-VER-002 | Environments usable for RL training, evals, synthetic data, harness experimentation | `SOURCE_CLAIM` + `HUMMBL_INTERPRETATION` | No enforceable provenance boundary for RL/eval/run reuse | Do not map to active governance surface without closure of receipt chain, run IDs, and provenance signatures |
| PrimeIntellect-ai/prime-rl | PI-RL-001 | PRIME-RL requires at least one NVIDIA GPU; named hardware includes 3090/4090/5090/A100/H100/H200/B200 | `SOURCE_CLAIM` + `LOCAL_AUDIT_REQUIRED` | No local feasibility attestation or compatibility manifest exists | Do not claim deployment feasibility without local/authorized compatibility proof |
| PrimeIntellect-ai/prime-rl | PI-RL-002 | RTX 3080 Ti local feasibility not verified in this packet | `LOCAL_AUDIT_REQUIRED` | No local reproduction or minimal check run | Do not treat RTX 3080 Ti as supported without bounded local test evidence |

## No-adoption checks (blocked until audited)

1. `EnvironmentContract` boundary: no canonical HUMMBL/BaseN/Ownward counterpart is adopted from verifiers claims.
2. `Runtime preconditions`: do not assume local GPU support claims from prime-rl are valid until a local audit manifest exists.
3. `Claim provenance`: do not close any claim loop without `ReceiptPolicy` + `EvidenceGraph` links in-repo.
4. `Human authority`: no operational learning loop changes without explicit human sign-off controls and review receipts.

## Required local verification receipts (future)

- Run a repository-only compatibility audit for prime-rl hardware preconditions (non-executing/no-operator-credential path).
- Add explicit source links and access dates for all future verifiers/prime-rl excerpts.
- Add bounded schema drafts for:
  - `Candidate EnvironmentContract`
  - `Candidate EvalReceipt`
  - `Candidate TrainingRunReceipt`  
- Mark all completed items with `LOCAL_AUDIT_REQUIRED -> VERIFIED` only after evidence is attached.

## Notes

This is intentionally a no-adoption packet; it is not approval for migration or dependency adoption.
