# Candidate Catalog

This catalog lists possible applications of directional degradation learning. It is deliberately cross-disciplinary. The ratings are provisional estimates intended to help people choose research or product directions; they are not empirical results.

## Rating scale

Each candidate is scored from 1 to 5.

- **Generation** — how easily paired data could be generated automatically
- **Verification** — how cheaply improvement and invariant preservation could be checked
- **Impact** — plausible practical or scientific value
- **Feasibility** — suitability for an initial research project or prototype

A high total is not proof that the idea is novel or useful. Prior-art review and domain validation are still required.

## Summary table

| # | Candidate | Domain | Core invariant | Directional degradation | Learned inverse | Gen. | Verif. | Impact | Feas. |
|---:|---|---|---|---|---|---:|---:|---:|---:|
| 1 | Poster attention-flow restoration | Visual communication | Text, images, message, brand constraints | Flatten hierarchy, create competing focal points, weaken CTA, separate related elements | Restore intended scan path and emphasis | 5 | 3 | 5 | 5 |
| 2 | Single-slide information hierarchy | Presentations | Slide claims, figures, factual content | Equalize emphasis, misplace conclusion, detach labels, overload secondary details | Restore conclusion-first hierarchy and reading order | 5 | 3 | 5 | 5 |
| 3 | Scientific-figure clarity repair | Science communication | Data values and scientific meaning | Obscure legends, weaken grouping, reorder panels, reduce label clarity | Improve interpretability without changing data | 4 | 4 | 5 | 4 |
| 4 | Data-visualization narrative alignment | Data analysis | Dataset and encoded values | Emphasize irrelevant series, weaken key comparison, disturb annotation order | Align visual emphasis with an analytical question | 4 | 4 | 5 | 4 |
| 5 | Personalized photo-editing recovery | Photography | Scene content and user intent | Perturb crop, tone, contrast, local emphasis, and color relationships | Recover a user- or style-conditioned edit | 5 | 3 | 4 | 4 |
| 6 | Musical foreground/background balance | Music | Notes, lyrics, harmonic identity, arrangement intent | Overemphasize accompaniment, mask melody, flatten dynamics, disturb entrances | Restore perceptual hierarchy in an arrangement or mix | 3 | 2 | 4 | 2 |
| 7 | Host-conditioned codon optimization | Synthetic biology | Amino-acid sequence | Replace preferred synonymous codons, disturb GC balance, introduce undesirable local motifs | Improve a DNA design for a specified host | 5 | 3 | 5 | 3 |
| 8 | Gene-annotation structure repair | Genomics | Underlying genomic sequence and evidence | Shift exon boundaries, omit isoforms, flatten transcript structure | Recover plausible gene and transcript annotations | 4 | 4 | 5 | 2 |
| 9 | PCR-primer design repair | Molecular biology | Target locus and assay goal | Introduce suboptimal length, GC balance, dimer risk, or target placement | Restore robust primer pairs under constraints | 5 | 5 | 4 | 4 |
| 10 | Clinical-note structure repair | Medicine | Clinical facts and chronology | Remove section structure, scatter related facts, obscure assessment-plan links | Restore clinically useful organization | 4 | 3 | 5 | 2 |
| 11 | Patient-instruction clarity repair | Health communication | Medical facts, warnings, prescribed actions | Increase jargon, disturb step order, weaken warnings, separate conditions from actions | Produce clearer instructions without altering meaning | 4 | 3 | 5 | 3 |
| 12 | Educational explanation sequencing | Education | Concepts, facts, intended learning objective | Present prerequisites late, separate examples from rules, remove signposting | Restore a teachable sequence for a learner profile | 5 | 3 | 5 | 4 |
| 13 | Mathematical-proof exposition repair | Mathematics | Logical validity and conclusion | Inline lemmas, remove motivation, reorder explanatory steps, hide dependencies | Improve exposition while preserving proof correctness | 4 | 4 | 4 | 4 |
| 14 | Philosophical-argument structure repair | Philosophy | Claims, premises, objections, commitments | Flatten premise hierarchy, detach objections, hide inferential dependencies | Recover a clearer argument map and exposition | 4 | 2 | 4 | 3 |
| 15 | Legal-contract readability repair | Law | Legal effect, parties, obligations, defined terms | Increase cross-reference distance, bury exceptions, weaken clause grouping | Improve navigability and clarity without changing obligations | 3 | 2 | 5 | 1 |
| 16 | Function-boundary recovery | Software engineering | Program behavior and tests | Inline helper functions, merge responsibilities, duplicate local logic | Propose extract-function boundaries, names, parameters, and returns | 5 | 5 | 5 | 5 |
| 17 | Spreadsheet-model structure repair | End-user programming | Calculated results and business assumptions | Duplicate formulas, scatter assumptions, mix input and output regions, perturb references | Restore maintainable model structure | 5 | 5 | 5 | 4 |
| 18 | Database-schema modularity repair | Data engineering | Represented entities, constraints, and query requirements | Merge tables, duplicate attributes, obscure ownership, weaken naming | Recover clearer schema boundaries and relationships | 4 | 5 | 5 | 3 |
| 19 | CAD-assembly modularity repair | Mechanical engineering | Geometry, fit, and required function | Merge parts, hide interfaces, disturb naming and assembly hierarchy | Recover useful part and subassembly boundaries | 3 | 5 | 5 | 2 |
| 20 | Business-process simplification | Operations and management | Required outcomes, controls, legal constraints | Add redundant approvals, reorder handoffs, split coherent tasks, obscure ownership | Remove friction while preserving controls and outcomes | 4 | 3 | 5 | 3 |

