# Quality Without Scores

> Learn improvement without first reducing quality to a single numeric score.

Many valuable qualities are difficult to measure directly: visual hierarchy, clarity, modularity, explanatory flow, maintainability, elegance, or biological design quality. Yet it may be much easier to define a transformation that reliably makes a good example worse along one specific axis while preserving its underlying meaning, function, or content.

This repository is a public-domain catalog of tasks built around that asymmetry.

## Core idea

Given a relatively good artifact `y`:

1. Apply a controlled, directional degradation `D` to produce `x = D(y)`.
2. Preserve the properties that should not change: meaning, function, factual content, physical constraints, or task intent.
3. Train a model to recover an improved artifact from the degraded one: `G(x) ≈ y`.

The degradation operator supplies supervision when an absolute quality score would be arbitrary, expensive, or impossible to define.

```text
good example
    ↓ controlled degradation
worse example with preserved intent
    ↓ inverse learning
improved example
```

## Flagship example: visual attention in posters

A well-designed poster may guide attention through a deliberate sequence:

```text
title → main image → key message → call to action
```

Without changing the text, images, or communicative goal, a generator could degrade that flow by flattening typographic hierarchy, creating competing focal points, separating related elements, weakening contrast, or moving the call to action into a low-attention region.

The resulting pairs could train a model to restore the intended attention flow. The point is not merely to score a poster as “good” or “bad,” but to learn a concrete improvement direction from controlled degradations.

## What this repository contains

- A precise description of the method and its boundaries
- A cross-disciplinary catalog of candidate applications
- A scorecard for comparing ideas
- Failure modes and evaluation guidance
- A contribution format for adding new candidates

No implementation is required. The goal is to make useful research and product directions explicit enough that others can test, build, publish, or commercialize them.

## Selection rule

A strong candidate usually has the following structure:

- Good examples are available.
- A specific quality axis can be degraded automatically.
- Important invariants can be preserved.
- Reversing the degradation requires context or judgment.
- Outputs can be checked at least partially.
- The synthetic degradation resembles a real failure mode.
- Solving the inverse task would be useful.

The ideal case is:

> **degradation is cheap, repair is hard, and verification is cheap.**

## Important limitation

This is not a claim that every form of quality has one correct answer, or that synthetic degradation automatically produces useful models. A model may learn fingerprints of the degradation operator rather than the intended quality concept. Multiple outputs may be valid. The original artifact may not be genuinely high quality. Real-world evaluation remains necessary.

This repository also does not claim that the broad pattern is entirely new. It overlaps with denoising, inverse problems, synthetic corruption, back-translation, preference learning, and mutation-based training. The focus here is narrower:

> **using directional, often meaning-preserving degradation operators as an operational definition of hard-to-score quality.**

## Repository map

- [`METHOD.md`](METHOD.md) — formal framing and boundaries
- [`CATALOG.md`](CATALOG.md) — cross-disciplinary application ideas
- [`EVALUATION.md`](EVALUATION.md) — scorecard and failure modes
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — how to add an idea

## Public-domain dedication

The contents of this repository are dedicated to the public domain under [CC0 1.0 Universal](LICENSE). You may use, copy, modify, publish, implement, or commercialize the ideas and text here without permission or attribution.

This dedication does not waive third-party rights, patents, trademarks, privacy rights, or rights in external datasets and artifacts.