# Governed EnvironmentContract v0.1 — Dataset + Harness + Rubric + Receipt Boundary

**Status: CANDIDATE — DO NOT ADOPT YET**

Issue: hummbl-dev/ai-source-verification#15
Parent issue: hummbl-dev/ai-source-verification#9

## Context

The architecture map maps Prime Intellect's environment primitives (PI-VER-001) to a candidate `Governed EnvironmentContract v0.1`. Source claims describe environments as including dataset inputs, harnesses, tools/sandboxes/context, and reward/rubric surfaces. No canonical environment interface contract exists in this repo.

## Scope

Draft a candidate `Governed EnvironmentContract v0.1` that defines:

- **Dataset boundary**: version, hash, source, access policy
- **Harness boundary**: allowed tools, sandbox controls, context limits
- **Rubric boundary**: scoring policy, reward function ref, version
- **Receipt linkage**: source claims, eval receipts, training run receipts
- **Governance controls**: operator authority, review gate, posture markers
- **Enforcement semantics**: what happens when contract is violated

## Candidate schema

```yaml
environment_contract_id:
schema_version: "0.1"
status: candidate

dataset_boundary:
  version:
  hash:
  source:
  access_policy:

harness_boundary:
  allowed_tools:
  sandbox_controls:
  context_limits:

rubric_boundary:
  scoring_policy:
  reward_function_ref:
  rubric_version:

receipt_linkage:
  source_claims:
  eval_receipts:
  training_run_receipts:

governance:
  operator_authority:
  review_gate:
  posture_markers:

enforcement:
  violation_semantics:
```

## Acceptance criteria

- [x] Candidate schema documented
- [ ] Candidate schema JSON file in `schemas/`
- [ ] Example artifact in `examples/` showing a valid EnvironmentContract
- [ ] All fields traced to source claims (PI-VER-001, PI-VER-002)
- [ ] Contract marked as `candidate` / `DO_NOT_ADOPT_YET`
- [ ] Governance controls linked to `OperatorAuthority` and `HumanReviewGate` candidates
- [ ] No dependency on Prime Intellect tooling

## Non-goals

- No dependency adoption
- No environment execution or RL training
- No canonization as HUMMBL/BaseN/Ownward standard
- No operator credential use

## Related

- `hummbl-dev/ai-source-verification#9` — parent issue
- `hummbl-dev/ai-source-verification#10` — TrainingRunReceipt (sibling)
- `hummbl-dev/ai-source-verification#14` — EvalReceipt (sibling)

## Fact posture

Derived from issue #15 and Prime Intellect architecture map. Schema is candidate only. No claims about Prime Intellect implementation beyond source-claimed behavior.

## Receipt

- **Issue**: hummbl-dev/ai-source-verification#15
- **Schema sections**: 6 (dataset, harness, rubric, linkage, governance, enforcement)
- **Review status**: PENDING
