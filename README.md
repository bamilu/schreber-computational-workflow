# Episodic Structure in Psychotic Discourse

**A reproducible computational workflow for modeling meta-communication and delusional ontology in Schreber’s *Memoirs of My Nervous Illness***

## Overview

This repository contains the code, derived data, manuscript files, and supplementary materials for the article:

**Barreiros, L. M. J. L.**  
*Episodic Structure in Psychotic Discourse: A Reproducible Workflow for Modeling Meta-Communication and Delusional Ontology in Schreber’s Memoirs.*

The project develops a reproducible computational framework for analyzing psychotic discourse as a temporally organized textual process. Drawing on pragmatic communication theory, phenomenological psychopathology, and computational text analysis, it operationalizes two discourse-level dimensions, **meta-communication** and **delusional ontology**, and examines their interaction across Schreber’s narrative through paragraph-level scoring and temporal analysis.

Rather than treating psychotic discourse as a uniformly escalating system, the workflow tests whether discursive intensification is globally cumulative or locally episodic. The analyses reported in the manuscript support the latter interpretation, identifying a limited number of high-coupling segments in which meta-communicative framing and delusional ontology become selectively aligned.

## Repository contents

This repository is structured as a Quarto manuscript project.

```text
Schreber_computational_workflow/
├── _quarto.yml
├── index.qmd
├── introduction.qmd
├── methods.qmd
├── results.qmd
├── discussion.qmd
├── conclusion.qmd
├── reproducibility_data_availability.qmd
├── references.bib
├── README.md
│
├── notebooks/
│   └── 01-analysis.qmd
│
├── supplementary/
│   └── supplement.qmd
│
├── scripts/
├── data/
├── tables/
├── images/
├── csl/
├── notes/
└── files_submission_QCMB/
```

## Main components

### Manuscript

The article is organized as a Quarto manuscript with separate section files:

- `index.qmd`  
  Main manuscript file, containing metadata, title, abstract, and assembly of article sections.

- `introduction.qmd`  
  Theoretical framing of psychotic discourse, pragmatics, phenomenology, and computational operationalization.

- `methods.qmd`  
  Corpus construction, paragraph segmentation, lexical scoring, coupling index, and statistical strategy.

- `results.qmd`  
  Empirical findings, including global association, temporal clustering, lag structure, and peak identification.

- `discussion.qmd`  
  Interpretation of findings in relation to phenomenological and communicational models of psychosis.

- `conclusion.qmd`  
  Final synthesis of theoretical and methodological implications.

- `reproducibility_data_availability.qmd`  
  Statement on data, code, and repository availability.

### Analysis notebook

- `notebooks/01-analysis.qmd`  
  Executable notebook containing the core computational workflow used to generate the principal analyses reported in the manuscript.

### Supplementary materials

- `supplementary/supplement.qmd`  
  Supplementary methodological and analytical material accompanying the article.

### Bibliography and style

- `references.bib`  
  BibTeX database used by the manuscript.

- `csl/apa7.csl`  
  Citation style file.

## What is reproduced here

The repository provides the materials necessary to inspect, reproduce, and extend the computational workflow described in the article, including:

- the Quarto manuscript source files;
- the executable R/Quarto analysis notebook;
- the derived analytical dataset used in the reported analyses;
- figures and tables generated from the workflow;
- supplementary material documenting additional methodological details.

## Data provenance and copyright note

This project analyzes **Schreber’s *Memoirs of My Nervous Illness*** as a historical and theoretical corpus.

The original published source text is not redistributed here as a direct facsimile of any single edition, and users should not assume that the repository contains a copyright-equivalent full-text reproduction of the source volume. Instead, the repository documents and uses a curated derivative corpus and/or derived analytical dataset produced for computational research purposes.

Accordingly, the materials provided here should be understood at three distinct levels:

1. **Original source text**  
   The published edition of Schreber’s *Memoirs of My Nervous Illness*, which remains subject to the legal and editorial status of the edition consulted.

2. **Curated derivative corpus**  
   A research-oriented textual representation prepared for segmentation, scoring, and computational analysis.

