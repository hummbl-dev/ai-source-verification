# Dependency Map: Governed Optimization-Loop Receipt Pack v0.1

Status: candidate
Date boundary: 2026-07-09
Origin issue: #17

## Purpose

Cross-issue sequencing map for the governed optimization-loop receipt pack. Defines the build order for child issues #10-#15 so that schemas are developed in dependency order without schema drift or premature canonization.

## Boundary

- `DO_NOT_ADOPT_YET`: all terms are candidate / non-canon unless separately audited.
- `no-claim-without-run-record`: no training-derived claim may be made without a linked `TrainingRunReceipt`.
- `no-continual-learning-without-consent`: no continual learning may occur without explicit operator consent and receipt.
- Source packet evidence is bounded and is not independent validation. See `docs/intelligence/prime-intellect-series-a-2026-07-08.md`.

## Dependency order

Issues are ordered so that each issue's schema can reference fields defined by earlier issues.

### 1. EnvironmentContract v0.1 (#15) — foundation

Defines the outermost boundary: dataset, harness, rubric, sandbox, and receipt linkage. All other schemas reference environment fields.

- **Depends on:** none
- **Depended by:** #14 (EvalReceipt), #10 (TrainingRunReceipt), #11 (SpecialistSubagentAssuranceProfile)
- **Schema dependency:** defines `EnvironmentContract` with fields: dataset_ref, harness_ref, rubric_ref, sandbox_policy, receipt_links
- **Source claims:** PI-VER-001, PI-VER-002

### 2. EvalReceipt v0.1 (#14) — eval provenance

Defines eval setup, input manifest, rubric/scoring policy, evaluator identity, and reproducibility metadata. References `EnvironmentContract` for environment fields.

- **Depends on:** #15 (EnvironmentContract) — references `environment_contract_ref`
- **Depended by:** #10 (TrainingRunReceipt) — training runs link to eval receipts for outcome validation
- **Schema dependency:** defines `EvalReceipt` with fields: environment_contract_ref, dataset_ref, rubric_version, scoring_policy, evaluator_ids, reviewer_signoff, reproducibility_metadata
- **Source claims:** PI-VER-001, PI-VER-002

### 3. TrainingRunReceipt v0.1 (#10) — run record

Defines run metadata, config snapshot, dataset references, trace spine, and outcome record. References `EvalReceipt` for outcome validation and `EnvironmentContract` for run environment.

- **Depends on:** #15 (EnvironmentContract), #14 (EvalReceipt) — references `environment_contract_ref` and `eval_receipt_ref`
- **Depended by:** #11 (SpecialistSubagentAssuranceProfile), #12 (OwnwardVoiceRuntimeTrainingEvalBoundary)
- **Schema dependency:** defines `TrainingRunReceipt` with fields: run_id, environment_contract_ref, eval_receipt_ref, dataset_refs, config_snapshot, trace_spine, outcome_record, operator_signoff
- **Enforces:** `no-claim-without-run-record` — any training-derived claim must link a `TrainingRunReceipt`
- **Source claims:** PI-RL-001, PI-RL-002

### 4. Specialist Subagent Assurance Profile v0.1 (#11) — subagent boundary

Defines specialist subagent scope, authority, rollback, validation, and receipt linkage. References `TrainingRunReceipt` for any training-derived subagent behavior.

- **Depends on:** #10 (TrainingRunReceipt) — references `training_run_receipt_ref` for trained subagents
- **Depended by:** #12 (OwnwardVoiceRuntimeTrainingEvalBoundary) — voice runtime boundary may reference subagent profiles
- **Schema dependency:** defines `SpecialistSubagentAssuranceProfile` with fields: scope, allowed_tools, authority_boundary, consent_surface, rollback_semantics, validation_criteria, training_run_receipt_ref
- **Source claims:** PI-RAMP-001, PI-RAMP-002

### 5. Ownward Voice Runtime Training/Eval Boundary v0.1 (#12) — consent layer

