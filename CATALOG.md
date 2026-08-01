# Candidate Catalog

This catalog lists possible applications of directional degradation learning. It is deliberately cross-disciplinary. Every estimate is provisional; none is an empirical result or a novelty claim.

## How to read the catalog

The catalog avoids unexplained numeric precision.

- **Generation** — ease of generating controlled pairs at scale
- **Verification** — strength and cost of independent improvement and invariant checks
- **Impact** — plausible practical or scientific value
- **Confidence** — confidence in the estimates, not confidence that the method will work
- **Review status** — whether the entry has only been literature-scoped or reviewed by a domain specialist

Values are `High`, `Medium`, `Low`, or `Unknown`. Confidence is `Low`, `Medium`, or `High`.

All entries currently remain hypotheses. `domain-review-needed` is especially important in medicine, law, biology, and safety-relevant engineering.

## Task definitions

| # | Candidate | Domain | Core invariant | Directional degradation | Preferred model output |
|---:|---|---|---|---|---|
| 1 | Poster attention-flow restoration | Visual communication | Text, images, message, brand constraints | Flatten hierarchy, create competing focal points, weaken CTA, separate related elements | Ranked layout edits or a constraint-preserving revised layout |
| 2 | Single-slide information hierarchy | Presentations | Claims, figures, factual content | Equalize emphasis, misplace conclusion, detach labels, overload secondary details | Ranked edits restoring intended reading order and emphasis |
| 3 | Scientific-figure clarity repair | Science communication | Data values and scientific meaning | Obscure legends, weaken grouping, reorder panels, reduce label clarity | Edit plan improving interpretation without changing the science |
| 4 | Data-visualization narrative alignment | Data analysis | Dataset and encoded values | Emphasize irrelevant series, weaken key comparison, disturb annotation order | Edits aligned to a declared analytical question |
| 5 | Personalized photo-editing recovery | Photography | Scene content and user intent | Perturb crop, tone, contrast, local emphasis, and color relationships | User-conditioned edit proposals, not one universal reconstruction |
| 6 | Musical foreground/background balance | Music | Notes, lyrics, harmonic identity, arrangement intent | Mask the lead, flatten dynamics, disturb entrances, overemphasize accompaniment | Mix or arrangement edits conditioned on genre and intent |
| 7 | Host-conditioned codon optimization | Synthetic biology | Amino-acid sequence | Replace preferred synonymous codons, disturb GC balance, introduce undesirable motifs | Improved synonymous sequence under explicit host constraints |
| 8 | Gene-annotation structure repair | Genomics | Genomic sequence and independent evidence | Shift exon boundaries, omit isoforms, merge genes, remove evidence links | Ranked annotation corrections with evidence confidence |
| 9 | PCR-primer design repair | Molecular biology | Target locus and assay goal | Introduce suboptimal length, GC balance, dimer risk, or target placement | Constrained primer alternatives or ranked repairs |
| 10 | Clinical-note structure repair | Medicine | Clinical facts, attribution, uncertainty, and chronology | Remove structure, scatter related facts, obscure assessment-plan links | Advisory reorganization with traceable fact preservation |
| 11 | Patient-instruction clarity repair | Health communication | Medical facts, warnings, and prescribed actions | Increase jargon, disturb step order, weaken warnings | Clearer instructions with clinical fidelity checks |
| 12 | Educational explanation sequencing | Education | Concepts, facts, and learning objective | Present prerequisites late, detach examples, remove signposting | Learner-conditioned reordering or edit plan |
| 13 | Mathematical-proof exposition repair | Mathematics | Logical validity and conclusion | Inline lemmas, remove motivation, hide dependencies | Clearer exposition or modularization while retaining formal validity |
| 14 | Philosophical-argument structure repair | Philosophy | Claims, premises, objections, scope, and commitments | Flatten premise hierarchy, detach objections, hide dependencies | Argument-map and exposition edits preserving argumentative force |
| 15 | Legal-contract readability repair | Law | Legal effect, parties, obligations, definitions, exceptions | Increase cross-reference distance, bury exceptions, weaken grouping | Advisory readability edits with lawyer review |
| 16 | Function-boundary recovery | Software engineering | Program behavior and tests | Inline helpers, merge responsibilities, duplicate local logic | Extract-method boundaries, names, parameters, and returns |
| 17 | Spreadsheet-model structure repair | End-user programming | Calculated results and business assumptions | Duplicate formulas, scatter assumptions, mix inputs and outputs | Ranked structural refactorings with recalculation checks |
| 18 | Database-schema modularity repair | Data engineering | Entities, constraints, dependencies, and workload requirements | Merge tables, duplicate attributes, obscure ownership | Schema alternatives with dependency and workload tradeoffs |
| 19 | CAD-assembly modularity repair | Mechanical engineering | Geometry, fit, kinematics, and required function | Merge parts, flatten assemblies, hide interfaces | Part and subassembly proposals conditioned on manufacturing intent |
| 20 | Business-process simplification | Operations and management | Required outcomes, controls, and legal constraints | Add redundant approvals, reorder handoffs, split ownership | Ranked process edits preserving controls and outcomes |

