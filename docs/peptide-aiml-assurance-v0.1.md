# Peptide AI/ML Assurance v0.1 — Source Verification, Leakage-Resistant Splits, and Closed-Loop Receipts

**Status: CANDIDATE ASSURANCE PROTOCOL — NO MODEL RELEASE — NON-CANONICAL**

Issue: hummbl-dev/ai-source-verification#19
Parent coordination: hummbl-dev/hummbl-dev#145
Source registry: hummbl-dev/hummbl-bibliography#77
Claim/evidence schema: hummbl-dev/claim-evidence-ledger#8
Ontology/API: hummbl-dev/knowledge-as-code#6

## Objective

Create a reusable assurance protocol for AI/ML work on peptide data. The protocol must prevent literature claims, database annotations, assay labels, generated sequences, and benchmark scores from being treated as interchangeable evidence.

The first phase should define source verification, dataset lineage, split construction, benchmark reporting, model-output posture, and experiment-to-ledger receipts. It should not train or publish a peptide-generation model.

## Primary risks

Peptide datasets are especially vulnerable to:

- exact and near-duplicate sequences
- variants from the same parent scaffold split across train/test
- homologous peptide families spanning splits
- duplicated records with conflicting labels
- incompatible assays collapsed into one target variable
- positive-only databases paired with synthetic negatives
- missing concentration, matrix, pH, salt, serum, species, cell line, route, or time
- publication and patent-selection bias
- labels copied recursively between databases
- uncertain modifications, topology, stereochemistry, or preparation identity
- censored measurements and arbitrary thresholding
- source leakage through embeddings, retrieved context, or foundation-model pretraining
- test-set tuning and benchmark overfitting
- generated candidates evaluated only by correlated predictors

## Required dataset manifest

```yaml
dataset_id:
version:
purpose:
task_definition:
source_records:
source_licenses:
entity_identity_level:
peptidoform_resolution:
assay_families:
label_definition:
units_and_normalization:
missingness_policy:
duplicate_policy:
conflict_policy:
negative_data_posture:
train_validation_test_split:
split_algorithm:
sequence_similarity_thresholds:
scaffold_or_family_groups:
time_cutoff:
source_holdouts:
known_leakage_risks:
exclusions:
preprocessing_code_ref:
checksums:
created_by:
reviewed_by:
as_of:
```

## Required split strategies

- exact-sequence deduplication
- normalized peptidoform deduplication
- sequence-cluster split
- scaffold/parent-series split
- family or homology split
- source/publication split
- assay-laboratory split where metadata permits
- temporal split
- external-dataset holdout

Random splitting may be included only as a diagnostic baseline and must not be presented as the primary generalization result without justification.

## Source verification rules

- Trace every label to an originating source, not only an aggregator database
- Distinguish direct measurement from curator inference and computational prediction
- Record whether multiple database entries ultimately cite the same experiment
- Preserve assay conditions and units before harmonization
- Do not manufacture negatives without labeling the negative-generation method
- Treat absence from a database as unknown, not inactive
- Record retractions, corrections, and superseded records
- Hash and version data snapshots where licensing permits

## Benchmark contract

Every benchmark report must include:

- task and decision relevance
- dataset and split manifests
- identity resolution level
- baseline methods
- metrics with confidence intervals or resampling uncertainty
- calibration results where outputs are probabilistic
- subgroup performance by sequence family, length, topology, modification state, assay family, and source when feasible
- false-positive and false-negative analysis
- out-of-distribution and abstention behavior
- failure examples
- leakage audit
- model, code, environment, and seed receipts
- claim language permitted by the evidence

Do not allow one leaderboard metric to stand in for scientific utility.

## Multi-objective design posture

A peptide candidate may require simultaneous consideration of:

```text
target activity
selectivity
solubility
aggregation
protease stability
permeability or desired extracellular restriction
hemolysis/cytotoxicity
immunogenicity
PK/exposure
synthetic tractability
purification
formulation stability
cost
freedom to operate
```

