# TrainingRunReceipt v0.1 — No Claim Without Run Record

**Status: CANDIDATE — DO NOT ADOPT YET**

Issue: hummbl-dev/ai-source-verification#10
Parent issue: hummbl-dev/ai-source-verification#9

## Context

Prime Intellect's `verifiers` and `prime-rl` artifacts describe training run metadata, config, traces, and outcomes. The architecture map maps this to a candidate `TrainingRunReceipt v0.1` primitive with a `no-claim-without-run-record` control.

Currently, no canonical run-boundary schema or validation exists in this repo. Claims about training outcomes cannot be traced to run records.

## Scope

Draft a candidate `TrainingRunReceipt v0.1` schema that captures:

- **Run metadata**: run ID, operator, timestamp, environment ref
- **Dataset references**: version, hash, source
- **Config snapshot**: model, hyperparameters, reward function ref
- **Trace spine**: immutable step IDs, signed checkpoints
- **Outcome record**: metrics, evaluator IDs, state transitions
- **Receipt linkage**: source claims, eval receipts, parent run ref

## Candidate schema

```yaml
training_run_receipt_id:
schema_version: "0.1"
status: candidate

run_metadata:
  run_id:
  operator:
  timestamp:
  environment_ref:

dataset_references:
  - dataset_id:
    version:
    hash:
    source:

config_snapshot:
  model:
  hyperparameters:
  reward_function_ref:

trace_spine:
  step_ids:
  signed_checkpoints:

outcome:
  metrics:
  evaluator_ids:
  state_transitions:

receipt_linkage:
  source_claims:
  eval_receipts:
  parent_run_ref:
```

## Governing control

> **no-claim-without-run-record**: No claim about training outcomes may be made without a corresponding TrainingRunReceipt.

## Acceptance criteria

- [x] Candidate schema documented
- [ ] Candidate schema JSON file in `schemas/`
- [ ] Example artifact in `examples/` showing a valid TrainingRunReceipt
- [ ] `no-claim-without-run-record` enforcement rule documented
- [ ] All fields traced to source claims in the architecture map
- [ ] Schema marked as `candidate` / `DO_NOT_ADOPT_YET`
- [ ] No dependency on Prime Intellect tooling

## Non-goals

- No dependency adoption
- No GPU training or execution
- No canonization as HUMMBL/BaseN/Ownward standard
- No operator credential use

## Related

- `hummbl-dev/ai-source-verification#9` — parent issue
- `hummbl-dev/ai-source-verification#14` — EvalReceipt (sibling)
- `hummbl-dev/ai-source-verification#15` — EnvironmentContract (sibling)

## Fact posture

Derived from issue #10 and Prime Intellect architecture map. Schema is candidate only. No claims about Prime Intellect implementation beyond source-claimed behavior.

## Receipt

- **Issue**: hummbl-dev/ai-source-verification#10
- **Schema sections**: 6 (metadata, dataset, config, trace, outcome, linkage)
- **Governing control**: no-claim-without-run-record
- **Review status**: PENDING
