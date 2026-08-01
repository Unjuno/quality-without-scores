# Evaluation and Falsification Protocol

This document provides a common way to compare candidate applications and evaluate experiments. It is designed to prevent attractive demonstrations from being mistaken for evidence that a model learned the intended quality concept.

## 0. What “without scores” does not mean

This method does not eliminate evaluation. It attempts to reduce dependence on manually assigned scalar labels during training.

A credible project still needs:

- evidence that the degradation is directionally worse under a stated intent;
- invariant checks;
- natural-failure evaluation;
- independent human or domain assessment where automatic checks are weak;
- a clear condition under which the hypothesis should be rejected.

## 1. Operator validation is a prerequisite

Before generating a large training set, validate the degradation operator itself.

For a proposed operator `D_k` and source artifact `y`, compare `y` with `D_k(y)` under an explicit intent and audience.

A minimum validation protocol should include:

1. blinded original-versus-degraded comparisons;
2. multiple source artifacts and operator strengths;
3. independent raters or domain evidence;
4. agreement and uncertainty reporting;
5. rejection of operators that are not reliably directional;
6. checks that required invariants remain unchanged.

Do not assume that common design advice, readability rules, normalization heuristics, or natural-source status automatically establishes a universal quality direction.

### Operator admission rule

An operator should enter the training generator only when:

- the intended quality axis is named;
- the audience or context is specified;
- the degradation direction is supported beyond the generator author's assertion;
- invariant violations are below a predeclared threshold;
- the operator has more than one implementation, where feasible, to reduce fingerprinting.

## 2. Candidate triage

Use qualitative labels unless there is evidence for precise estimates.

| Dimension | Low | Medium | High | Unknown |
|---|---|---|---|---|
| Source availability | Rare, private, or expensive | Moderate collection effort | Abundant or generatable | Not assessed |
| Degradation automation | Mostly manual | Partially automatic | Fully automatic at scale | Not assessed |
| Invariant preservation | Hard to guarantee | Checkable with caveats | Strong automatic checks | Not assessed |
| Inverse difficulty | Simple rule reversal | Context required | Substantial judgment or search | Not assessed |
| Independent verification | Mainly subjective | Mixed automatic and human | Cheap, strong, independent | Not assessed |
| Distribution realism | Artificial failure only | Partial overlap | Close to natural failures | Not assessed |
| Practical impact | Narrow research interest | Specialist utility | Broad scientific or commercial value | Not assessed |
| Compactness | Large multimodal artifacts | Manageable with preprocessing | Short structured representations | Not assessed |
| Safety risk | High and difficult to contain | Requires expert governance | Low-risk and reversible | Not assessed |

Every estimate should include:

- **confidence:** Low, Medium, or High;
- **rationale:** one or two sentences;
- **review status:** `literature-scoped`, `domain-review-needed`, or `domain-reviewed`;
- **date reviewed.**

Do not collapse all dimensions into one universal ranking. If numeric weights are used, publish the weights, rationale, and uncertainty.

## 3. Required dataset splits

A serious evaluation should separate at least five conditions.

### 3.1 Seen-operator interpolation

New source artifacts degraded by operator families seen during training.

This is the easiest condition and is insufficient by itself.

### 3.2 Unseen-parameter generalization

Known operator families with unseen strengths, positions, combinations, or parameter distributions.

### 3.3 Unseen-implementation generalization

The same degradation concept implemented through a different generator or rendering path.

This helps detect reliance on serialization, formatting, or renderer fingerprints.

### 3.4 Unseen-operator-family generalization

A held-out family of degradations targeting the same quality axis.

This is important evidence against simple operator reversal.

### 3.5 Natural-failure transfer

Real low-quality artifacts not produced by the generator.

This is the most important test. Synthetic performance without natural-failure transfer does not demonstrate useful quality learning.

## 4. Baselines

At minimum, compare against:

1. **No change** — preserves the degraded artifact.
2. **Known inverse** — applies the deterministic reverse of the generator where available.
3. **Rule-based repair** — applies conventional domain heuristics.
4. **Proxy optimization** — directly optimizes available quality metrics.
5. **Generic pretrained model** — prompted or fine-tuned without degradation pairs.
6. **Pairwise preference model** — learns preferences without reconstructive supervision.
7. **Search or exact optimization** — required where formal algorithms already exist.
8. **Human or expert revision**, where feasible.

The method is compelling only when it adds value beyond known reversal, ordinary rules, and established optimization.

## 5. Core outcomes

