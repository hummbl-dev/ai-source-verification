# EvalReceipt v0.1 — Local/Hosted Eval Provenance Schema

**Status: CANDIDATE — DO NOT ADOPT YET**

Issue: hummbl-dev/ai-source-verification#14
Parent issue: hummbl-dev/ai-source-verification#9

## Context

The architecture map maps Prime Intellect's eval/reward surfaces to a candidate `EvalReceipt v0.1` primitive. Source claims (PI-VER-002) describe environments used for RL training, evals, synthetic data, and harness experiments. No enforceable provenance chain for eval reuse exists yet.

## Scope

Draft a candidate `EvalReceipt v0.1` schema that captures:

- **Eval setup**: dataset ref, rubric ref, harness ref, model ref
- **Input manifest**: data version, hash, source
- **Rubric version and scoring policy**
- **Output record**: scores, evaluator IDs, reviewer sign-off
- **Provenance chain**: source claims, run receipts, parent eval ref
- **Reproducibility metadata**: seed, environment hash, config snapshot

## Candidate schema

```yaml
eval_receipt_id:
schema_version: "0.1"
status: candidate

eval_setup:
  dataset_ref:
  rubric_ref:
  harness_ref:
  model_ref:

input_manifest:
  data_version:
  data_hash:
  data_source:

rubric:
  rubric_version:
  scoring_policy:

output:
  scores:
  evaluator_ids:
  reviewer_sign_off:

provenance:
  source_claims:
  run_receipts:
  parent_eval_ref:

reproducibility:
  seed:
  environment_hash:
  config_snapshot:
```

## Acceptance criteria

- [x] Candidate schema documented
- [ ] Candidate schema JSON file in `schemas/`
- [ ] Example artifact in `examples/` showing a valid EvalReceipt
- [ ] Provenance chain enforcement rule documented
- [ ] All fields traced to source claims (PI-VER-001, PI-VER-002)
- [ ] Schema marked as `candidate` / `DO_NOT_ADOPT_YET`
- [ ] No dependency on Prime Intellect tooling

## Non-goals

- No dependency adoption
- No eval execution or benchmark reruns
- No canonization as HUMMBL/BaseN/Ownward standard
- No independent validation of Prime Intellect benchmark claims

## Related

- `hummbl-dev/ai-source-verification#9` — parent issue
- `hummbl-dev/ai-source-verification#10` — TrainingRunReceipt (sibling)
- `hummbl-dev/ai-source-verification#15` — EnvironmentContract (sibling)

## Fact posture

Derived from issue #14 and Prime Intellect architecture map. Schema is candidate only. No claims about Prime Intellect implementation beyond source-claimed behavior.

## Receipt

- **Issue**: hummbl-dev/ai-source-verification#14
- **Schema sections**: 6 (setup, input, rubric, output, provenance, reproducibility)
- **Review status**: PENDING
