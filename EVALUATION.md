# Evaluation and Scorecard

This document provides a common way to compare candidate applications and to evaluate eventual experiments. It is designed to prevent attractive demonstrations from being mistaken for evidence that a model learned the intended quality concept.

## 1. Candidate scorecard

Score each dimension from 1 to 5. Scores should be accompanied by a brief justification and treated as provisional.

| Dimension | 1 | 3 | 5 |
|---|---|---|---|
| Source availability | Rare, private, or expensive | Moderate collection effort | Abundant or generatable |
| Degradation automation | Mostly manual | Partially automatic | Fully automatic at scale |
| Invariant preservation | Hard to guarantee | Checkable with caveats | Strong automatic checks |
| Inverse difficulty | Simple rule reversal | Some context required | Requires substantial judgment or search |
| Independent verification | Mainly subjective | Mixed automatic and human | Cheap, strong, independent verification |
| Distribution realism | Artificial failure only | Partial overlap with real failures | Closely matches naturally occurring failures |
| Practical impact | Limited research value | Useful specialist workflow | Broad scientific, social, or commercial value |
| Novelty room | Crowded and solved | Open variants remain | Clear underexplored framing |
| Compactness | Large multimodal artifacts | Manageable with preprocessing | Short structured representations |
| Safety and domain risk | High-stakes and hard to review | Containable with expert review | Low-risk or easily reversible |

## 2. Recommended ranking views

Do not collapse every dimension into one universal score. Different contributors have different constraints.

Useful views include:

- **Best method demonstration** — high visual or conceptual clarity
- **Easiest experiment** — high automation, compact representation, cheap verification
- **Highest impact** — strong practical or scientific value
- **Most novel** — substantial differentiation from established methods
- **Safest** — low cost of incorrect output
- **Best human-AI collaboration task** — automatic checks plus meaningful expert judgment

If a total score is needed, publish the weights. A reasonable default for exploratory work is:

```text
20% degradation automation
15% invariant preservation
15% inverse difficulty
15% independent verification
15% distribution realism
15% practical impact
5% compactness
```

Novelty and safety should normally be reported separately rather than hidden inside the total.

## 3. Dataset split requirements

A serious evaluation should separate at least four conditions.

### 3.1 Seen-operator interpolation

New source artifacts degraded by operator families seen during training.

This measures ordinary generalization but is the easiest condition.

### 3.2 Unseen-parameter generalization

Known operator families with unseen strengths, positions, combinations, or parameter distributions.

### 3.3 Unseen-operator generalization

A held-out family of degradations targeting the same quality axis.

This is important evidence against simple operator reversal.

### 3.4 Natural-failure transfer

Real low-quality artifacts not produced by the generator.

This is the most important test. Synthetic performance without natural-failure transfer does not demonstrate useful quality learning.

## 4. Baselines

At minimum, compare against:

1. **No change** — preserves the degraded artifact.
2. **Rule reversal** — applies known deterministic fixes.
3. **Quality heuristic optimization** — directly optimizes available proxy metrics.
4. **Generic pretrained model** — prompted or fine-tuned without the degradation pairs.
5. **Pairwise preference model** — learns only which item is preferred.
6. **Human or expert revision**, where feasible.

The method is most compelling when it improves over rule reversal and transfers to natural failures.

## 5. Core metrics

Every experiment should measure four distinct outcomes.

### 5.1 Improvement

Did the target quality axis improve?

Possible measures include pairwise preference, task completion, readability, scan path, cycle time, comprehension, maintainability, or domain-specific utility.

### 5.2 Invariant preservation

Did meaning, behavior, data, constraints, or legal and biological properties remain unchanged?

This should be reported independently from quality improvement.

### 5.3 Edit efficiency

How much was changed to obtain the improvement?

Useful measures include edit distance, number of operations, changed area, changed tokens, or number of affected components.

### 5.4 Calibration and abstention

Can the model identify cases where no change is needed or where it is uncertain?

An improvement model that always edits can damage already-good artifacts.

## 6. Pairwise evaluation

When absolute quality is hard to score, pairwise evaluation is often more reliable.

Ask an evaluator:

> Which version better satisfies the stated intent while preserving the required constraints?

The intent and constraints must be shown explicitly. Otherwise, pairwise preferences may reflect taste rather than task quality.

For human studies, randomize order, hide the source label, measure agreement, and include unchanged controls.

## 7. Multiple valid outputs

Exact reconstruction should not be the sole metric when several improvements are valid.

Prefer one or more of:

- constraint satisfaction;
- task success;
- expert pairwise preference;
- semantic equivalence;
- execution or simulation;
- proof or type checking;
- edit-plan agreement at the level of quality axes rather than exact coordinates;
- diversity among valid solutions.

## 8. Operator-fingerprint tests

To test whether the model learned superficial cues:

- randomize irrelevant formatting;
- create several implementations of the same degradation concept;
- remove metadata revealing operator identity;
- hold out entire operator families;
- mix real and synthetic failures;
- test adversarial examples where the usual fingerprint is present but no repair is needed;
- test examples with the target problem but without the familiar fingerprint.

## 9. Source-quality tests

The original artifact should not automatically be treated as globally optimal.

Recommended controls:

- independent review of the source set;
- multiple good references for the same task;
- a no-edit option;
- comparison against alternative expert revisions;
- exclusion of artifacts whose quality depends on hidden context;
- conditioning on audience, user, host organism, jurisdiction, or design objective.

## 10. Safety gates

Extra review is required for medicine, law, biology, public policy, safety engineering, and other high-stakes domains.

A candidate should state:

- who could be harmed by an incorrect repair;
- which invariants cannot be reliably checked;
- whether the output is advisory or executable;
- the required expert review;
- privacy and data-governance constraints;
- whether synthetic degradation could create unsafe examples.

The catalog is a source of research ideas, not a claim that every candidate should be deployed.

## 11. Minimum evidence for a convincing result

A strong project should show all of the following:

1. Automatic generation of controlled degradation pairs.
2. Explicit invariant checks.
3. Improvement over a generic model and rule-based reversal.
4. Generalization to unseen operator parameters.
5. At least one held-out operator family.
6. Transfer to naturally occurring failures.
7. Independent human or domain evaluation.
8. Analysis of unnecessary or harmful edits.

Without items 5 and 6, the result is primarily evidence of synthetic operator inversion, not general quality improvement.