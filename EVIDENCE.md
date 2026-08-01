# Evidence Types and Source Maturity

_Last reviewed: 2026-08-01._

This file classifies representative sources cited in [`LANDSCAPE.md`](LANDSCAPE.md). It is intended to prevent peer-reviewed research, preprints, official documentation, and product marketing from being treated as equivalent evidence.

This is a scoped classification, not a systematic literature review. Venue status, publication metadata, and links should be rechecked before making novelty or effectiveness claims.

## Evidence labels

- **`[peer-reviewed journal]`** — published journal article.
- **`[peer-reviewed proceedings]`** — published conference or workshop proceedings paper.
- **`[accepted / forthcoming]`** — accepted or journal-listed work whose final issue may be future-dated.
- **`[preprint]`** — manuscript available without relying on completed peer review.
- **`[dataset]`** — source primarily establishes a dataset or benchmark.
- **`[official tool or documentation]`** — documentation maintained by the tool, institution, or standards body.
- **`[official product page]`** — first-party description of a commercial product. This supports existence and claimed features, not independent effectiveness.
- **`[secondary source]`** — survey, overview, or other source not serving as primary evidence for the specific claim.
- **`[unverified]`** — evidence type or bibliographic status still needs checking.

## General rules

1. A preprint can establish that an idea has been proposed, but not that its claims are settled.
2. A product page can establish that a feature is advertised, but not that it works independently or uses this method.
3. A peer-reviewed paper can still be narrow, incorrect, or non-replicated.
4. Adjacent work is not direct precedent unless it actually uses controlled directional degradation for the same inverse task.
5. “No direct precedent found” means only that this scoped search did not find one.

## Candidate-by-candidate evidence map

### 1. Poster attention-flow restoration

