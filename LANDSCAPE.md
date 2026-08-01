# Prior-Art and Product Landscape

_Last reviewed: 2026-08-01._

This document grounds the 20 candidates in [`CATALOG.md`](CATALOG.md) in existing research and adjacent tools. It is a scoped landscape review, not a systematic review. Links are included so that researchers can verify novelty before making claims.

The products and tools listed below are **adjacent**, not necessarily direct implementations of directional degradation learning. The open gaps are synthesis by this repository and should be treated as hypotheses to test.

## Summary

| # | Candidate | Established adjacent work? | Direct controlled-degradation precedent? | Main unresolved question |
|---:|---|---|---|---|
| 1 | Poster attention-flow restoration | Strong | Limited | Can synthetic hierarchy damage transfer to naturally weak posters and human scan paths? |
| 2 | Single-slide information hierarchy | Strong | Limited | Can fixed-content hierarchy repair outperform generation-first slide systems? |
| 3 | Scientific-figure clarity repair | Emerging | Limited | Can clarity improve without changing scientific meaning or introducing misleading emphasis? |
| 4 | Data-visualization narrative alignment | Strong | Limited | Can a model align emphasis to an analytical intent without manipulating interpretation? |
| 5 | Personalized photo-editing recovery | Strong | Partial | Can degradations cheaply learn a user preference without collapsing to preset reversal? |
| 6 | Musical foreground/background balance | Moderate | Limited | Can perceptual hierarchy be repaired while preserving artistic intent across genres? |
| 7 | Host-conditioned codon optimization | Strong | Partial | Do controlled degradations improve real expression beyond proxy metrics and natural-sequence training? |
| 8 | Gene-annotation structure repair | Strong | Limited | Can corrupted annotations produce models that improve real, evidence-poor genomes? |
| 9 | PCR-primer design repair | Strong | Partial | Is learned repair useful beyond exact constrained optimization tools? |
| 10 | Clinical-note structure repair | Strong | Limited | Can reorganization preserve every clinically material fact and chronology? |
| 11 | Patient-instruction clarity repair | Strong | Partial | Can simplicity improve without accuracy loss, and does it improve layperson comprehension? |
| 12 | Educational explanation sequencing | Emerging | Limited | Can synthetic sequencing errors transfer to real learner-specific misconceptions? |
| 13 | Mathematical-proof exposition repair | Emerging | Limited | Can readability and modularity improve without rewarding one canonical style? |
| 14 | Philosophical-argument structure repair | Strong adjacent field | Limited | Can argument clarity be improved without changing commitments or argumentative force? |
| 15 | Legal-contract readability repair | Emerging | Limited | Can readability change while legal effect remains invariant? |
| 16 | Function-boundary recovery | Strong | Partial | Can inverse-inline training generalize to real extraction opportunities rather than operator traces? |
| 17 | Spreadsheet-model structure repair | Strong | Partial | Can whole-model maintainability improve beyond local formula smells? |
| 18 | Database-schema modularity repair | Strong algorithms | Limited | Where does learning add value beyond normalization algorithms and known dependencies? |
| 19 | CAD-assembly modularity repair | Emerging | Limited | Can learned boundaries reflect manufacturing and maintenance intent, not only geometry? |
| 20 | Business-process simplification | Strong | Limited | Can synthetic friction model real organizational constraints and preserve controls? |

---

## 1. Poster attention-flow restoration

### Existing research