3. **Derived analytical dataset**  
   The paragraph-level scored dataset used for the statistical analyses reported in the manuscript.

Users remain responsible for ensuring that any reuse of source-text material complies with applicable copyright rules and edition-specific restrictions.

## Computational workflow

The analytical workflow implemented in this repository includes the following stages:

1. **Corpus preparation**  
   The narrative is segmented into paragraph-level units.

2. **Lexical operationalization**  
   Two main discourse dimensions are operationalized through dictionary-based scoring:
   - meta-communication
   - delusional ontology

3. **Coupling index construction**  
   These dimensions are combined into a derived index representing their local interaction.

4. **Temporal analysis**  
   The workflow evaluates:
   - global association between dimensions;
   - serial persistence;
   - lagged relationships;
   - peak segments of high coupling.

5. **Interpretive integration**  
   The resulting patterns are interpreted in relation to discourse theory, phenomenological psychopathology, and computational approaches to psychosis research.

## Software environment

The project was developed in **R** and **Quarto**.

Core packages used in the analysis include, among others:

- `dplyr`
- `stringr`
- `readr`
- `tidyr`
- `ggplot2`
- `quanteda`
- `quanteda.textstats`

Exact package versions should be documented either in the session information of the notebook, a lockfile, or the final release materials associated with the submission.

## How to reproduce the manuscript

### 1. Clone the repository

```bash
git clone [INSERT-REPOSITORY-URL]
cd Schreber_computational_workflow
```

### 2. Open the project in RStudio

Open the repository as an R project or Quarto project.

### 3. Install dependencies

Install the required R packages if they are not already available in your system.

Example:

```r
install.packages(c(
  "dplyr",
  "stringr",
  "readr",
  "tidyr",
  "ggplot2",
  "quanteda",
  "quanteda.textstats"
))
```

### 4. Render the manuscript

To render the full manuscript:

```bash
quarto render
```

This will generate the manuscript outputs specified in `_quarto.yml`, including article formats and the MECA bundle.

### 5. Render the analysis notebook only

To render the main computational notebook independently:

```bash
quarto render notebooks/01-analysis.qmd
```

### 6. Render the supplementary materials only

To render the supplementary notebook independently:

```bash
quarto render supplementary/supplement.qmd
```

## Outputs

The Quarto manuscript configuration is set to generate multiple output formats, including:

- HTML
- PDF
- DOCX
- JATS
- MECA bundle

The MECA bundle is specified in `_quarto.yml` as:

```yaml
meca-bundle: "schreber-meca.zip"
```

## Reproducibility statement

This repository is intended to support transparent and inspectable computational scholarship. The aim is not merely to provide a static article, but to expose the analytical logic of the study in a form that can be reviewed, rerun, and extended.

The project therefore functions simultaneously as:

- a manuscript;
- an executable workflow;
- a code repository;
- a derived-data repository;
- a methodological record of the study.

## Status

Current status of the repository:

**Submission-ready academic workflow for a computational article prepared for journal submission.**

Before public release or archival deposit, the following should be finalized where applicable:

- permanent repository URL;
- DOI for archived release;
- final data-availability wording;
- package/session provenance details;
- confirmation of which derived corpus materials can be redistributed openly.

## Suggested citation

If you use or refer to this repository, please cite the associated article version or archived release.

**Manuscript citation, provisional form:**

Barreiros, L. M. J. L. *Episodic Structure in Psychotic Discourse: A Reproducible Workflow for Modeling Meta-Communication and Delusional Ontology in Schreber’s Memoirs.*

## License

[INSERT LICENSE]

If no open license has yet been chosen, do not leave the repository ambiguous at the moment of public release. The manuscript, code, and derived data may require different licensing decisions.

## Contact

For questions regarding the repository, manuscript, or reproducibility materials:

**Luís Miguel J. L. Barreiros**  
[luismiguelbarreiros@gmail.com; luis.miguel.barreiros@ubi.pt / [ORCID](https://orcid.org/0000-0003-4037-988X) / University of Beira Interior]
