# khan_et_al_4nqo_oscc_bcatcpb

Omics data analyses associated to the manuscript studying the role of beta-catenin (Ctnnb1) in 4NQO-induced oral squamous cell carcinoma (OSCC).

This repository contains R scripts and Rmarkdown files detailing the analysis of bulk and single-cell RNA-seq data.

## Experimental Design

The study uses a 4-Nitroquinoline 1-oxide (4NQO) mouse model of oral carcinogenesis with conditional perturbation of beta-catenin (CPB). Three experimental groups are analyzed:

- **Control**: Wild-type mice without 4NQO treatment
- **4NQO**: Wild-type mice treated with 4NQO to induce OSCC
- **4NQO + CPB**: 4NQO-treated mice with conditional Ctnnb1 (beta-catenin) knockout

## Directory Structure

```
/scripts
  /bulk         - Bulk RNA-seq analysis scripts
  /singlecell   - Single-cell RNA-seq analysis scripts
/data           - Input data (expression matrices, annotations, etc.)
/results        - Output results from analysis scripts
```

## Bulk RNA-seq Analysis

Scripts are numbered in order of execution:

| Script | Description |
|--------|-------------|
| `scripts/bulk/01_summstats_eset.{Rmd,html}` | Summary statistics, QC plots, and ExpressionSet creation |
| `scripts/bulk/02_diffanalysis.{Rmd,html}` | Pairwise differential expression analysis using DESeq2 |
| `scripts/bulk/03_enrichment.{Rmd,html}` | Pathway enrichment (ORA via hypeR) and GSVA signature scoring |

## Single-Cell RNA-seq Analysis

Scripts are numbered in order of execution:

| Script | Description |
|--------|-------------|
| `scripts/singlecell/01_qc_preprocessing.{Rmd,html}` | QC filtering, normalization, and dimensionality reduction (Seurat) |
| `scripts/singlecell/02_clustering.{Rmd,html}` | Unsupervised clustering and cell type annotation |
| `scripts/singlecell/03_diffanalysis.{Rmd,html}` | Differential expression per cell type using MAST |
| `scripts/singlecell/04_enrichment.{Rmd,html}` | ORA (hypeR), gene module scoring, and cell proportion analysis |

## Dependencies

Key R packages used:

- **Seurat** — single-cell analysis
- **DESeq2** — bulk differential expression
- **MAST** — single-cell differential expression
- **hypeR** — geneset enrichment (ORA)
- **GSVA** — gene set variation analysis
- **Biobase** — ExpressionSet objects
- **ggplot2**, **pheatmap**, **DT** — visualization and reporting