Defines consent model, no-continual-learning-without-governance rule, training/eval boundary, and receipt requirements. References `TrainingRunReceipt` for learning-event receipts and `SpecialistSubagentAssuranceProfile` for subagent consent surfaces.

- **Depends on:** #10 (TrainingRunReceipt), #11 (SpecialistSubagentAssuranceProfile) — references both for receipt linkage
- **Depended by:** none (terminal in dependency chain)
- **Schema dependency:** defines `OwnwardVoiceRuntimeTrainingEvalBoundary` with fields: consent_model, learning_trigger_policy, training_run_receipt_ref, subagent_assurance_ref, operator_override, data_handling_boundary
- **Enforces:** `no-continual-learning-without-consent` — any learning event requires explicit consent and receipt
- **Source claims:** HUMMBL_INTERPRETATION (no direct Prime Intellect source for consent controls)

### 6. RuntimeVendor Watchlist v0.1 (#13) — parallel guardrail

Defines vendor posture, trust boundary, data handling, and disclosure requirements. Does not depend on any schema — it is a governance guardrail that runs parallel to the schema chain.

- **Depends on:** none
- **Depended by:** none (parallel, not in the schema chain)
- **Schema dependency:** defines `RuntimeVendorWatchlist` with fields: vendor_name, governance_posture, trust_boundary, data_residency, contract_required, disclosure_template
- **Source claims:** HUMMBL_INTERPRETATION + SOURCE_CLAIM (Prime Intellect, OpenAI GPT-Live, Anthropic, local NIM)

## Dependency graph

```
#15 EnvironmentContract
  |
  +---> #14 EvalReceipt
  |       |
  |       +---> #10 TrainingRunReceipt
  |               |
  |               +---> #11 SpecialistSubagentAssuranceProfile
  |               |       |
  |               |       +---> #12 OwnwardVoiceRuntimeTrainingEvalBoundary
  |               |
  |               +---> #12 OwnwardVoiceRuntimeTrainingEvalBoundary
  |
  +---> #10 TrainingRunReceipt (direct ref)

#13 RuntimeVendorWatchlist (parallel, no schema dependency)
```

## Schema dependency vs implementation dependency

| Issue | Schema dependencies (must exist first) | Implementation dependencies (can be built in parallel) |
|-------|---------------------------------------|------------------------------------------------------|
| #15 | none | none |
| #14 | #15 | none |
| #10 | #15, #14 | none |
| #11 | #10 | none |
| #12 | #10, #11 | none |
| #13 | none | none (parallel guardrail) |

Schema dependency means the schema fields referenced by this issue are defined by the dependency. Implementation dependency means the implementation of this issue requires the dependency to be built first.

For this receipt pack, all dependencies are schema dependencies. Implementation of each issue can proceed once the schema fields it references are defined, even if the full implementation of the dependency is not complete.

## Boundary rules

1. `no-claim-without-run-record`: Any training-derived claim must link a `TrainingRunReceipt` (#10). Claims without run records are `SOURCE_CLAIM` only.
2. `no-continual-learning-without-consent`: Any learning event must have explicit operator consent and a receipt. Enforced by #12.
3. `DO_NOT_ADOPT_YET`: All schemas are candidate. No schema is canonical until operator-approved review passes.
4. Source packet evidence is bounded: See `docs/intelligence/prime-intellect-series-a-2026-07-08.md`. No independent validation has been performed.

## Non-goals

- No training execution
- No eval execution
- No Prime Intellect adoption
- No vendor commitment
- No canonization
- No public/private boundary expansion
- No dependency installation

## Source artifacts

- `docs/intelligence/prime-intellect-series-a-2026-07-08.md` — source-claim packet
- `docs/architecture/owned-optimization-loops-prime-intellect-map.md` — architecture mapping
- `docs/audits/prime-intellect-verifiers-prime-rl-no-adoption-audit.md` — no-adoption audit stub
