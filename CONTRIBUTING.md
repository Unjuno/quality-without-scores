# Contributing

Contributions are welcome from any discipline. This repository does not require code, a trained model, or a completed experiment. A well-specified idea, prior-art correction, domain warning, evaluation proposal, or link to an implementation is useful.

## License of contributions

By submitting a contribution, you agree to dedicate that contribution to the public domain under the [CC0 1.0 Universal Public Domain Dedication](LICENSE), to the extent legally possible.

Do not submit text, figures, datasets, or other material that you do not have the right to contribute.

## Before adding an idea

A candidate should answer four basic questions:

1. What quality is difficult to score directly?
2. What controlled operation reliably makes a good example worse along that quality axis?
3. What meaning, function, fact, constraint, or intent must remain unchanged?
4. How could an independent evaluator tell whether the learned inverse is genuinely useful?

Ideas that are merely ordinary noise removal are still relevant as comparisons, but the main catalog prioritizes directional and interpretable degradation.

## Idea template

Copy this template into an issue or pull request.

```markdown
## Candidate name

### Domain

### Difficult-to-score quality
What form of quality is being represented?

### Good source artifacts
Where could relatively good examples come from? Why are they good enough to use as sources?

### Directional degradation operator
Describe the exact operation that moves the artifact in a worse direction.

### Preserved invariants
What must not change: meaning, behavior, facts, geometry, legal effect, biological function, audience intent, or something else?

### Learned inverse task
What should the model predict: a full artifact, edit script, ranked fixes, critique, constraints, or quality severity?

### Automatic generation
How could paired data be generated at scale?

### Independent verification
How would improvement and invariant preservation be checked without reusing the same heuristic that generated the degradation?

### Natural failure mode
What real-world failure resembles this synthetic degradation?

### Main shortcut risk
What superficial signature or deterministic reversal might the model learn instead of the intended quality concept?

### Prior work
List related datasets, methods, papers, products, or exact algorithms. State clearly what is already established.

### Practical or scientific value
Who benefits if the inverse task works?

### Safety and ethics
Who could be harmed by an incorrect output? What review or restrictions are necessary?

### Provisional ratings
- Generation: /5
- Verification: /5
- Impact: /5
- Feasibility: /5
```

## Quality standards

A useful contribution should:

- define one specific quality axis rather than “make it better”;
- describe an executable or at least operational degradation;
- identify invariants and failure conditions;
- acknowledge multiple valid outputs;
- separate known facts from speculation;
- avoid claiming novelty without a prior-art search;
- propose evaluation on naturally occurring failures;
- state domain risks honestly.

## Prior-art corrections

Corrections are especially valuable. If a listed idea is already well explored, add the relevant work and explain whether any narrower open question remains.

Do not remove a candidate merely because prior work exists. The catalog may still benefit from documenting that the method is established in one domain and underexplored in another.

## Status labels

Ideas may be described with one of the following statuses:

- `idea-only`
- `prior-art-needed`
- `established-pattern`
- `open-research-question`
- `prototype-reported`
- `paper-published`
- `product-reported`
- `open-source-implementation`

Status labels should describe evidence, not enthusiasm.

## High-stakes domains

Medical, legal, biological, public-policy, safety, and security applications require additional care.

Contributions in these areas should explicitly state:

- whether outputs are advisory or executable;
- what expert review is required;
- which invariants cannot be checked automatically;
- privacy, consent, and data-governance constraints;
- the consequences of an incorrect repair.

This catalog is not professional medical, legal, scientific, or engineering advice.

## Scope

Relevant contributions include:

- new application ideas;
- refinements to an existing degradation operator;
- better invariant checks;
- negative examples where the method is unsuitable;
- prior-art references;
- evaluation designs;
- links to independent implementations, datasets, papers, or products;
- translations and accessibility improvements.

The repository intentionally does not require a central implementation. Independent implementations may use any license or business model.