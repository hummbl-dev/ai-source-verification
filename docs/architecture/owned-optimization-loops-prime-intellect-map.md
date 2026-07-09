# Owned Optimization Loops — Prime Intellect Architecture Map

Status: candidate
Date boundary: 2026-07-08

## Source posture
- `SOURCE_CLAIM`
- `LOCAL_AUDIT_REQUIRED`
- `HUMMBL_INTERPRETATION`
- `DO_NOT_ADOPT_YET`

## Cautious HUMMBL candidate mapping

- `Candidate-only`: Every row is a mapping hypothesis, not a required architecture decision.
- `No canon without explicit operator approval`: No column entry is treated as canonical HUMMBL/BaseN/Ownward doctrine.
- `Evidence-first constraint`: `SOURCE_CLAIM`/`HUMMBL_INTERPRETATION` rows must be closed with receipt-linked local or external verification before any adoption.
- `No dependency migration`: mapped terms from Prime claims do not imply dependency, tool, or workflow migration.
- `Action discipline`: rows with `LOCAL_AUDIT_REQUIRED` are blocked from adoption until feasibility/audit evidence is attached.

## Short mapping

- `PI-SA-2026-001` / `PI-SA-2026-002` / `PI-SA-2026-003`: source-backed ownership thesis and stack decomposition; used as bounded strategic context only.
- `PI-RAMP-001` / `PI-RAMP-002`: specialist subagent development + benchmark reporting, treated as bounded evidence for interpretation and non-canon profiling only.
- `PI-VER-001` / `PI-VER-002`: environment surface (dataset + harness + reward/rubric; RL/evals/synthetic/harness uses) mapped to candidate `EnvironmentContract` / `EvalReceipt` controls.
- `PI-RL-001` / `PI-RL-002`: hardware and local feasibility boundaries mapped to deployment/audit gating requirements.

## Mapping table