- `[peer-reviewed journal]` [Poster graphic design with your Eyes](https://www.sciencedirect.com/science/article/pii/S0141938223000914)
- `[accepted / forthcoming]` [Learning priority-aware controllable poster layout generation](https://www.sciencedirect.com/science/article/abs/pii/S0031320326004632)
- `[peer-reviewed journal]` [Reverse-engineering information presentations](https://link.springer.com/article/10.1007/s44267-023-00010-1)
- `[official product page]` [Adobe Express Poster Maker](https://www.adobe.com/express/create/poster)

**Evidence note:** saliency-aware generation and hierarchy extraction are established adjacent tasks. Transfer from synthetic hierarchy damage to natural weak posters remains a hypothesis.

### 2. Single-slide information hierarchy

- `[peer-reviewed proceedings]` [SlideCoder](https://aclanthology.org/2025.emnlp-main.458/)
- `[peer-reviewed proceedings]` [Design First, Code Later](https://aclanthology.org/2026.findings-acl.1524/)
- `[peer-reviewed journal]` [Reverse-engineering information presentations](https://link.springer.com/article/10.1007/s44267-023-00010-1)
- `[official product page]` [Copilot in PowerPoint](https://support.microsoft.com/en-us/powerpoint/copilot/keep-your-presentation-on-brand-with-copilot)

**Evidence note:** generation and reconstruction are well represented. Fixed-content hierarchy repair is narrower and less directly evidenced.

### 3. Scientific-figure clarity repair

- `[preprint]` [SciFig](https://arxiv.org/abs/2601.04390)
- `[preprint]` `[dataset]` [SciFigQual-Bench](https://arxiv.org/abs/2607.27084)
- `[peer-reviewed proceedings]` [GPT-4 as an Effective Zero-Shot Evaluator for Scientific Figure Captions](https://aclanthology.org/2023.findings-emnlp.363/)
- `[official product page]` [BioRender](https://www.biorender.com/)

**Evidence note:** the most directly relevant automated figure work is recent. Scientific misleadingness and invariant preservation remain weakly established.

### 4. Data-visualization narrative alignment

- `[peer-reviewed proceedings]` [Attention-Aware Visualization](https://content-staging.ieeevis.org/year/2024/paper_v-full-1480.html)
- `[peer-reviewed proceedings]` [Narrative Player](https://mp1.ieeevis.org/year/2025/program/paper_a8c54e73-a078-47b8-94b9-8b8dfda73721.html)
- `[peer-reviewed journal or proceedings]` [The Impact of Elicitation and Contrasting Narratives](https://ieeevis.org/year/2024/program/paper_v-tvcg-20243355884.html)
- `[official product page]` [Tableau](https://www.tableau.com/)

**Evidence note:** attention and narrative effects are established. Truth-preserving repair toward a declared analytical intent is not established by these sources.

### 5. Personalized photo-editing recovery

- `[peer-reviewed proceedings]` [Learning Personalized Photographic Style from Pairwise User Preferences](https://openaccess.thecvf.com/content/CVPR2026/html/Kim_Learning_Personalized_Photographic_Style_from_Pairwise_User_Preferences_CVPR_2026_paper.html)
- `[peer-reviewed proceedings]` [PieNet](https://www.ecva.net/papers/eccv_2020/papers_ECCV/html/7579_ECCV_2020_paper.php)
- `[peer-reviewed proceedings]` [Multimodal Prediction and Personalization of Photo Edits](https://proceedings.mlr.press/v84/saeedi18a.html)

**Evidence note:** personalization and multiple valid edits are established. Directional degradation around a user's accepted edit is a narrower training proposal.

### 6. Musical foreground/background balance

- `[peer-reviewed journal]` [Segregation and Integration of Auditory Streams when Listening to Multi-Part Music](https://pmc.ncbi.nlm.nih.gov/articles/PMC3901649/)
- `[peer-reviewed proceedings]` [AutoSchA](https://ojs.aaai.org/index.php/AAAI/article/view/39640)
- `[peer-reviewed proceedings]` [Encoder-Only Transformers for Melodic Harmonization](https://proceedings.mlr.press/v303/kaliakatsos-papakostas26a.html)
- `[official product page]` [iZotope Neutron](https://www.izotope.com/en/products/neutron/features/mix-assistant)

**Evidence note:** perceptual hierarchy and mix assistance are adjacent. A universal foreground rule is not supported; conditioning on genre and intent is essential.

### 7. Host-conditioned codon optimization

- `[peer-reviewed journal]` [CodonTransformer](https://www.nature.com/articles/s41467-025-58588-7)
- `[peer-reviewed journal]` [DeepCodon](https://www.sciencedirect.com/science/article/pii/S2693125725000433)
- `[peer-reviewed journal]` [Codon optimization with deep learning to enhance protein expression](https://www.nature.com/articles/s41598-020-74091-z)
- `[official tool or documentation]` [Benchling codon optimization](https://help.benchling.com/hc/en-us/articles/9684246819213-Codon-optimize-sequences)
- `[official product page]` [Twist Bioscience codon optimization](https://www.twistbioscience.com/faq/gene-synthesis/codon-optimization-what-steps-are-taken-maintain-wild-type-protein-expression)

**Evidence note:** the base task is crowded and mature. A new project needs wet-lab evidence beyond the proxies used to create degradation.

### 8. Gene-annotation structure repair

- `[peer-reviewed journal]` [BRAKER3](https://genome.cshlp.org/content/early/2024/05/28/gr278090123)
- `[official tool or documentation]` [NCBI Eukaryotic Genome Annotation Pipeline](https://www.ncbi.nlm.nih.gov/refseq/annotation_euk/process/)
- `[official tool or documentation]` [Ensembl genome annotation](https://beta.ensembl.org/help/articles/gene-annotation)
- `[official tool or documentation]` [NCBI EGAPx](https://github.com/ncbi/egapx)

**Evidence note:** automated annotation is established. Corrupted-annotation training that improves naturally difficult genomes remains unverified.

### 9. PCR-primer design repair

- `[official tool or documentation]` [Primer3 manual](https://primer3.org/manual.html)
- `[preprint]` [Primer C-VAE](https://arxiv.org/abs/2503.01459)
- `[preprint]` [Deep learning forward and reverse primer design](https://arxiv.org/abs/2209.13591)

**Evidence note:** exact constrained design is a strong baseline. Machine learning is justified only for objectives not captured by established optimization.

### 10. Clinical-note structure repair

- `[peer-reviewed journal]` [Generalizable clinical note section identification with large language models](https://academic.oup.com/jamiaopen/article/7/3/ooae075/7732128)
- `[peer-reviewed journal]` [MedSlice](https://academic.oup.com/jamiaopen/article/9/1/ooaf179/8425855)
- `[peer-reviewed journal]` [SecTag](https://pubmed.ncbi.nlm.nih.gov/19717800/)

**Evidence note:** section identification is established. Safe invariant-preserving reorganization of an existing note is a substantially harder claim.

### 11. Patient-instruction clarity repair

- `[peer-reviewed journal]` `[secondary source]` [Survey of automated biomedical text simplification](https://pmc.ncbi.nlm.nih.gov/articles/PMC10161533/)
- `[peer-reviewed journal]` `[dataset]` [Paragraph-level Simplification of Medical Texts](https://pmc.ncbi.nlm.nih.gov/articles/PMC9161242/)
- `[peer-reviewed journal]` [Enhancing the Readability of Online Patient Education Materials Using Large Language Models](https://pubmed.ncbi.nlm.nih.gov/40465378/)

**Evidence note:** readability improvement does not establish comprehension, action accuracy, or clinical fidelity.

### 12. Educational explanation sequencing

- `[preprint]` [Prerequisite Structure Discovery in Intelligent Tutoring Systems](https://arxiv.org/abs/2402.01672)
- `[preprint]` [Adaptive Sequencing of Educational Documents](https://arxiv.org/abs/2411.11520)
- `[peer-reviewed proceedings]` [Towards Comprehensive Argument Analysis in Education](https://aclanthology.org/2025.acl-long.696/)

**Evidence note:** learning-path sequencing is adjacent. Repairing the internal exposition of one explanation using synthetic mistakes remains a hypothesis.

### 13. Mathematical-proof exposition repair

- `[preprint]` [Proof-Refactor](https://arxiv.org/abs/2606.03743)
- `[preprint]` [NaturalProver](https://arxiv.org/abs/2205.12910)
- `[preprint]` [A Natural Formalized Proof Language](https://arxiv.org/abs/2405.07973)
- `[official tool or documentation]` [Lean](https://lean-lang.org/)

**Evidence note:** the closest refactoring work is recent and largely preprint-based. Formal correctness is easier to verify than explanatory quality.

### 14. Philosophical-argument structure repair

- `[peer-reviewed journal]` [End-to-end Argument Mining with Cross-corpora Multi-task Learning](https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00481/111222/End-to-end-Argument-Mining-with-Cross-corpora)
- `[peer-reviewed proceedings]` [Segmentation of Argumentative Texts by Key Statements](https://aclanthology.org/2025.argmining-1.22/)
- `[peer-reviewed proceedings]` `[dataset]` [ArgAnalysis35K](https://aclanthology.org/2023.acl-long.778/)

**Evidence note:** argument mining is established, but clarity-preserving philosophical rewriting is not established by these sources.

### 15. Legal-contract readability repair

- `[preprint]` [Unsupervised Simplification of Legal Texts](https://arxiv.org/abs/2209.00557)
- `[preprint]` [Evaluating Document Simplification](https://arxiv.org/abs/2404.03278)
- `[preprint]` [The Use of Readability Metrics in Legal Text](https://arxiv.org/abs/2411.09497)

**Evidence note:** the cited evidence is preprint-heavy, and legal-effect invariance is not cheaply verifiable. This candidate requires specialist review before strong claims.

### 16. Function-boundary recovery

- `[preprint]` [Data-Driven Extract Method Recommendations](https://arxiv.org/abs/2107.05396)
- `[peer-reviewed journal]` [Just-in-time code duplicates extraction](https://www.sciencedirect.com/science/article/pii/S095058492300023X)
- `[preprint]` [Extract Method Based on Predicted Method Name](https://arxiv.org/abs/2108.11011)
- `[official tool or documentation]` [IntelliJ IDEA Extract Method](https://www.jetbrains.com/help/idea/extract-method.html)

**Evidence note:** extraction recommendation is established. Inverse-inline generation must prove transfer to natural long methods and held-out projects.

### 17. Spreadsheet-model structure repair

- `[unverified]` [Detecting and refactoring code smells in spreadsheet formulas](https://research.tudelft.nl/en/publications/detecting-and-refactoring-code-smells-in-spreadsheet-formulas/)
- `[peer-reviewed journal]` [Evaluating refactorings for spreadsheet models](https://www.sciencedirect.com/science/article/abs/pii/S0164121216300280)
- `[unverified]` [Automated Refactoring of Nested-IF Formulae in Spreadsheets](https://www.microsoft.com/en-us/research/publication/automated-refactoring-of-nested-if-formulae-in-spreadsheets/)

**Evidence note:** spreadsheet smells and refactoring are established, but the bibliographic status of some landing pages should be verified before publication claims.

### 18. Database-schema modularity repair

- `[peer-reviewed journal]` [SQL schema design: foundations, normal forms, and normalization](https://www.sciencedirect.com/science/article/pii/S0306437917305069)
- `[peer-reviewed journal]` [Standard transformations for normalization of ER schemata](https://www.sciencedirect.com/science/article/pii/0306437996000117)
- `[peer-reviewed journal]` `[secondary source]` [Systematic review of database normalization learning tools](https://link.springer.com/article/10.1007/s10586-026-06166-x)

**Evidence note:** exact normalization is mature when dependencies are known. The open question concerns implicit intent, ownership, and workload tradeoffs.

### 19. CAD-assembly modularity repair

- `[peer-reviewed journal]` [Kinematic constraint prediction for CAD assemblies](https://www.sciencedirect.com/science/article/pii/S0010448524001325)
- `[peer-reviewed journal]` [Tensor factorisation for CAE model preparation](https://www.sciencedirect.com/science/article/pii/S0010448522001178)
- `[preprint]` [ASSEMCAD](https://arxiv.org/abs/2607.05123)

**Evidence note:** assembly representation and constraint prediction are adjacent. Manufacturing- and maintenance-aware modularity repair remains unverified.

### 20. Business-process simplification

- `[peer-reviewed journal]` [Model repair—aligning process models to reality](https://www.sciencedirect.com/science/article/pii/S0306437913001725)
- `[peer-reviewed journal]` `[secondary source]` [Survey on recommendation in process mining](https://onlinelibrary.wiley.com/doi/10.1002/cpe.7304)
- `[peer-reviewed journal]` [Domain knowledge for process model repair](https://link.springer.com/article/10.1007/s10270-022-01067-0)
- `[official product page]` [Celonis Process Management](https://www.celonis.com/platform/process-management)

**Evidence note:** process repair and recommendation are established. Synthetic friction must be shown to represent real constraints without deleting controls.

## Maintenance checklist

Before citing this repository publicly:

1. check that every link still resolves;
2. confirm publication year, venue, and evidence label;
3. replace landing pages with DOI or canonical proceedings links where available;
4. distinguish source claims from independent replications;
5. mark newly discovered direct precedents;
6. downgrade or remove open-gap claims when prior work closes them;
7. request domain review for high-stakes candidates.
