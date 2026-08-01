# Method

## 1. Problem statement

Many domains contain qualities that experts can recognize but cannot reduce cleanly to a scalar score. Examples include visual hierarchy, explanatory flow, modularity, maintainability, argument structure, and biological design quality.

A direct reward function may be incomplete or misleading. Human labeling may be expensive. However, it may still be possible to define an operation that moves a relatively good artifact in a reliably worse direction along one selected quality axis.

This repository studies that asymmetry.

The method does **not** remove the need for evaluation. It asks whether some manually assigned scalar training labels can be replaced by validated directional transformations.

## 2. Basic formulation

Let:

- `y` be a relatively good artifact;
- `k` be a named quality axis;
- `c` be the relevant context, audience, user, host, or objective;
- `D_k` be a controlled degradation operator for axis `k`;
- `x = D_k(y)` be the degraded artifact;
- `I` be the set of invariants that should remain unchanged;
- `G` be a learned improvement model.

A proposed degradation should preserve the required invariants, as far as the domain permits:

```text
I(x, c) = I(y, c)
```

It should also be supported as directionally worse for the stated context:

```text
P[y is preferred to x | k, c] > threshold
```

This preference does not require a complete scalar quality function. It does require evidence beyond the generator author's assertion.

The model may be trained on pairs, rankings, or edit targets:

```text
G(x, k, c) → improved artifact, ranked edits, constraints, or abstention
```

The original `y` is one reference improvement, not necessarily the only valid output.

## 3. Operator validation

The inequality “the degradation is worse” is a hypothesis, not a definition that becomes true by naming an operator.

Before scaling data generation:

1. specify the quality axis and context;
2. create several operator implementations and strengths;
3. compare original and degraded examples blindly;
4. measure human agreement or independent domain evidence;
5. reject non-directional or context-sensitive operators that cannot be conditioned properly;
6. verify invariants independently;
7. record uncertainty and failure cases.

For objective domains, evidence may come from tests, simulation, formal checking, laboratory measurements, or task success. For subjective domains, pairwise judgment should be tied to a stated intent rather than an undefined notion of universal quality.

## 4. What makes this different from generic corruption

The central object is not arbitrary noise. It is a **named, interpretable, validated directional degradation operator** with an explicit relationship to a quality concept.

Examples:

- Flatten typographic hierarchy while preserving poster content and communication intent.
- Inline a useful helper function while preserving program behavior.
- Replace host-preferred synonymous codons while preserving the amino-acid sequence.
- Remove headings and discourse markers while preserving document propositions.
- Separate related diagram elements while preserving the underlying data.

A useful operator should expose a quality axis, not merely make the input harder to read.

## 5. Three task families

### 5.1 Restoration

The degradation removes or obscures information that can be reconstructed from context.

```text
clean observation → degraded observation → restoration
```

Examples include measurement noise, missing labels, or reduced resolution.

### 5.2 Quality-direction repair

The degradation preserves meaning or function but worsens organization, presentation, or design.

```text
well-organized artifact → validated degradation → constrained improvement
```

This is the primary focus of this repository.

### 5.3 Cheap-forward / hard-inverse generation

A latent solution can be sampled cheaply and mapped forward into an observation, while the inverse problem is difficult.

```text
latent solution → cheap forward transform → difficult inverse task
```

Prime factorization is a clean synthetic example, but practical applications require a reason to use a learned model rather than an existing exact algorithm.

## 6. Candidate admission criteria

A candidate is strong when most of the following hold:

1. **Source availability** — relatively good examples can be collected or generated.
2. **Source support** — there is evidence that the source examples are suitable references.
3. **Operator validation** — the proposed degradation is reliably directional for a stated context.
4. **Automatic degradation** — the operator can be applied at scale.
5. **Invariant preservation** — meaning, function, factual content, or physical constraints remain stable.
6. **Inverse difficulty** — repair requires context, search, judgment, or latent structure.
7. **Independent verification** — outputs can be checked without reusing the generator's own heuristic as the sole metric.
8. **Distribution realism** — the synthetic failure resembles failures found in practice.
9. **Practical value** — solving the inverse task changes a real workflow or outcome.
10. **Compact representation** — early experiments are technically manageable.
11. **Falsifiability** — the candidate has a predeclared test and kill criterion.