## Provisional triage

| # | Candidate | Generation | Verification | Impact | Confidence | Review status |
|---:|---|---|---|---|---|---|
| 1 | Poster attention-flow restoration | High | Medium | High | Medium | literature-scoped |
| 2 | Single-slide information hierarchy | High | Medium | High | Medium | literature-scoped |
| 3 | Scientific-figure clarity repair | Medium | Medium | High | Low | domain-review-needed |
| 4 | Data-visualization narrative alignment | Medium | Medium | High | Low | domain-review-needed |
| 5 | Personalized photo-editing recovery | High | Medium | Medium | Medium | literature-scoped |
| 6 | Musical foreground/background balance | Medium | Low | Medium | Low | domain-review-needed |
| 7 | Host-conditioned codon optimization | High | Medium | High | Low | domain-review-needed |
| 8 | Gene-annotation structure repair | Medium | Medium | High | Low | domain-review-needed |
| 9 | PCR-primer design repair | High | High | Medium | Medium | domain-review-needed |
| 10 | Clinical-note structure repair | Medium | Low | High | Low | domain-review-needed |
| 11 | Patient-instruction clarity repair | Medium | Low | High | Low | domain-review-needed |
| 12 | Educational explanation sequencing | High | Medium | High | Low | domain-review-needed |
| 13 | Mathematical-proof exposition repair | Medium | High | Medium | Medium | domain-review-needed |
| 14 | Philosophical-argument structure repair | Medium | Low | Medium | Low | domain-review-needed |
| 15 | Legal-contract readability repair | Low | Low | High | Low | domain-review-needed |
| 16 | Function-boundary recovery | High | High | High | Medium | literature-scoped |
| 17 | Spreadsheet-model structure repair | High | High | High | Medium | literature-scoped |
| 18 | Database-schema modularity repair | Medium | High | High | Medium | domain-review-needed |
| 19 | CAD-assembly modularity repair | Low | Medium | High | Low | domain-review-needed |
| 20 | Business-process simplification | Medium | Medium | High | Low | domain-review-needed |

These labels summarize current judgment only. Every row should be revised when domain experts, datasets, or experiments provide better evidence.

## Falsification and kill criteria

A candidate should not remain in the “promising” category merely because a demonstration looks attractive.