Every experiment should report distinct outcomes rather than a single aggregate score.

### 5.1 Directional improvement

Did the target quality axis improve under independent evaluation?

Possible measures include task completion, comprehension, scan path, maintainability, cycle time, expression yield, developer acceptance, or expert pairwise judgment.

### 5.2 Invariant preservation

Did meaning, behavior, facts, data, geometry, legal effect, biological properties, or safety constraints remain unchanged?

Report invariant failures separately. Do not average them away with quality gains.

### 5.3 Edit efficiency

How much changed to obtain the improvement?

Useful measures include edit distance, changed tokens, changed area, number of operations, or affected components.

### 5.4 Calibration, no-edit behavior, and abstention

Can the model identify cases where no change is needed or where it lacks sufficient confidence?

A model that always edits can damage already-good artifacts.

### 5.5 Diversity of valid improvements

When multiple outputs are valid, does the system support alternatives rather than forcing imitation of the source artifact?

## 6. Pairwise human evaluation

When absolute quality is hard to score, use a question tied to explicit intent:

> Which version better satisfies the stated intent while preserving the listed constraints?

A human study should:

- randomize order;
- hide source and system identity;
- include unchanged controls;
- measure inter-rater agreement;
- report ties and uncertainty;
- separate preference from invariant violations;
- include domain specialists for high-stakes claims.

A preference for the original source does not prove global optimality. It only supports the direction for that context and task.

## 7. Multiple valid outputs

Exact reconstruction should not be the sole metric when several improvements are valid.

Prefer one or more of:

- constraint satisfaction;
- task success;
- expert pairwise preference;
- semantic equivalence;
- execution or simulation;
- proof, type, or formula checking;
- agreement at the quality-axis or edit-intent level;
- diversity among valid solutions.

## 8. Operator-fingerprint tests

To test whether the model learned superficial cues:

- randomize irrelevant formatting;
- implement the same degradation concept in several ways;
- remove metadata revealing operator identity;
- hold out whole operator families;
- mix real and synthetic failures;
- include adversarial examples where the usual fingerprint is present but no repair is needed;
- include examples with the target problem but without familiar fingerprints;
- test across source generators, renderers, projects, institutions, or datasets.

## 9. Source-quality tests

The original artifact should not automatically be treated as globally optimal.

Recommended controls:

- independent review of the source set;
- multiple good references for the same task;
- a no-edit option;
- comparison with alternative expert revisions;
- exclusion of artifacts whose quality depends on hidden context;
- conditioning on audience, user, host organism, jurisdiction, or objective;
- sensitivity analysis when the source is only weakly supported as “good.”

## 10. Circular-evaluation audit

For every metric, state whether it was used to:

- choose source examples;
- generate degradations;
- filter training pairs;
- train the model;
- select checkpoints;
- evaluate the final result.

A metric used throughout the pipeline cannot serve as the only independent evidence of quality improvement.

## 11. Predeclared falsification and kill criteria

Before training, write down outcomes that would make the candidate unpromising.

A useful kill criterion is specific and costly to explain away. Examples:

- no improvement over deterministic reversal;
- no transfer to natural failures;
- success only on seen operator fingerprints;
- invariant failures above a safety threshold;
- human evaluation disagrees with proxy metrics;
- exact algorithms outperform the learned approach at lower cost;
- gains vanish when source imitation is removed from the metric;
- the operator cannot be validated as directionally worse.

Negative results should remain useful contributions to the catalog.

## 12. Safety gates

Extra review is required for medicine, law, biology, public policy, safety engineering, and other high-stakes domains.

A candidate should state:

- who could be harmed by an incorrect repair;
- which invariants cannot be reliably checked;
- whether the output is advisory or executable;
- required expert review;
- privacy and data-governance constraints;
- whether generated degradations could themselves create unsafe artifacts;
- deployment restrictions and rollback mechanisms.

The catalog is a source of research hypotheses, not professional advice or deployment authorization.

## 13. Minimum evidence for a convincing result

A strong project should show all of the following:

1. Validated degradation direction.
2. Automatic generation of controlled pairs.
3. Explicit invariant checks.
4. Improvement over known reversal, rules, and relevant exact algorithms.
5. Generalization to unseen parameters and implementations.
6. At least one held-out operator family.
7. Transfer to naturally occurring failures.
8. Independent human or domain evaluation.
9. Analysis of unnecessary or harmful edits.
10. Results against predeclared kill criteria.

Without items 6 and 7, the result is primarily evidence of synthetic operator inversion, not general quality improvement.