The ideal shape is:

> degradation is cheap, repair is hard, and verification is independent and affordable.

## 7. Training targets

The target need not be a full reconstructed artifact. Depending on the domain, the model may predict:

- one reference artifact;
- a ranked set of edits;
- an edit script;
- a quality axis and severity;
- a pairwise preference;
- a local region that should be changed;
- constraints for another optimizer;
- a critique plus proposed corrections;
- `no edit`;
- abstention with uncertainty.

Edit-based or constraint-based targets are often preferable when many valid improved outputs exist.

## 8. Data-generation design

A robust generator should vary more than one superficial parameter.

For each source artifact:

1. select one or more validated quality axes;
2. sample degradation strength;
3. choose among multiple operator implementations where possible;
4. apply the operator while checking invariants;
5. remove or randomize fingerprints unrelated to the quality problem;
6. record source, degraded artifact, operator, strength, context, and constraints;
7. create held-out source distributions, parameters, implementations, and operator families;
8. maintain a separate set of naturally occurring failures.

A degradation curriculum may include:

```text
original → mild degradation → moderate degradation → severe degradation
```

This supports ranking, severity prediction, and partial repair rather than only binary reconstruction.

## 9. Evaluation principles

A convincing result should separate:

- reversal of known operator signatures;
- generalization to unseen parameters;
- generalization to unseen implementations of the same operator;
- generalization to unseen operator families;
- transfer to naturally occurring low-quality artifacts;
- preservation of invariants;
- improvement under independent human or domain evaluation;
- unnecessary or harmful edits;
- performance against deterministic rules and exact algorithms.

The strongest evidence is improvement on real failures that were not produced by the training generator.

## 10. Main failure modes

### Invalid direction assumption

The transformation encodes taste or a local convention but is treated as universally worse.

### Operator fingerprinting

The model detects synthetic artifacts and applies a memorized reversal rule without learning the intended quality concept.

### Unrealistic degradation

Generated examples do not resemble real mistakes, weak designs, or noisy observations.

### Invalid source assumption

The original artifact is treated as optimal even when it is merely one acceptable solution.

### Invariant violation

The degradation or repair changes meaning, function, legal effect, biological behavior, or factual content.

### Evaluation circularity

The same heuristic is used to generate, filter, train, select, and evaluate the data.

### Single-answer bias

The model is punished for producing a valid alternative that differs from the source artifact.

### Unnecessary machine learning

A deterministic inverse, formal algorithm, or conventional optimizer solves the problem more reliably and cheaply.

### Hidden harm

In medicine, law, biology, policy, or safety engineering, a formally improved artifact may still cause real-world harm.

## 11. Relation to adjacent methods

The pattern overlaps with:

- denoising and corruption-based pretraining;
- inverse problems;
- synthetic bug injection;
- back-translation;
- data augmentation;
- preference and ranking learning;
- mutation testing;
- self-supervision;
- simulation-based inference;
- constrained optimization;
- refactoring and simplification.

This repository does not claim that the general family is wholly new. Its organizing proposal is to examine **validated, meaning- or function-preserving directional degradation as a source of supervision for hard-to-score quality axes**.

## 12. Research claim to test

The broad claim is not that every degradation pair creates a useful model. The testable claim is narrower:

> For some quality axes, validated controlled degradation can produce cheaper and more scalable supervision than direct scalar scoring or manual collection of bad-to-good pairs, while retaining enough realism to improve naturally occurring artifacts under independent evaluation.

A candidate should be downgraded or rejected when:

- its operator cannot be validated as directionally worse;
- a simple inverse or exact algorithm performs equally well;
- it fails on held-out operators or natural failures;
- invariant violations are unacceptable;
- proxy gains do not correspond to human or domain outcomes.

Every candidate in the catalog should ultimately be judged against these conditions.