| # | Candidate | Minimum falsifiable test | Kill criterion or major downgrade condition |
|---:|---|---|---|
| 1 | Train on several hierarchy degradations; test on held-out operators and naturally weak posters with human scan paths | No improvement over deterministic typography rules, or saliency gains fail to improve human attention/task results |
| 2 | Preserve all slide content and compare ranked edits against generation-first and rule baselines | Improvements disappear when exact source reconstruction is not rewarded, or natural slides do not benefit |
| 3 | Blind experts compare repaired figures while checking every data value and claim | Clarity rises only by changing scientific emphasis, meaning, or uncertainty |
| 4 | Condition on a declared analytical question and audit for misleading encodings | The system improves persuasive impact but not truthful interpretation, or routinely hides uncertainty |
| 5 | Test on new photos with blinded choices from the same user | Performance collapses outside known perturbations or merely reproduces fixed presets |
| 6 | Conduct genre-conditioned listening tests on unseen mixes | No consistent preference over standard mix-assistant baselines, or edits erase artistic intent |
| 7 | Evaluate on held-out proteins and hosts with wet-lab expression | Gains exist only on proxy metrics and do not improve expression or robustness |
| 8 | Test on difficult genomes using independent long-read, protein, and curation evidence | The model mainly reconstructs source annotations, including their errors, and fails on evidence-poor genomes |
| 9 | Compare against Primer3 and exact constrained search on empirical assay outcomes | Learned repair does not beat exact optimization or adds no value on laboratory-specific failures |
| 10 | Clinicians audit fact, chronology, negation, attribution, and downstream task utility | Any clinically material fact changes, or structure gains do not improve clinical use |
| 11 | Lay users answer comprehension and action questions after reading outputs | Grade-level scores improve but comprehension, action accuracy, or factual fidelity do not |
| 12 | Learner-conditioned trial measures comprehension, retention, and transfer | The model only reverses artificial orderings and does not help real learner misconceptions |
| 13 | Preserve formal validity and compare with alternative expert expositions | Exact-source similarity drives the score, or formal correctness/reuse is harmed |
| 14 | Philosophers judge clarity and identity of commitments under blinded comparison | Revisions alter scope, modal force, objections, or dialectical position |
| 15 | Lawyers compare legal effect using adversarial clauses and executable checks where possible | Legal-effect invariance cannot be demonstrated or readability gains introduce ambiguity |
| 16 | Test on natural long methods from held-out projects with developer acceptance | Gains vanish outside inverse-inline examples or rule-based extract-method tools perform equally well |
| 17 | Test real workbooks on recalculation, scenario tasks, and maintenance time | Only local formula smells improve while whole-model maintainability and outputs do not |
| 18 | Compare with formal normalization and workload-aware optimization | Learning adds no value once dependencies and workloads are supplied, or invents invalid constraints |
| 19 | Engineers perform manufacturing, maintenance, and assembly tasks with proposed decompositions | Boundaries reflect geometry only and reduce manufacturability, serviceability, or kinematic validity |
| 20 | Use event logs, simulation, control coverage, and process-owner review | Synthetic friction does not resemble real constraints, or simplification removes required controls |

## Flagship candidates

### 1. Poster attention-flow restoration

**Why it advertises the method well:** degradation and intended repair can be understood visually in seconds.

- **Good source:** professionally designed posters or structured templates with editable elements.
- **Operator validation:** show original and degraded versions under a declared attention goal; retain only operators for which blinded raters consistently prefer the original.
- **Preserved invariants:** words, images, communicative objective, required branding, and canvas size.
- **Target:** ranked edit operations or a revised layout, with a no-edit option.
- **Independent evaluation:** eye tracking, task completion, pairwise human judgment, legibility, and overlap checks.
- **Falsifiable test:** held-out operator families plus naturally weak posters.
- **Kill criterion:** deterministic rules match the model, or predicted saliency improves without human scan-path or task improvement.

### 2. Host-conditioned codon optimization

**Why it matters:** it demonstrates that the pattern is not limited to software or visual design.

- **Good source:** experimentally successful coding sequences conditioned on organism and context.
- **Operator validation:** use named synonymous changes with evidence that they tend to reduce the target property in the stated host; do not assume every natural sequence is optimal.
- **Preserved invariant:** encoded amino-acid sequence; other biological properties are not automatically invariant.
- **Target:** improved synonymous sequence under explicit constraints.
- **Independent evaluation:** sequence checks, expression proxies, and ultimately laboratory measurements.
- **Falsifiable test:** held-out proteins and hosts with wet-lab expression.
- **Kill criterion:** no gain beyond established optimizers, or gains exist only on the same proxies used to generate degradation.