Represent Pareto trade-offs and uncertainty. Do not collapse these into an opaque scalar without publishing the weighting and sensitivity analysis.

## Prediction / observation boundary

Model outputs must create `Prediction` records. Physical synthesis, identity confirmation, and assays create distinct `Observation` records. A prediction may be linked to later evidence but cannot be rewritten in place as an observation.

Required closed-loop lineage:

```text
hypothesis
→ candidate generation
→ synthesis-feasibility gate
→ physical production
→ identity/purity verification
→ assay with controls
→ atomic observations and claims
→ uncertainty-aware update
→ next-candidate decision
```

## Agent provenance

For any agent-generated dataset transformation, annotation, literature synthesis, or candidate recommendation, record:

- task specification
- model/provider/version if available
- retrieval sources and snapshots
- tools and code versions
- transformation steps
- human/agent review roles
- rejected outputs
- downstream artifacts
- permissions and private/public posture

Agreement among multiple agents using shared sources is not independent replication.

## Adversarial fixtures (10)

1. 95% sequence-identical peptides split across train/test
2. same scaffold with single-residue variants across splits
3. same nominal sequence but different modification or cyclization
4. positive and negative labels from incompatible salt/serum conditions
5. duplicated labels derived from the same paper through different databases
6. synthetic negatives mislabeled as experimentally inactive
7. retrospective threshold chosen after inspecting the test set
8. generated candidate scored by two models trained on overlapping data
9. prediction accidentally emitted as an observed claim
10. model benchmark with no source-license or split receipt

## Acceptance criteria

- [x] Dataset manifest documented (25+ fields)
- [x] 9 split strategies documented
- [x] Source verification rules documented (8)
- [x] Benchmark contract documented (14 items)
- [x] Multi-objective posture documented (14 objectives)
- [x] Prediction/observation boundary documented
- [x] Agent provenance documented (9 fields)
- [x] 10 adversarial fixtures documented
- [ ] Dataset-card and split-manifest schemas are machine-valid
- [ ] Leakage audit detects exact, near-duplicate, scaffold, and family overlap
- [ ] Random split classified as weak diagnostic
- [ ] Direct observations, curated labels, and predictions remain distinguishable
- [ ] Assay incompatibility detected or explicitly waived
- [ ] Negative-data provenance mandatory
- [ ] Benchmark reports include calibration, uncertainty, subgroup, and failure analysis
- [ ] Agent provenance resolves to source and transformation receipts
- [ ] At least one valid and multiple adversarial fixtures included
- [ ] Output claim templates prevent benchmark inflation
- [ ] Independent reviewer performs leakage/source-lineage red-team pass

## Non-goals

- Training a production model
- Generating actionable human-use peptide recommendations
- Declaring benchmark superiority from random splits alone
- Publishing restricted datasets
- Treating model agreement as experimental confirmation
- Creating a single universal developability score

## Cross-repo dependencies

- `hummbl-dev/hummbl-dev#145` — peptide science infrastructure (parent)
- `hummbl-dev/hummbl-bibliography#77` — source registry
- `hummbl-dev/claim-evidence-ledger#8` — claim/evidence schema
- `hummbl-dev/claim-evidence-ledger#9` — seed records
- `hummbl-dev/knowledge-as-code#6` — ontology/API

## Fact posture

This is a candidate assurance protocol derived from issue #19. No model training or release. All schemas, rules, and fixtures are candidate until validated.

## Receipt

- **Issue**: hummbl-dev/ai-source-verification#19
- **Dataset manifest fields**: 25+
- **Split strategies**: 9
- **Source verification rules**: 8
- **Benchmark contract items**: 14
- **Multi-objective dimensions**: 14
- **Adversarial fixtures**: 10
- **Cross-repo deps**: 5
- **Review status**: PENDING
