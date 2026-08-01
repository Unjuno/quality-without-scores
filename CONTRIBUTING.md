# Contributing

Contributions are welcome from any discipline. This repository does not require code, a trained model, or a completed experiment. A well-specified hypothesis, prior-art correction, domain warning, negative result, evaluation proposal, or link to an implementation is useful.

## License of contributions

By submitting a contribution, you agree to dedicate that contribution to the public domain under the [CC0 1.0 Universal Public Domain Dedication](LICENSE), to the extent legally possible.

Do not submit text, figures, datasets, or other material that you do not have the right to contribute.

## Before adding a candidate

A candidate should answer five basic questions:

1. What quality is difficult to score directly?
2. What controlled operation is hypothesized to make a good example worse along that axis?
3. What evidence supports the direction of that operation?
4. What meaning, function, fact, constraint, or intent must remain unchanged?
5. What result would show that the idea is not useful?

Ideas that are merely ordinary noise removal are still relevant as comparisons, but the main catalog prioritizes interpretable, directional degradation.

## Evidence labels

Use one or more of the following labels for every cited source:

- `[peer-reviewed journal]`
- `[peer-reviewed proceedings]`
- `[accepted / forthcoming]`
- `[preprint]`
- `[dataset]`
- `[official tool or documentation]`
- `[official product page]`
- `[secondary source]`
- `[unverified]`

When uncertain, use the weaker label and explain the uncertainty. A product page demonstrates product claims, not independent effectiveness. A preprint demonstrates an available research claim, not settled evidence.

## Review-status labels

Use one of:

- `literature-scoped` — sources were reviewed, but no specialist has approved the entry;
- `domain-review-needed` — specialist review is required before strong claims;
- `domain-reviewed` — a named specialist or review process has checked the entry;
- `prior-art-disputed` — novelty or coverage is actively contested;
- `experiment-proposed` — a falsifiable protocol has been specified;
- `negative-result-reported` — an attempted test did not support the hypothesis;
- `prototype-reported`;
- `paper-published`;
- `product-reported`;
- `open-source-implementation`.

Status labels describe evidence, not enthusiasm.

## Candidate template

Copy this template into an issue or pull request.

```markdown
## Candidate name

### Domain

### Difficult-to-score quality
What form of quality is being represented? State the audience, objective, or context.

### Good source artifacts
Where could relatively good examples come from? What evidence supports using them as sources? Are multiple valid good examples available?

### Directional degradation operator
Describe the exact operation. Include multiple implementations where feasible.

### Operator-direction evidence
How will you establish that the transformation is usually worse for the stated intent?
Describe blinded A/B validation, domain evidence, agreement thresholds, and rejection criteria.

### Preserved invariants
What must not change: meaning, behavior, facts, geometry, legal effect, biological properties, audience intent, or something else?
How will each invariant be checked?

### Learned improvement task
What should the model predict: a full artifact, ranked edits, edit script, critique, constraints, quality axis, or severity?
Include no-edit and abstention behavior.

### Automatic generation
How could paired data be generated at scale without leaking operator identity?

### Independent verification
How would improvement be checked without reusing the same heuristic that generated the degradation?

### Natural failure mode
What real-world failure resembles this degradation? Where will natural examples come from?

### Baselines
Include deterministic reversal, domain rules, proxy optimization, generic models, and exact algorithms where relevant.

### Shortcut risk
What superficial signature might the model learn instead of the intended quality concept?

### Falsifiable test
State the smallest experiment that could support the hypothesis.

### Kill criterion
What result should cause the candidate to be rejected or substantially downgraded?

### Prior work and evidence type
Label every paper, dataset, tool, and product by evidence type. State clearly what is already established.

### Practical or scientific value
Who benefits if the inverse task works?

### Safety and ethics
Who could be harmed? Is the output advisory or executable? What review, restrictions, or rollback are required?

### Provisional triage
- Generation: High / Medium / Low / Unknown
- Verification: High / Medium / Low / Unknown
- Impact: High / Medium / Low / Unknown
- Confidence: High / Medium / Low
- Review status:
- Rationale:
- Date reviewed:
```

## Quality standards

A useful contribution should:

- define one quality axis rather than “make it better”;
- describe an operational degradation;
- validate the degradation direction rather than assume it;
- identify invariants and failure conditions;
- acknowledge multiple valid outputs;
- include no-edit or abstention when appropriate;
- separate known facts, source claims, and speculation;
- label evidence maturity;
- avoid blanket novelty claims;
- propose held-out operators and natural-failure evaluation;
- compare with rules and exact algorithms;
- state a falsifiable test and kill criterion;
- report confidence and domain-review status;
- state domain risks honestly.

## Prior-art corrections

Corrections are especially valuable. When an idea is already explored:

1. add the strongest primary sources;
2. label their evidence type;
3. explain what the work already demonstrates;
4. narrow or remove the claimed open gap;
5. mark the entry `established-pattern` or `prior-art-disputed` where appropriate.

Do not preserve a candidate merely to maintain a list length. Removing or downgrading an idea is a valid contribution.

## Negative results

Negative results are encouraged. Useful reports include:

- the operator could not be validated as directionally worse;
- a rule-based inverse matched the learned model;
- the model failed on held-out operators;
- synthetic gains did not transfer to natural failures;
- invariant violations made the task unsafe;
- exact optimization made machine learning unnecessary.

A concise negative report can prevent duplicated effort.

## High-stakes domains

Medical, legal, biological, public-policy, safety, and security applications require additional care.

Contributions in these areas should explicitly state:

- whether outputs are advisory or executable;
- what expert review is required;
- which invariants cannot be checked automatically;
- privacy, consent, and data-governance constraints;
- consequences of an incorrect repair;
- deployment restrictions;
- whether synthetic degradation creates unsafe examples.

This catalog is not professional medical, legal, scientific, or engineering advice.

## Scope

Relevant contributions include:

- new application hypotheses;
- rejection or downgrading of existing candidates;
- refinements to degradation operators;
- operator-validation studies;
- better invariant checks;
- prior-art references and evidence corrections;
- evaluation and falsification designs;
- negative results;
- links to independent implementations, datasets, papers, or products;
- translations and accessibility improvements.

The repository intentionally does not require a central implementation. Independent implementations may use any license or business model.