- [Poster graphic design with your Eyes: An approach to automatic textual layout design based on visual perception](https://www.sciencedirect.com/science/article/pii/S0141938223000914) uses saliency prediction and eye-movement evaluation to guide text placement.
- [Learning priority-aware controllable poster layout generation](https://www.sciencedirect.com/science/article/abs/pii/S0031320326004632) explicitly models element priority and salient regions for poster generation.
- [Reverse-engineering information presentations](https://link.springer.com/article/10.1007/s44267-023-00010-1) recovers hierarchical grouping from posters, slides, and reports.

### Adjacent products or tools

- [Adobe Express Poster Maker](https://www.adobe.com/express/create/poster) provides templates and AI-assisted poster generation.

### Open gap

Existing systems mainly generate layouts or predict saliency. A distinct experiment would hold content and intent fixed, create graded hierarchy and scan-path degradations, and train an edit model to restore a specified attention order. Evaluation should include held-out degradation families, natural weak posters, and human eye tracking—not only the same saliency model used to generate data.

## 2. Single-slide information hierarchy

### Existing research

- [SlideCoder](https://aclanthology.org/2025.emnlp-main.458/) reconstructs editable slides from reference designs and reports strong gains in layout fidelity and execution accuracy.
- [Design First, Code Later](https://aclanthology.org/2026.findings-acl.1524/) separates slide design from implementation and introduces a slide-design dataset and trained models.
- [Reverse-engineering information presentations](https://link.springer.com/article/10.1007/s44267-023-00010-1) provides evidence that implicit hierarchical grouping can be recovered from page layouts.

### Adjacent products or tools

- [Copilot in PowerPoint](https://support.microsoft.com/en-us/powerpoint/copilot/keep-your-presentation-on-brand-with-copilot) uses templates, layouts, objects, and brand kits to generate and edit slides.

### Open gap

Generation and reconstruction are well studied, but fixed-content **hierarchy repair** is less explicit. A useful benchmark would preserve claims, figures, and wording while degrading emphasis, grouping, conclusion placement, and reading order. The target should be an edit script or ranked edits rather than exact pixel reconstruction.

## 3. Scientific-figure clarity repair

### Existing research

- [SciFig: Towards Automating Scientific Figure Generation](https://arxiv.org/abs/2601.04390) generates scientific figures with hierarchical layout planning and rubric-based iterative feedback.
- [SciFigQual-Bench](https://arxiv.org/abs/2607.27084) evaluates figures with manuscript context across clarity, layout, caption fit, contextual relevance, and misleading risk.
- [GPT-4 as an Effective Zero-Shot Evaluator for Scientific Figure Captions](https://aclanthology.org/2023.findings-emnlp.363/) shows the cost and difficulty of expert-grounded figure-caption evaluation.

### Adjacent products or tools

- [BioRender](https://www.biorender.com/) provides structured templates, scientific assets, and editable figure creation.

### Open gap

A repair model must preserve data values, causal direction, labels, and scientific claims. Controlled degradations could target grouping, legend distance, panel order, annotation clutter, or caption linkage. The hardest requirement is an independent misleadingness check: a visually clearer figure can still become scientifically wrong or rhetorically biased.

## 4. Data-visualization narrative alignment

### Existing research

- [Attention-Aware Visualization](https://content-staging.ieeevis.org/year/2024/paper_v-full-1480.html) studies visualizations that track and respond to user attention.
- [Narrative Player](https://mp1.ieeevis.org/year/2025/program/paper_a8c54e73-a078-47b8-94b9-8b8dfda73721.html) addresses the relationship between data-rich documents and visual narratives.
- [The Impact of Elicitation and Contrasting Narratives](https://ieeevis.org/year/2024/program/paper_v-tvcg-20243355884.html) demonstrates that narrative choices around visualization affect engagement, recall, and attitudes.

### Adjacent products or tools

- [Tableau](https://www.tableau.com/) provides AI-assisted visual analytics and automated insight workflows.

### Open gap

The task is not generic chart beautification. The model would receive an analytical question or intended comparison, then repair emphasis while preserving the data encoding. Evaluation must detect misleading scale, selective annotation, hidden uncertainty, and narrative manipulation. A central research question is whether an intended narrative can be separated from an unjustified persuasive nudge.

## 5. Personalized photo-editing recovery

### Existing research

- [Learning Personalized Photographic Style from Pairwise User Preferences](https://openaccess.thecvf.com/content/CVPR2026/html/Kim_Learning_Personalized_Photographic_Style_from_Pairwise_User_Preferences_CVPR_2026_paper.html) introduces a large pairwise-preference dataset and personalized style baselines.
- [PieNet: Personalized Image Enhancement Network](https://www.ecva.net/papers/eccv_2020/papers_ECCV/html/7579_ECCV_2020_paper.php) learns a user preference vector from a small set of preferred images.
- [Multimodal Prediction and Personalization of Photo Edits](https://proceedings.mlr.press/v84/saeedi18a.html) models multiple valid edits and adaptation to user preferences.

### Adjacent products or tools

- Commercial photo editors already provide presets and automatic enhancement, but the cited research emphasizes that users have materially different preferences and that one universal target is insufficient.

### Open gap

Controlled degradations could be sampled around a user's accepted edit: crop drift, competing local contrast, tone imbalance, or weakened subject-background separation. The key test is whether the model learns preference geometry rather than merely reversing known perturbations. Evaluation should use new photos and blinded pairwise user choices.

## 6. Musical foreground/background balance

### Existing research

- [Segregation and Integration of Auditory Streams when Listening to Multi-Part Music](https://pmc.ncbi.nlm.nih.gov/articles/PMC3901649/) finds perceptual hierarchy between melody and accompaniment and studies structural and temporal cues.
- [AutoSchA](https://ojs.aaai.org/index.php/AAAI/article/view/39640) learns hierarchical music representations and reports performance comparable to expert analysis for a constrained repertoire.
- [Encoder-Only Transformers for Melodic Harmonization](https://proceedings.mlr.press/v303/kaliakatsos-papakostas26a.html) models relationships between melody and accompaniment.

### Adjacent products or tools

- [iZotope Neutron](https://www.izotope.com/en/products/neutron/features/mix-assistant) provides AI-powered mix assistance and visual balancing tools.

### Open gap

A degradation generator could mask the intended lead through gain, spectral masking, dynamics flattening, or entrance timing while preserving notes and arrangement identity. The approach must be conditioned on genre and artistic intent; melody dominance is not a universal quality rule. Human listening tests are indispensable.

## 7. Host-conditioned codon optimization

### Existing research

- [CodonTransformer](https://www.nature.com/articles/s41467-025-58588-7) trains on more than one million DNA-protein pairs across 164 organisms and generates host-conditioned sequences.
- [DeepCodon](https://www.sciencedirect.com/science/article/pii/S2693125725000433) addresses multiple sequence-level objectives and reports experimental expression validation.
- [Codon optimization with deep learning to enhance protein expression](https://www.nature.com/articles/s41598-020-74091-z) is an earlier deep-learning approach to the task.

### Adjacent products or tools

- [Benchling codon optimization](https://help.benchling.com/hc/en-us/articles/9684246819213-Codon-optimize-sequences) exposes host, GC, hairpin, restriction-site, and motif constraints.
- [Twist Bioscience codon optimization](https://www.twistbioscience.com/faq/gene-synthesis/codon-optimization-what-steps-are-taken-maintain-wild-type-protein-expression) describes a proprietary multi-factor optimization process.

### Open gap

The direct task is already competitive. The catalog's distinct proposal is to start from experimentally successful sequences, generate synonymous degradations along named axes, and learn graded repair. The decisive evidence would be improved wet-lab expression on held-out proteins and hosts, not only CAI, GC, or RNA-folding proxies.

## 8. Gene-annotation structure repair

### Existing research

- [BRAKER3](https://genome.cshlp.org/content/early/2024/05/28/gr278090123) combines RNA-seq and protein evidence for automated eukaryotic annotation and reports substantial transcript-level gains.
- [NCBI Eukaryotic Genome Annotation Pipeline](https://www.ncbi.nlm.nih.gov/refseq/annotation_euk/process/) combines alignments, Gnomon prediction, filtering, and RefSeq integration.
- [Ensembl genome annotation](https://beta.ensembl.org/help/articles/gene-annotation) combines automated, manual, and imported evidence.

### Adjacent products or tools

- [NCBI EGAPx](https://github.com/ncbi/egapx) exposes an external version of the NCBI eukaryotic annotation pipeline.

### Open gap

Controlled corruption could shift splice sites, omit isoforms, merge neighboring genes, or remove evidence links. However, exact recovery of the source annotation is not sufficient because the source may itself be incomplete. Evaluation needs independent transcript, protein, long-read, conservation, and manual-curation evidence on naturally difficult genomes.

## 9. PCR-primer design repair

### Existing research

- [Primer3](https://primer3.org/manual.html) performs constrained primer selection using melting temperature, size, GC content, dimer risk, product size, positional constraints, and mispriming criteria.
- [Primer C-VAE](https://arxiv.org/abs/2503.01459) explores interpretable neural primer generation for emerging variants and closely related organisms.
- [Deep learning forward and reverse primer design](https://arxiv.org/abs/2209.13591) uses neural models to identify sequence features and propose variant-specific primer pairs.

### Adjacent products or tools

- [Primer3](https://primer3.org/) is a mature open-source design tool and a strong non-learning baseline.

### Open gap

Because many constraints are explicit and efficiently optimized, this candidate has a high risk of being unnecessary machine learning. A controlled-degradation approach is only compelling for objectives that are difficult to encode—robustness across future variants, laboratory-specific failure patterns, or empirical assay yield—and must beat exact optimization plus search baselines.

## 10. Clinical-note structure repair

### Existing research

- [Generalizable clinical note section identification with large language models](https://academic.oup.com/jamiaopen/article/7/3/ooae075/7732128) studies section identification across note types and reports transfer limitations.
- [MedSlice](https://academic.oup.com/jamiaopen/article/9/1/ooaf179/8425855) fine-tunes open models for secure section extraction and evaluates external validity.
- [SecTag](https://pubmed.ncbi.nlm.nih.gov/19717800/) is an earlier system for identifying explicit and implied clinical note sections.

### Adjacent products or tools

- The adjacent product category is ambient documentation and EHR note assistance. This scan did not identify a product whose explicit target is invariant-preserving structural repair of an existing note.

### Open gap

Sectioning is easier than safe reorganization. A repair model must preserve negation, chronology, attribution, uncertainty, medication details, and assessment-plan links. Evaluation must include clinician review and downstream safety checks; improved formatting alone is not evidence of improved clinical utility.

## 11. Patient-instruction clarity repair

### Existing research

- [A survey of automated methods for biomedical text simplification](https://pmc.ncbi.nlm.nih.gov/articles/PMC10161533/) identifies data scarcity and limited human-comprehension evidence as central barriers.
- [Paragraph-level Simplification of Medical Texts](https://pmc.ncbi.nlm.nih.gov/articles/PMC9161242/) introduces parallel technical/lay summaries and transformer baselines.
- [Enhancing the Readability of Online Patient Education Materials Using Large Language Models](https://pubmed.ncbi.nlm.nih.gov/40465378/) reports readability gains but also model-dependent inaccuracies.

### Adjacent products or tools

- General-purpose LLMs are already used experimentally for this task, but the evidence does not establish a validated autonomous patient-instruction product.

### Open gap

Readability formulas are weak proxies for comprehension. Directional degradation could preserve actions and facts while increasing jargon, separating conditions from actions, weakening warnings, or disordering steps. The required endpoint is layperson comprehension and correct action—not only lower grade level—and all outputs require clinical fidelity checks.

## 12. Educational explanation sequencing

### Existing research

- [Prerequisite Structure Discovery in Intelligent Tutoring Systems](https://arxiv.org/abs/2402.01672) learns knowledge-component structure from learner trajectories and evaluates it through recommendation.
- [A Pre-Trained Graph-Based Model for Adaptive Sequencing of Educational Documents](https://arxiv.org/abs/2411.11520) studies data-efficient learning-path personalization without extensive expert annotation.
- [Towards Comprehensive Argument Analysis in Education](https://aclanthology.org/2025.acl-long.696/) connects fine-grained discourse and argument structure to educational assessment.

### Adjacent products or tools

- Adaptive tutoring and course-recommendation systems are adjacent, but they generally optimize item selection or progression rather than repair the internal exposition of one explanation.

### Open gap

A degradation generator could delay prerequisites, detach examples from rules, insert irrelevant detail before the core idea, or disturb progressive difficulty. The challenge is transfer: artificial ordering mistakes may not represent real learner misconceptions. Evaluation needs learner-conditioned comprehension, retention, and error transfer.

## 13. Mathematical-proof exposition repair

### Existing research

- [Proof-Refactor](https://arxiv.org/abs/2606.03743) explicitly targets readability, modularity, maintainability, and reuse in formally verified proofs.
- [NaturalProver](https://arxiv.org/abs/2205.12910) generates natural-language proof steps grounded in references and evaluates usefulness with students.
- [A Natural Formalized Proof Language](https://arxiv.org/abs/2405.07973) develops a proof representation intended to bridge natural and formal proof communication.

### Adjacent products or tools

- [Lean](https://lean-lang.org/) provides machine-checked formal verification and is a natural invariant checker for correctness.

### Open gap

Controlled degradations such as inlining lemmas, hiding dependencies, replacing meaningful names, or removing motivation could create supervision for exposition repair. The target cannot be exact reconstruction: many clear proofs exist. Evaluation should combine formal validity, structural rubrics, reuse, and blinded mathematician or student review.

## 14. Philosophical-argument structure repair

### Existing research

- [End-to-end Argument Mining with Cross-corpora Multi-task Learning](https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00481/111222/End-to-end-Argument-Mining-with-Cross-corpora) identifies claims, premises, and relations while documenting cross-corpus transfer issues.
- [Segmentation of Argumentative Texts by Key Statements](https://aclanthology.org/2025.argmining-1.22/) reports that current methods, including LLMs, do not satisfactorily solve key-statement segmentation.
- [ArgAnalysis35K](https://aclanthology.org/2023.acl-long.778/) provides large-scale argument-quality annotations.

### Adjacent products or tools

- Argument-mining systems and argument-mapping software are adjacent, but this scan did not identify a mature product that repairs exposition while explicitly preserving philosophical commitments.

### Open gap

The degradation must preserve premises, conclusions, objections, modal force, scope, and dialectical position. Reordering can change pragmatic force even when propositions remain. Human philosophers should evaluate whether the repaired text is clearer without becoming a different argument.

## 15. Legal-contract readability repair

### Existing research

- [Unsupervised Simplification of Legal Texts](https://arxiv.org/abs/2209.00557) performs domain-specific lexical and syntactic simplification while attempting semantic preservation.
- [Evaluating Document Simplification](https://arxiv.org/abs/2404.03278) argues that simplicity and meaning preservation must be assessed separately.
- [The Use of Readability Metrics in Legal Text](https://arxiv.org/abs/2411.09497) finds fragmented metric usage and limited consensus across legal domains.

### Adjacent products or tools

- Contract-review products are adjacent, but clause extraction and risk detection are not equivalent to rewriting while guaranteeing identical legal effect.

### Open gap

This is among the highest-risk candidates. Controlled degradations could increase cross-reference distance, bury exceptions, split definitions from uses, or flatten clause grouping. The invariant—legal effect—is not cheaply verifiable. Any research must use lawyers, executable clause representations where possible, adversarial counterexamples, and explicit refusal to automate final legal approval.

## 16. Function-boundary recovery

### Existing research

- [Data-Driven Extract Method Recommendations: A Study at ING](https://arxiv.org/abs/2107.05396) evaluates learned extract-method recommendations in an industrial setting.
- [Just-in-time code duplicates extraction](https://www.sciencedirect.com/science/article/pii/S095058492300023X) trains on mined refactorings and reports an F-measure of 0.82 plus a developer study.
- [Recommending Extract Method Refactoring Based on Confidence of Predicted Method Name](https://arxiv.org/abs/2108.11011) uses method-name predictability as a semantic-coherence signal.

### Adjacent products or tools

- [IntelliJ IDEA Extract Method](https://www.jetbrains.com/help/idea/extract-method.html) performs the refactoring after a user selects the code region and explicitly supports the inverse Inline operation.

### Open gap

The proposed data generator is unusually direct: take accepted functions, inline them, then learn to recover boundaries, names, parameters, and return values. The critical split is held-out projects and held-out degradation implementations. Success must be measured on natural long methods and developer acceptance, not only reconstruction of the original helper.

## 17. Spreadsheet-model structure repair

### Existing research

- [Detecting and refactoring code smells in spreadsheet formulas](https://research.tudelft.nl/en/publications/detecting-and-refactoring-code-smells-in-spreadsheet-formulas/) adapts code smells to spreadsheets and evaluates automated suggestions.
- [Evaluating refactorings for spreadsheet models](https://www.sciencedirect.com/science/article/abs/pii/S0164121216300280) defines model-level refactorings and studies user productivity.
- [Automated Refactoring of Nested-IF Formulae in Spreadsheets](https://www.microsoft.com/en-us/research/publication/automated-refactoring-of-nested-if-formulae-in-spreadsheets/) evaluates automated formula refactoring at large scale.

### Adjacent products or tools

- Spreadsheet auditing and formula-assistance products are adjacent, but most focus on local formula correctness or generation rather than whole-model structure and maintainability.

### Open gap

Controlled degradations can duplicate formulas, scatter assumptions, mix inputs and outputs, inline lookup tables, or introduce inconsistent reference patterns while preserving computed outputs. The model should be tested on real workbooks, with formula equivalence, recalculation, scenario tests, and user maintenance tasks as independent evaluation.

## 18. Database-schema modularity repair

### Existing research

- [SQL schema design: foundations, normal forms, and normalization](https://www.sciencedirect.com/science/article/pii/S0306437917305069) develops formal dependencies and normalization algorithms for realistic SQL features.
- [Standard transformations for the normalization of ER schemata](https://www.sciencedirect.com/science/article/pii/0306437996000117) formalizes local schema transformations and an ER normal form.
- [A systematic review of interactive tools for database normalization learning](https://link.springer.com/article/10.1007/s10586-026-06166-x) catalogs interactive normalization tools and methodologies.

### Adjacent products or tools

- Database modeling products automate diagrams and migrations, while normalization itself already has strong exact algorithms when dependencies are known.

### Open gap

A learned model is justified only when intent and dependencies are incomplete or implicit: domain ownership, query workload, naming, service boundaries, or denormalization tradeoffs. Controlled degradation could merge entities or duplicate attributes, but the benchmark must compare against formal normalization and workload-aware optimization baselines.

## 19. CAD-assembly modularity repair

### Existing research

- [Multi-part kinematic constraint prediction for automatic generation of CAD model assemblies](https://www.sciencedirect.com/science/article/pii/S0010448524001325) predicts assembly constraints with graph neural networks.
- [Application of tensor factorisation for CAE model preparation from CAD assembly models](https://www.sciencedirect.com/science/article/pii/S0010448522001178) identifies similar parts and assembly inconsistencies in industrial models.
- [ASSEMCAD](https://arxiv.org/abs/2607.05123) represents assemblies through typed parts, ports, mates, and engineering axioms with geometric validation.

### Adjacent products or tools

- Commercial CAD systems support parts, assemblies, mates, and design reuse, but this scan did not identify a general product that proposes modular decomposition from intentionally flattened assemblies.

### Open gap

Controlled degradations could merge parts, flatten subassembly trees, hide interfaces, or degrade naming while preserving geometry and fit. The intended modularity depends on manufacturing, maintenance, procurement, and load paths—not geometry alone. Evaluation needs engineering-task outcomes and physical/kinematic validation.

## 20. Business-process simplification

### Existing research

- [Model repair—aligning process models to reality](https://www.sciencedirect.com/science/article/pii/S0306437913001725) repairs process models against event logs while minimizing change.
- [A survey on recommendation in process mining](https://onlinelibrary.wiley.com/doi/10.1002/cpe.7304) finds that process recommendation is emerging and lacks common datasets, metrics, and large-scale practical validation.
- [On the use of domain knowledge for process model repair](https://link.springer.com/article/10.1007/s10270-022-01067-0) argues that protected fragments and practitioner knowledge are necessary to avoid unusable repairs.

### Adjacent products or tools

- [Celonis Process Management](https://www.celonis.com/platform/process-management) combines process mining, target-state design, guardrails, and AI-assisted process modeling.

### Open gap

Controlled degradations could insert redundant approvals, delay information collection, split ownership, duplicate checks, or create avoidable handoffs while preserving required outcomes and controls. The core risk is realism: actual friction often encodes regulation, incentives, legacy-system limits, or segregation-of-duties requirements. Evaluation should use simulation, event logs, control coverage, and domain-owner review.

---

## Cross-cutting conclusion

The scan supports a narrower and more defensible claim than “nobody has tried learning from degraded good examples.” Corruption, inverse learning, refactoring, simplification, preference learning, and optimization already exist across these fields.

The recurring underexplored opportunity is:

> Use **named, graded, invariant-checked degradation operators** to create supervision for a quality direction that is otherwise expensive, subjective, or difficult to score; then prove transfer to naturally occurring failures using evaluation independent of the generator.

For Hacker News or research communication, the most credible framing is therefore:

1. acknowledge adjacent work;
2. make no blanket novelty claim;
3. identify the precise missing experiment for each domain;
4. require independent evaluation on natural failures;
5. invite domain experts to correct, reject, or implement candidates.
