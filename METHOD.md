# Method

## 1. Problem statement

Many domains contain qualities that experts can recognize but cannot reduce cleanly to a scalar score. Examples include visual hierarchy, explanatory flow, modularity, maintainability, argument structure, and biological design quality.

A direct reward function may be incomplete or misleading. Human labeling may be expensive. However, it may still be possible to write an operator that moves a relatively good artifact in a reliably worse direction along one selected quality axis.

This repository studies that asymmetry.

## 2. Basic formulation

Let:

- `y` be a relatively good artifact.
- `D_k` be a controlled degradation operator for quality axis `k`.
- `x = D_k(y)` be the degraded artifact.
- `I` be the set of invariants that should remain unchanged.
- `G` be a learned inverse or improvement model.

A valid degradation should satisfy, as far as the domain allows:

```text
I(x) = I(y)
```

while reducing quality along the selected axis:

```text
q_k(x) < q_k(y)
```

The model is trained on pairs `(x, y)` or on edit instructions that map `x` toward `y`:

```text
G(x, k, context) ≈ y
```

The quality function `q_k` does not need to be fully measurable. The operator `D_k` acts as an operational statement that the transformation moves in the wrong direction.

## 3. What makes this different from generic corruption

The central object is not arbitrary noise. It is a **directional degradation operator** with an interpretable relationship to a quality concept.

Examples:

- Flatten typographic hierarchy while preserving poster content.
- Inline a well-chosen helper function while preserving program behavior.
- Replace host-preferred synonymous codons while preserving the amino-acid sequence.
- Remove headings and discourse markers while preserving document propositions.
- Separate related diagram elements while preserving the underlying data.

A useful operator should expose a quality axis, not merely make the input harder to read.

## 4. Three task families

### 4.1 Restoration

The degradation removes or obscures information that can be reconstructed from context.

```text
clean observation → degraded observation → restoration
```

Examples include measurement noise, missing labels, or reduced resolution.

### 4.2 Quality-direction repair

The degradation preserves meaning or function but worsens organization, presentation, or design.

```text
well-organized artifact → meaning-preserving degradation → quality repair
```

This is the primary focus of this repository.

### 4.3 Cheap-forward / hard-inverse generation

A latent solution can be sampled cheaply and mapped forward into an observation, while the inverse problem is difficult.

```text
latent solution → cheap forward transform → difficult inverse task
```

Prime factorization is a clean synthetic example, but practical applications require a reason to use a learned model rather than an existing exact algorithm.

## 5. Candidate admission criteria

A candidate is strong when most of the following hold:

1. **Source availability** — relatively good examples can be collected or generated.
2. **Automatic degradation** — the operator can be applied at scale.
3. **Invariant preservation** — meaning, function, factual content, or physical constraints remain stable.
4. **Inverse difficulty** — repair requires context, search, judgment, or latent structure.
5. **Verification** — outputs can be checked automatically or with inexpensive pairwise evaluation.
6. **Distribution realism** — the synthetic failure resembles failures found in practice.
7. **Practical value** — solving the inverse task changes a real workflow or outcome.
8. **Compact representation** — early experiments do not require prohibitively long sequences or huge artifacts.

The ideal shape is:

> degradation is cheap, repair is hard, and verification is cheap.

## 6. Training targets

The target need not be a full reconstructed artifact. Depending on the domain, the model may predict:

- the original artifact;
- a ranked set of edits;
- an edit script;
- a quality axis and severity;
- a preferred pairwise ordering;
- a local region that should be changed;
- constraints for another optimizer;
- a critique plus a proposed correction.

Edit-based targets are often preferable when many valid improved outputs exist.

## 7. Data-generation design

A robust generator should vary more than one superficial parameter.

For each source artifact:

1. Select one or more quality axes.
2. Sample degradation strength.
3. Apply the operator while checking invariants.
4. Remove or randomize operator fingerprints where possible.
5. Record the source, degraded artifact, operator, strength, and preserved constraints.
6. Create held-out operator families, source distributions, and severity levels for evaluation.

A degradation curriculum may include several levels:

```text
original → mild degradation → moderate degradation → severe degradation
```

This supports ranking, severity prediction, and partial repair rather than only binary reconstruction.

## 8. Evaluation principles

A convincing result should separate:

- reversal of known operator signatures;
- generalization to unseen operator parameters;
- generalization to unseen operator families;
- transfer to naturally occurring low-quality artifacts;
- preservation of the intended invariants;
- improvement according to independent human or domain evaluation.

The strongest evidence is improvement on real failures that were not produced by the training generator.

## 9. Main failure modes

### Operator fingerprinting

The model detects synthetic artifacts and applies a memorized reversal rule without learning the intended quality concept.

### Unrealistic degradation

The generated examples do not resemble real mistakes, weak designs, or noisy observations.

### Invalid source assumption

The original artifact is treated as optimal even when it is merely one acceptable solution.

### Invariant violation

The degradation changes meaning, function, legal effect, biological behavior, or factual content.

### Evaluation circularity

The same heuristic is used to generate, train, and evaluate the data, making the result tautological.

### Single-answer bias

The model is punished for producing a valid alternative that differs from the source artifact.

### Hidden harm

In medicine, law, biology, or public policy, a formally improved artifact may still cause real-world harm. Domain review remains necessary.

## 10. Relation to adjacent methods

The pattern overlaps with:

- denoising and corruption-based pretraining;
- inverse problems;
- synthetic bug injection;
- back-translation;
- data augmentation;
- preference and ranking learning;
- mutation testing;
- self-supervision;
- simulation-based inference.

This repository does not claim that the general family is wholly new. Its organizing proposal is to treat a **meaning-preserving, directional degradation operator as an operational definition of hard-to-score quality**, and to catalog domains where that framing may create useful supervision.

## 11. Research claim to test

The broad claim is not that every degradation pair creates a useful model. The testable claim is narrower:

> For some quality axes, controlled degradation can produce cheaper and more scalable supervision than direct scoring or manual collection of bad-to-good pairs, while retaining enough realism to improve naturally occurring artifacts.

Every candidate in the catalog should ultimately be judged against that claim.