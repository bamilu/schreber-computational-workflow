[README_PCS.md](https://github.com/user-attachments/files/28185013/README_PCS.md)
# Schreber Computational Workflow

## Overview

This repository contains all materials necessary to reproduce the analyses reported in:

> **Episodic Structure in Psychotic Discourse: A Reproducible Workflow for Modeling Meta-Communication and Delusional Ontology in Schreber's Memoirs**

The study proposes a reproducible computational framework for the analysis of psychotic discourse, operationalizing two theoretically grounded dimensions — meta-communication and delusional ontology — as paragraph-level lexical features in an extended narrative corpus. Applied to Daniel Paul Schreber's *Memoirs of My Nervous Illness*, the analysis tests competing structural models of psychotic discourse and finds evidence for an episodic, temporally heterogeneous architecture rather than continuous escalation or stable global coupling.

---

## Repository structure

```
.
├── README.md
├── _quarto.yml                        # Quarto project configuration
├── index.qmd                          # Master manuscript file
├── introduction.qmd
├── methods.qmd
├── results.qmd
├── discussion.qmd
├── conclusion.qmd
├── data_availability.qmd
├── references.bib                     # Full bibliography (APA 7)
├── apa7.csl                           # Citation style
├── data/
│   ├── schreber_segments_scored.csv   # 235 paragraph segments with scores
│   ├── keyness_peak_top.csv           # Keyness analysis: peak-favoring terms
│   └── keyness_nonpeak_top.csv        # Keyness analysis: non-peak terms
├── Schreber_memoirs.txt               # Curated corpus (UTF-8 plain text)
├── schreber_analysis.R                # Full R analysis pipeline
└── images/
    ├── time_series_scores.png         # Figure 1: temporal trajectory
    ├── meta_acf.png                   # Figure 2: ACF of meta-communication
    └── coupling_peaks.png             # Figure 3: coupling index with peaks
```

---

## Requirements

### R packages

All analyses were conducted in R 4.5 or later. The following packages are required:

```r
install.packages(c(
  "quanteda",
  "quanteda.textstats",
  "dplyr",
  "ggplot2",
  "readr"
))
```

### Quarto

To render the manuscript, [Quarto](https://quarto.org) version 1.5 or later is required.

---

## Reproducing the analyses

### Step 1 — Run the analysis pipeline

Open `schreber_analysis.R` in RStudio or run from the terminal:

```bash
Rscript schreber_analysis.R
```

This script reads `Schreber_memoirs.txt`, performs all segmentation, scoring, and statistical analyses, and writes the derived data to `data/schreber_segments_scored.csv` and all figures to `images/`.

### Step 2 — Render the manuscript

```bash
quarto render index.qmd --to docx
```

Or from the R console:

```r
quarto::quarto_render("index.qmd", output_format = "docx")
```

---

## Corpus note

The corpus (`Schreber_memoirs.txt`) was derived from:

> Schreber, D. P. (1903/2000). *Memoirs of my nervous illness* (I. Macalpine & R. A. Hunter, Trans.). New York Review of Books.

The digitization combined OCR processing of a printed edition with systematic manual curation to isolate Schreber's narrative voice and exclude non-authorial material (editorial apparatus, translator notes, running titles, page headers). The resulting corpus represents a processed derivative intended for paragraph-level computational analysis. All transformations are documented within `schreber_analysis.R`.

---

## Data

The derived dataset `schreber_segments_scored.csv` contains the following variables:

| Variable | Description |
|---|---|
| `seg_id` | Unique segment identifier |
| `order` | Sequential position in narrative |
| `words` | Word count per segment |
| `text` | Raw segment text |
| `meta_score` | Normalized meta-communication density |
| `delus_score` | Normalized delusional-ontology density |
| `paranoid_meta` | Multiplicative coupling index |

---

## Archived version

A static archived version of this repository corresponding to the submitted manuscript is available via Zenodo:

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19153006.svg)](https://doi.org/10.5281/zenodo.19153006)

---

## License

All code and derived data are released under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

The curated corpus (`Schreber_memoirs.txt`) is derived from a work in the public domain. The derived dataset is made available under CC-BY 4.0.
