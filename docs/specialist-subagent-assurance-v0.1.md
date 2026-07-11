# Specialist Subagent Assurance Profile v0.1

**Status: CANDIDATE — DO NOT ADOPT YET**

Issue: hummbl-dev/ai-source-verification#11
Parent issue: hummbl-dev/ai-source-verification#9

## Context

Prime Intellect's Ramp case study (PI-RAMP-001) describes a specialist spreadsheet retrieval subagent. The architecture map maps this to a candidate `Specialist Subagent Assurance Profile v0.1` primitive.

Currently, scope, rollback, and authority boundaries for specialist subagents are not operationally defined in this repo.

## Scope

Draft a candidate `Specialist Subagent Assurance Profile v0.1` that defines:

- **Scope boundary**: task domain, allowed tools, data access
- **Authority boundary**: what the subagent can and cannot decide
- **Consent surface**: what requires human approval
- **Rollback semantics**: how to undo subagent actions
- **Validation criteria**: how to assess subagent output quality
- **Receipt linkage**: source claims, eval receipts, run receipts

## Candidate schema

```yaml
specialist_subagent_profile_id:
schema_version: "0.1"
status: candidate

scope_boundary:
  task_domain:
  allowed_tools:
  data_access:

authority_boundary:
  can_decide:
  cannot_decide:

consent_surface:
  requires_human_approval:

rollback_semantics:
  undo_actions:

validation_criteria:
  output_quality_checks:

receipt_linkage:
  source_claims:
  eval_receipts:
  run_receipts:
```

## Acceptance criteria

- [x] Candidate profile documented
- [ ] Candidate profile schema or template in `schemas/` or `docs/`
- [ ] Example artifact showing a valid specialist subagent profile
- [ ] All fields traced to source claims (PI-RAMP-001, PI-RAMP-002)
- [ ] Profile marked as `candidate` / `DO_NOT_ADOPT_YET`
- [ ] No dependency on Prime Intellect tooling

## Non-goals

- No dependency adoption
- No subagent deployment or execution
- No canonization as HUMMBL/BaseN/Ownward standard
- No independent benchmark reruns (PI-RAMP-002 is `LOCAL_AUDIT_REQUIRED`)

## Related

- `hummbl-dev/ai-source-verification#9` — parent issue
- `hummbl-dev/ai-source-verification#10` — TrainingRunReceipt (sibling)
- `hummbl-dev/ai-source-verification#14` — EvalReceipt (sibling)
- `hummbl-dev/ai-source-verification#15` — EnvironmentContract (sibling)

## Fact posture

Derived from issue #11 and Prime Intellect architecture map. Profile is candidate only. No claims about Prime Intellect implementation beyond source-claimed behavior.

## Receipt

- **Issue**: hummbl-dev/ai-source-verification#11
- **Schema sections**: 6 (scope, authority, consent, rollback, validation, linkage)
- **Review status**: PENDING