## Flagship candidates

### 1. Poster attention-flow restoration

**Why it advertises the method well:** the degradation and repair can be understood visually in seconds.

- **Good source:** professionally designed posters or structured templates with editable elements.
- **Degradation operators:** flatten size hierarchy, create competing contrast, move the CTA, break proximity groups, place text over salient background regions.
- **Preserved invariants:** words, images, communicative objective, required branding, canvas size.
- **Target:** edit operations or a revised layout that restores a specified attention order.
- **Independent evaluation:** eye-tracking, scan-path prediction, task completion, pairwise human judgment, legibility and overlap checks.
- **Primary risk:** the model learns simple typography rules or synthetic operator signatures instead of visual communication.

### 2. Host-conditioned codon optimization

**Why it matters:** it demonstrates that the method is not limited to software or visual design.

- **Good source:** experimentally successful or naturally expressed coding sequences, conditioned on organism and context.
- **Degradation operators:** synonymous substitutions that worsen host preference, local GC balance, RNA structure, repeat structure, or motif constraints.
- **Preserved invariant:** encoded amino-acid sequence.
- **Target:** improved synonymous DNA sequence under host-specific constraints.
- **Independent evaluation:** sequence constraints, expression proxies, and ultimately laboratory measurements.
- **Primary risk:** the source sequence may not be optimal, and sequence-level proxies may not predict biological performance.

### 3. Educational explanation sequencing

**Why it fits the thesis:** teaching quality is difficult to score globally, but many directional mistakes can be generated explicitly.

- **Good source:** expert-reviewed lessons, worked examples, and instructional explanations.
- **Degradation operators:** delay prerequisites, remove signposting, separate a rule from its example, add irrelevant detail before the core concept, disturb progressive difficulty.
- **Preserved invariants:** facts, examples, target concept, and intended learning outcome.
- **Target:** reordered explanation, edit plan, or learner-conditioned revision.
- **Independent evaluation:** comprehension questions, retention, error diagnosis, and pairwise teacher review.
- **Primary risk:** the original ordering may suit one learner but not another; conditioning on learner state is essential.

### 4. Mathematical-proof exposition repair

**Why it is useful:** correctness can often be checked separately from explanatory quality.

- **Good source:** formally valid proofs with human-readable exposition.
- **Degradation operators:** inline lemmas, remove motivation, reorder non-dependent explanatory blocks, replace meaningful names, hide dependency structure.
- **Preserved invariant:** logical validity and theorem proved.
- **Target:** a clearer proof presentation or a structured edit script.
- **Independent evaluation:** proof checking plus human evaluation of clarity and dependency recovery.
- **Primary risk:** exact reconstruction rewards the source style rather than genuine clarity; multiple valid expositions must be allowed.

### 5. Business-process simplification

**Why it could become a product:** organizations routinely pay to identify unnecessary handoffs and approvals.

- **Good source:** validated, efficient workflows with explicit controls and outcomes.
- **Degradation operators:** insert redundant approval loops, split ownership, move information collection late, create avoidable handoffs, duplicate checks.
- **Preserved invariants:** required outcome, legal controls, segregation of duties, and safety constraints.
- **Target:** a simplified process graph or ranked edit proposal.
- **Independent evaluation:** simulation, cycle time, handoff count, control coverage, and domain review.
- **Primary risk:** synthetic inefficiency may be easier to remove than real organizational constraints.

## Suggested views of the catalog

### Best demonstrations of the general method

1. Poster attention-flow restoration
2. Host-conditioned codon optimization
3. Educational explanation sequencing
4. Mathematical-proof exposition repair
5. Function-boundary recovery

These span visual design, biology, education, mathematics, and software.

### Easiest candidates for an initial experiment

1. Poster attention-flow restoration
2. Single-slide information hierarchy
3. Function-boundary recovery
4. PCR-primer design repair
5. Spreadsheet-model structure repair

### Highest potential impact, with higher domain risk

1. Clinical-note structure repair
2. Patient-instruction clarity repair
3. Host-conditioned codon optimization
4. Gene-annotation structure repair
5. Legal-contract readability repair

### Most important candidates for independent human evaluation

1. Musical foreground/background balance
2. Philosophical-argument structure repair
3. Legal-contract readability repair
4. Personalized photo-editing recovery
5. Educational explanation sequencing

## How to extend the catalog

New candidates should state:

1. the difficult-to-score quality;
2. the source of relatively good examples;
3. the exact degradation operator;
4. the invariant that must be preserved;
5. the inverse task;
6. an independent evaluation method;
7. a realistic failure mode represented by the degradation;
8. the main reason the model might learn the wrong thing;
9. relevant prior work;
10. expected practical or scientific value.

See [`CONTRIBUTING.md`](CONTRIBUTING.md) for the submission template.