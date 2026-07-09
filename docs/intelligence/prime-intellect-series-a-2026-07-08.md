# Prime Intellect Series A (2026-07-08) — Bounded Receipt

## Receipt metadata
- Receipt ID: `prime-intellect-series-a-2026-07-08`
- Date observed: `2026-07-08`
- Source anchor date: `2026-07-08`
- Repo: `hummbl-dev/ai-source-verification`
- Working branch: `docs/codex/issue-5-readme-clarity`
- Output kind: `bounded source packet receipt`

## Posture and boundary
- `SOURCE_CLAIM`: used for Prime-supplied claims and cited primary artifacts.
- `EXTERNALLY_REPORTED`: used where claims appear in external media coverage.
- `LOCAL_AUDIT_REQUIRED`: local feasibility checks that remain unexecuted.
- `HUMMBL_INTERPRETATION`: non-canon mapping used for governance architecture planning.
- `DO_NOT_ADOPT_YET`: explicit adoption guardrail for any tool, stack, or term.

## Source posture table
| Source | Posture | Verification status | Notes |
| --- | --- | --- | --- |
| Prime Intellect Series A announcement | `SOURCE_CLAIM` | `SOURCE_RECORDED` | $130M Series A; led by Radical Ventures; participation includes NVIDIA Ventures, Intel Capital, Dell Technologies Capital, and existing investors; total funding reported above $150M |
| Prime Intellect Ramp case study | `SOURCE_CLAIM` | `SOURCE_RECORDED` | FastAsk benchmark claims: +27% faster, +4 exact-match points vs Claude Opus 4.6; 14 finance task types in Ramp Sheets RL environment |
| PrimeIntellect-ai/verifiers | `SOURCE_CLAIM` | `SOURCE_RECORDED` | Environments include dataset inputs, harnesses, tools/sandboxes/context, and reward/rubric surfaces; used for RL training/evals/synthetic data/harness experimentation |
| PrimeIntellect-ai/prime-rl | `SOURCE_CLAIM`, `LOCAL_AUDIT_REQUIRED` | `SOURCE_RECORDED` | Publicly states at least one NVIDIA GPU required and named hardware list; RTX 3080 Ti feasibility not yet locally verified |
| Prime Intellect public positioning on owned optimization | `HUMMBL_INTERPRETATION` | `INTERPRETATION_RECORDED` | Architecture mapping only; candidate wedge is governed optimization loops with receipts and trace/audit boundaries |

## Primary source list
- Prime Intellect Series A announcement (source claim; `Date observed: 2026-07-08`)
- Prime Intellect Ramp case study (source claim; `Date observed: 2026-07-08`)
- `PrimeIntellect-ai/verifiers` GitHub repository (source claim; `Date observed: 2026-07-08`)
- `PrimeIntellect-ai/prime-rl` GitHub repository (source claim + hardware posture; `Date observed: 2026-07-08`)

## Key claims table
| claim_id | claim | source | posture | confidence | HUMMBL relevance | action |
| --- | --- | --- | --- | --- | --- | --- |
| PI-SA-2026-001 | $130M Series A led by Radical Ventures with participation from NVIDIA Ventures, Intel Capital, Dell Technologies Capital, and existing investors; total funding above $150M; RL framing as owned optimization loop for workflow-specific performance | Prime Intellect Series A announcement | `SOURCE_CLAIM` | `medium` | Candidate: tests hypothesis that ownership claims map to controlled optimization loops (non-canonical) | `record` |
| PI-SA-2026-003 | Prime stack positioning spans compute, RL, environments, sandboxes, evals, deployment | Prime Intellect Series A announcement | `SOURCE_CLAIM` | `medium` | Candidate architecture mapping for stack boundary decomposition | `record` |
| PI-SA-2026-004 | 6k+ customers and over $100M annualized revenue | Prime Intellect Series A announcement | `SOURCE_CLAIM` | `medium` | Financial scale context for governance architecture impact assumptions | `record` |
| PI-RAMP-001 | Ramp trained specialist spreadsheet retrieval subagent; benchmark claims include +27% faster and +4 exact-match points vs Claude Opus 4.6 in spreadsheet workflow context | Prime Intellect Ramp case study | `SOURCE_CLAIM` | `low` | Supports candidate for specialist subagent validation pathways under evidence constraints | `local verify required` |
| PI-RAMP-002 | FastAsk reported better/faster than Claude Opus 4.6 on cited benchmark (27% faster; +4 exact-match points) | Prime Intellect Ramp case study | `SOURCE_CLAIM` | `low` | Supports candidate for specialist subagent benchmarking assumptions in managed optimization loops | `local verify required` |
| PI-VER-001 | Verifiers environment = dataset + harness + reward/rubric | `PrimeIntellect-ai/verifiers` repository | `SOURCE_CLAIM` | `high` | Core mapping anchor for environment contract/watchdog candidates | `record` |
| PI-VER-002 | Environments usable for RL, evals, synthetic data, harness experimentation | `PrimeIntellect-ai/verifiers` repository | `SOURCE_CLAIM` | `high` | Supports evidence-preserving mapping for environment-driven eval and training controls | `record` |
| PI-RL-001 | PRIME-RL requires at least one NVIDIA GPU | `PrimeIntellect-ai/prime-rl` repository | `SOURCE_CLAIM`, `LOCAL_AUDIT_REQUIRED` | `medium` | Feasibility gate for deployment and audit boundary design | `LOCAL_AUDIT_REQUIRED` |
| PI-RL-002 | RTX 3080 Ti local feasibility unverified | `PrimeIntellect-ai/prime-rl` repository | `LOCAL_AUDIT_REQUIRED` | `low` | Clarifies local capability boundary for feasibility follow-up and audit scope | `LOCAL_AUDIT_REQUIRED` |
| K6 | Strategic interpretation: potential shift from leasing generic frontier behavior to owning workflow-specific optimization loops; candidate HUMMBL wedge is governed, receipt-backed optimization loop with consent/audit boundaries | Prime Intellect public positioning + source synthesis | `HUMMBL_INTERPRETATION` | `low-medium` | Core mapping hypothesis under this receipt, not canon | `interpretation only` |

