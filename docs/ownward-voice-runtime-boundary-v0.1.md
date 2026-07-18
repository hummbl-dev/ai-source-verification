# Ownward Voice Runtime Training/Eval Boundary v0.1

**Status: CANDIDATE — DO NOT ADOPT YET**

Issue: hummbl-dev/ai-source-verification#12
Parent issue: hummbl-dev/ai-source-verification#9

## Context

The architecture map identifies continual learning as a candidate governance area. Prime Intellect's positioning includes ongoing optimization/update loops after deployment. No direct source artifact for consent or opt-in policy controls exists in the current packet.

This issue addresses the Ownward voice runtime boundary: no continual learning without explicit consent and receipt.

## Scope

Draft a candidate `Ownward Voice Runtime Training/Eval Boundary v0.1` that encodes:

- **Consent model**: explicit opt-in required before any continual learning
- **No-continual-learning-without-governance rule**
- **Training/eval boundary definition**: what triggers learning, what doesn't
- **Receipt requirements**: for any learning event
- **Operator override and veto semantics**
- **Data handling boundary**: what data may be used for learning

## Candidate boundary definition

```yaml
boundary_id:
schema_version: "0.1"
status: candidate

consent_model:
  opt_in_required: true
  consent_scope:
  consent_expiry:

no_continual_learning_rule:
  description: "No continual learning without explicit consent and receipt"
  exceptions: none

training_eval_boundary:
  triggers_learning:
  does_not_trigger_learning:

receipt_requirements:
  linked_to_training_run_receipt: true
  required_fields:

operator_override:
  veto_semantics:
  override_scope:

data_handling:
  allowed_data:
  prohibited_data:
  retention_policy:
```

## Acceptance criteria

- [x] Boundary definition documented
- [x] Consent model documented
- [x] No-continual-learning rule documented
- [x] Receipt requirements linked to TrainingRunReceipt (#10)
- [ ] Boundary definition document in `docs/`
- [ ] Consent model schema or template
- [ ] All concepts marked `candidate` / `DO_NOT_ADOPT_YET`
- [ ] No dependency on Prime Intellect tooling
- [ ] Explicit `HUMMBL_INTERPRETATION` posture on all mapping entries

## Non-goals

- No dependency adoption
- No continual learning implementation
- No canonization as HUMMBL/BaseN/Ownward standard
- No private strategy or workflow data in public artifacts

## Related

- `hummbl-dev/ai-source-verification#9` — parent issue
- `hummbl-dev/ai-source-verification#10` — TrainingRunReceipt (sibling)
- `hummbl-dev/ai-source-verification#13` — RuntimeVendor Watchlist (sibling)

## Fact posture

Derived from issue #12 and Prime Intellect architecture map. Boundary is candidate only. No claims about Prime Intellect implementation beyond source-claimed behavior.

## Receipt

- **Issue**: hummbl-dev/ai-source-verification#12
- **Schema sections**: 6 (consent, rule, boundary, receipts, override, data handling)
- **Review status**: PENDING