| Prime concept | Source meaning | HUMMBL adjacent primitive | Current status | Gap | Proposed next action |
| --- | --- | --- | --- | --- | --- |
| Owned model optimization loop | Prime’s public positioning around organizational control of optimization process | `governed optimization lifecycle` (candidate) | `HUMMBL_INTERPRETATION` source-mapped | Term is strategic shorthand, not verified as formal architecture pattern | Keep as non-canonical term; require local governance/audit mapping before adoption |
| RL environment | Prime-specified environments for task-specific RL workflows | `EnvironmentContract` / harness boundary candidate | `SOURCE_CLAIM` mapped | Environment interface contracts are not yet normalized as formal schema | Draft HUMMBL-side environment interface schema + receipt linkage |
| Harness | Tooling + sandbox controls around RL or eval actions | `EvalReceipt` / controlled execution boundary (candidate) | `SOURCE_CLAIM` mapped | Missing explicit boundary definitions for tool invocation and audit trails | Define harness control schema and attach receipts per tool path |
| HarnessContract | Contract for allowed tool actions, context boundaries, and invocation policy | `HarnessContract` (candidate) + `EvalReceipt` envelope | `HUMMBL_INTERPRETATION` | Candidate concept appears in source intent but lacks formal schema in repo | Draft candidate `HarnessContract` with explicit tool policy, allowed actions, and receipt links |
| Sandbox | Isolated runtime area for RL/eval execution | `Runtime control boundary` + `receipt-scoped isolation` (candidate) | `SOURCE_CLAIM` mapped | No explicit isolation policy or recovery semantics in captured source | Add local policy mapping for sandbox boundaries and failure containment |
| Reward function / rubric | Scoring logic used in verification or RL updates | `EvalReceipt` + `Evidence scoring policy` (candidate) | `SOURCE_CLAIM` mapped | Scoring semantics and governance constraints are not standardized in captured claims | Add schema for score provenance, rubric versioning, and sign-off requirements |
| RewardRubric | Explicit rubric-like artifact used to evaluate outputs or behaviors | `Evidence scoring policy` + `EvalReceipt` + `EvalReceipt v0.1` (candidate) | `HUMMBL_INTERPRETATION` + `SOURCE_CLAIM` | No canonical rubric format, version history, or audit trail requirements in source | Publish candidate rubric receipt schema with owner, version, change-log, and validation steps |
| ClaimPosture | Source-claim / interpretation / verification posture applied before mapping | `ClaimPosture marker` (candidate) + `Receipt boundary` (candidate) | `HUMMBL_INTERPRETATION` | Source posture taxonomy is present but enforcement and policy binding are not implemented as architecture rule | Add a constrained posture enum and require posture checks before any HUMMBL interpretation |
| OperatorAuthority | Human authority boundary over training/eval run lifecycle | `Operator override + sign-off` (candidate) + `No-claim-without-run` control | `HUMMBL_INTERPRETATION` | Source claims do not define operator veto, override, or explicit consent workflows for loop continuation | Add explicit operator sign-off checkpoint and auditable authority log for every production-affecting change |
| HumanReviewGate | Required human review before adoption of claims, receipts, or run changes | `Human-review gate` (candidate) + `ReviewReceipt` (candidate) | `HUMMBL_INTERPRETATION` | No explicit mandatory review workflow or reviewer attribution in source claims | Add gate definition with mandatory reviewer role, scope, timestamp, and escalation path |
| ReceiptPolicy | Governance rule defining required receipts and mandatory fields for each claim chain | `ReceiptPolicy` (candidate) + `DO_NOT_ADOPT_YET` boundary | `HUMMBL_INTERPRETATION` | No enforceable policy object currently defines minimum receipt completeness and closure | Draft bounded receipt policy contract (required fields, signer role, chain depth, failure handling) |
| RuntimeVendor | Third-party/provider actor for training/eval infrastructure | `RuntimeVendor Watchlist` (candidate) + `HostedRunReceipt` (candidate) | `HUMMBL_INTERPRETATION` + `DO_NOT_ADOPT_YET` | Source list includes vendors, but host-level controls, contracts, and trust boundaries are not established | Require signed vendor contract evidence, residency model, and explicit `DO_NOT_ADOPT_YET` boundary checks |
| EvidenceGraph | Bound provenance graph connecting sources, claims, and interpretations | `EvidenceGraph` (candidate) + `Receipt spine` | `HUMMBL_INTERPRETATION` + `SOURCE_CLAIM` | No canonical schema for graph edges, trust metadata, and verification closure in repo | Publish bounded graph schema with claim-link integrity, provenance hashes, and unresolved-node tracking |
| Evaluation | Comparison and reporting of model outputs for optimization quality | `EvalReceipt` / `Evaluation trace` (candidate) | `SOURCE_CLAIM` mapped | Eval reproducibility and chain completeness not yet independently verified | Add eval manifest with data, rubric, and reviewer receipt |
| EvalReceipt | Bound receipt artifact for eval setup, inputs, rubric, outputs, and interpretation | `EvalReceipt v0.1` (candidate) + `Receipt boundary` (candidate) | `HUMMBL_INTERPRETATION` + `DO_NOT_ADOPT_YET` | No authoritative in-repo schema or required provenance fields | Define bounded schema, required receipts, and non-adoptive review workflow |
| Rollout trace | End-to-end sequence record of action, state, reward, and policy updates | `TrainingRunReceipt` + execution trace ledger (candidate) | `SOURCE_CLAIM` mapped | Replayability and integrity controls are not defined in source claims | Require trace schema with immutable step IDs and signed checkpoints |
| TrainingRunReceipt | Bounded record of training run metadata, config, traces, and outcome | `TrainingRunReceipt v0.1` (candidate) + `ControlledRunContract` (candidate) | `HUMMBL_INTERPRETATION` + `SOURCE_CLAIM` | No canonical run-run boundary schema, no no-claim-without-run validation yet | Publish candidate receipt format with dataset refs, run hashes, evaluator IDs, and immutable state transitions |
| TraceReceipt | Receipts capturing ordered execution/learning trace entries across runs and evals | `TraceReceipt v0.1` + `TrainingRunReceipt` (candidate) | `HUMMBL_INTERPRETATION` | Ordering, immutability, and attestation semantics are not yet standardized in repo | Define bounded trace receipt schema with run ID, step hash chain, actor, action context, and consent flag |
| EnvironmentContract | Contract describing dataset, harness, context, tools, and rubric inputs | `Governed EnvironmentContract v0.1` (candidate) | `HUMMBL_INTERPRETATION` + `SOURCE_CLAIM` | Missing explicit schema and enforcement semantics | Draft candidate contract artifact and tie each field to source receipts |
| Specialist subagent | Task-scoped agent optimized for a narrow workflow (e.g., spreadsheet retrieval) | `Specialist Subagent Assurance Profile` (candidate) | `SOURCE_CLAIM` mapped | Scope, rollback, and authority boundaries are not yet operationally defined | Define subagent contract including scope, allowed tools, and consent surface |
| Continual learning | Ongoing optimization/update loop after deployment | `RuntimeVendor Watchlist` + `consent-gated training` boundary (candidate) | `HUMMBL_INTERPRETATION` | No direct source artifact for consent or opt-in policy controls in this packet | Require explicit consent model + local policy audit before any adoptive reuse |
| Production learning loop | Update/deployment cycle in production-like environments | `TrainingRunReceipt` + deployment control receipt (candidate) | `HUMMBL_INTERPRETATION` | Runtime boundary and rollback semantics are not yet proven by this packet | Add pre- and post-deploy evidence receipts with local audit checkpoints |
| Compute substrate | Compute platforms and capacity used for RL and eval workflows (3090/4090/5090/A100/H100/H200/B200 mentions) | `Runtime/infra precondition` + resource attestation (candidate) | `SOURCE_CLAIM` + `LOCAL_AUDIT_REQUIRED` | Hardware capability and local feasibility are only partially source-verified | Verify local capability envelope before treating as architecture dependency |
| Hosted training | External or managed training services versus local execution | `RuntimeVendor Watchlist` + `HostedRunReceipt` (candidate) | `SOURCE_CLAIM` / `HUMMBL_INTERPRETATION` | Hosted workflow boundaries and data-leak controls not captured in source claims | Require vendor disclosure, data handling contract, and local legal/privacy audit before adoption |
| PI-SA-2026-001 | Funding and owned-model optimization thesis | Evidence spine + strategy posture marker | `SOURCE_CLAIM` recorded | Financial framing lacks corroborated canonical metric baseline | Add immutable source links and keep interpretation bounded |
| PI-SA-2026-002 | Owned-optimization thesis in Stack/positioning | `governed sourceType` marker in contract surface | `SOURCE_CLAIM` recorded | No direct control policy or consent text in source | Mark as interpretive input only; no adoption |
| PI-SA-2026-003 | Compute, RL, environments, sandboxes, evals, deployment | Stack decomposition for receipt boundaries | `SOURCE_CLAIM` recorded | Missing explicit interface and handoff contracts | Recommend `EnvironmentContract`/`EvalReceipt` schema draft |
| PI-SA-2026-004 | Scale signals (customers and annualized revenue) | Organizational impact context (non-normative) | `SOURCE_CLAIM` recorded | No governance rule binding this metric | Keep as business context; do not route as architecture control |
| PI-RAMP-001 | Specialist spreadsheet retrieval subagent | `Specialist Subagent Assurance Profile` (candidate) | `SOURCE_CLAIM` recorded | No local reproduction package or run artifact | Add local reproduction manifest before use |
| PI-RAMP-002 | FastAsk benchmark outperforms Claude Opus 4.6 | Performance evidence envelope for subagent claims | `SOURCE_CLAIM` recorded | No independent benchmark rerun | LOCAL_AUDIT_REQUIRED |
| PI-VER-001 | Verifiers: dataset + harness + reward/rubric | `EnvironmentContract` / `receipt boundary` candidate | `SOURCE_CLAIM` recorded | Not yet modeled as a required schema field set | Draft contract template with required source links |
| PI-VER-002 | Verifiers usable for RL, evals, synthetic data, harness experiments | `EvalReceipt` + eval provenance pattern (candidate) | `SOURCE_CLAIM` recorded | No enforcement semantics for eval chain | Add audit rule for eval provenance completeness |
| PI-RL-001 | PRIME-RL requires NVIDIA GPU | `Runtime/infra precondition` gate | `SOURCE_CLAIM` + LOCAL_AUDIT_REQUIRED | No in-repo hardware validation evidence | Run local repo-level environment check before adoption |
| PI-RL-002 | RTX 3080 Ti local feasibility unverified | `LOCAL_AUDIT_REQUIRED` gate | `LOCAL_AUDIT_REQUIRED` | No feasibility test executed locally | Execute bounded local check on approved operator hardware |

## Interpretation guardrails
- This is not canonicalized HUMMBL/BaseN/Ownward architecture.
- No dependency or terminology adoption.
- `DO_NOT_ADOPT_YET` applies until operator-approved verification passes and explicit receipt-linked review.

## Source artifacts
- See `docs/intelligence/prime-intellect-series-a-2026-07-08.md`
- See `docs/prime-intellect-owned-optimization-loop-architecture-watch-2026-07-08.md`