## Primary source posture retained
1. **Series A announcement** (`SOURCE_CLAIM`) — preserves claims of $130M Series A, led by Radical Ventures, participation from NVIDIA Ventures/Intel Capital/Dell Technologies Capital and existing investors, and total funding above $150M.
2. **Positioning claim** (`SOURCE_CLAIM`) — RL as the mechanism for organizations to own workflow-specific optimization loops across compute, RL scale, environments, sandboxes, evals, and deployment.
3. **Ramp deployment claim** (`SOURCE_CLAIM`) — FastAsk, spreadsheet specialist subagent with reported 27% faster performance and 4+ exact-match points above Claude Opus 4.6, 14 finance task types, 3 tools, 15 turns for workbook navigation.
4. **Verifiers repository claim** (`SOURCE_CLAIM`) — environment primitives include dataset inputs, harness, tool/sandbox/context surfaces, and reward/rubric; environments used for RL, evals, synthetic data, and harness experimentation.
5. **Prime-RL claim + hardware envelope** (`SOURCE_CLAIM`, `LOCAL_AUDIT_REQUIRED`) — PRIME-RL requires one NVIDIA GPU; named development/test hardware includes 3090/4090/5090, A100, H100, H200, B200; local RTX 3080 Ti feasibility unverified locally.

## HUMMBL interpretation (bounded)
- Strategic question assessment (bounded): Prime’s public positioning is consistent with a move toward owned workflow-specific optimization loops, but this receipt records **source posture only**; it is not independent validation of HUMMBL architecture correctness.
- Candidate mapping to HUMMBL/BaseN/Ownward: evidence suggests a promising fit for a *governed optimization loop* model (receipt-backed, trace-audited, consent-governed), which remains non-canon until operator approval and local audit.
- Candidate framing phrase kept non-canonical: **Be your own governed lab**.
- Non-adoption guard: no Prime term, method, tool, or stack claim is adopted as HUMMBL canon in this document.

## Verification constraints
- No claim of independent performance validation in this packet.
- No GPU execution or hosted-training runs were performed.
- No private customer data, private workflow data, or operator credentials were used.
- No dependency adoption performed from Prime-owned stack.

## Non-adoption boundary
- `DO_NOT_ADOPT_YET` applies to all Prime-intellect stack claims, terminology, and repo-derived methods until explicitly approved by HUMMBL governance.
- No Prime Intellect repository, framework, term, or benchmark is adopted as canonical HUMMBL/BaseN/Ownward architecture.
- `Be your own governed lab` is preserved as a candidate framing only and is not canonized in this receipt.
- All source claims are preserved as provenance context, not canonical requirements.

## Open questions
- What exact source artifacts (URLs, commit IDs, timestamps) should be attached as immutable primary-source evidence for each table entry?
- Can independent local repository checks confirm `prime-rl` claim-to-code consistency for hardware envelope and any gating logic around RTX 3080 Ti?
- Are there direct source artifacts that define governance or consent boundaries for continual learning in Prime’s runtime docs, separate from marketing phrasing?
- Which HUMMBL/BaseN/Ownward term set should be used to map "owned RL optimization loop" without introducing new canon?
- What minimum receipt fields are required by the destination governance repo for a completed ArchitectureWatch packet?

## Follow-up issues / next actions
- Recommended issues (do not create until explicitly authorized):
  - Governed EnvironmentContract v0.1 — dataset + harness + rubric + receipt boundary
  - EvalReceipt v0.1 — local/hosted eval provenance schema
  - TrainingRunReceipt v0.1 — no-claim-without-run-record
  - Specialist Subagent Assurance Profile v0.1
  - Ownward Voice Runtime Training/Eval Boundary — no continual learning without consent + receipt
  - RuntimeVendor Watchlist v0.1 — Prime Intellect, OpenAI GPT-Live, Anthropic, local NIM
- Next action: run a local, repository-only verification pass for `prime-rl` and `verifiers` artifacts and add explicit immutable source links, then rerun this packet as `verificationStatus: reviewed`.

## Artifacts
- Packet example: `examples/prime-intellect-owned-optimization-loop-verification-2026-07-08.json`
- Architecture watch doc: `docs/prime-intellect-owned-optimization-loop-architecture-watch-2026-07-08.md`
- Receipt companion: `receipts/prime-intellect-owned-optimization-loop-2026-07-08-receipt.md`