### 3. Educational explanation sequencing

**Why it fits the thesis:** teaching quality is hard to score globally, but specific sequencing mistakes can be operationalized.

- **Good source:** expert-reviewed lessons and worked examples.
- **Operator validation:** teachers or learners confirm that a reordering is worse for a specified learner state and objective.
- **Preserved invariants:** facts, examples, target concept, and learning objective.
- **Target:** reordered explanation or ranked edit plan, conditioned on learner profile.
- **Independent evaluation:** comprehension, retention, error diagnosis, and transfer.
- **Falsifiable test:** real misconceptions and learner states not produced by the generator.
- **Kill criterion:** the model reverses synthetic permutations but does not improve learning outcomes.

### 4. Mathematical-proof exposition repair

**Why it is useful:** formal correctness can often be checked separately from explanatory quality.

- **Good source:** formally valid proofs with human-readable exposition.
- **Operator validation:** mathematicians or students confirm that the degradation harms clarity while validity remains intact.
- **Preserved invariant:** theorem, assumptions, and logical validity.
- **Target:** clearer proof presentation, modularization, or edit script—not exact reconstruction.
- **Independent evaluation:** proof checking, reuse, dependency recovery, and blinded human review.
- **Falsifiable test:** alternative valid proofs and held-out degradation families.
- **Kill criterion:** scores reward only source-style imitation or refactoring reduces correctness and reuse.

### 5. Function-boundary recovery

**Why it is a strong low-risk candidate:** behavior can be checked automatically, and the forward operation is direct.

- **Good source:** accepted functions from tested projects.
- **Operator validation:** confirm that the inlined result remains behaviorally equivalent and that developers view the source boundary as useful.
- **Preserved invariants:** program behavior, tests, and externally visible interfaces.
- **Target:** extraction boundary, name, parameters, return values, and ranked confidence.
- **Independent evaluation:** held-out repositories, natural long methods, tests, static analysis, and developer acceptance.
- **Falsifiable test:** hold out entire projects and degradation implementations.
- **Kill criterion:** the model recognizes inline fingerprints but does not find natural refactoring opportunities.

## High-stakes candidates

The following should be treated as research hypotheses requiring specialist governance, not autonomous deployment suggestions:

- gene-annotation structure repair;
- clinical-note structure repair;
- patient-instruction clarity repair;
- legal-contract readability repair;
- host-conditioned codon optimization when outputs proceed to synthesis;
- CAD and business-process changes where safety or regulatory controls are involved.

## Suggested views

### Best demonstrations of the general method

1. Poster attention-flow restoration
2. Function-boundary recovery
3. Host-conditioned codon optimization
4. Educational explanation sequencing
5. Mathematical-proof exposition repair

### Lower-risk starting points

1. Function-boundary recovery
2. Spreadsheet-model structure repair
3. Poster attention-flow restoration with non-deceptive content
4. Single-slide information hierarchy
5. Mathematical-proof exposition repair with formal checking

### Highest potential impact with substantial domain risk

1. Clinical-note structure repair
2. Patient-instruction clarity repair
3. Host-conditioned codon optimization
4. Gene-annotation structure repair
5. Legal-contract readability repair

## How to extend the catalog

New candidates should state:

1. the difficult-to-score quality;
2. the source of relatively good examples;
3. the exact degradation operator;
4. evidence that the operator is directionally valid;
5. the invariant that must be preserved;
6. the preferred output type, including no-edit or abstention;
7. an independent evaluation method;
8. a natural failure mode;
9. the main shortcut risk;
10. a falsifiable test and kill criterion;
11. relevant prior work with evidence-type labels;
12. domain-review status and safety constraints.

See [`CONTRIBUTING.md`](CONTRIBUTING.md) for the submission template.