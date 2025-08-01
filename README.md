# CircRes_2025_QC_pipeline
R scripts for data processing and QC from our 2025 Circulation Research paper - Isolevuglandins Modulate Histone H1 in Myeloid cells in Salt-Sensitive Hypertension

# salty-chromatin

This repository contains the R code used in our manuscript:  
**"Isolevuglandins modulate histone H1 in myeloid cells in salt-sensitive hypertension"**

The analysis focuses on multiomic single-cell ATAC and gene expression data derived from PBMCs isolated from salt-sensitive (SS) and salt-resistant (SR) individuals. Using the Seurat + Signac + chromVAR pipeline, we investigate chromatin accessibility changes in response to IsoLG stress, highlighting histone H1 dynamics in myeloid populations.

> 💡 This script was written for transparency and reproducibility, enabling others to replicate our pipeline and build upon our findings.

## 🔧 Requirements

This analysis was developed and tested in **R version 4.3.1**. You will need the following R packages (installed via CRAN or Bioconductor):

### CRAN:
- `ggplot2`
- `dplyr`
- `tibble`
- `future`
- `irlba`
- `Matrix`
- `patchwork`
- `ggpubr`

### Bioconductor:
- `BiocManager`
- `S4Vectors`
- `IRanges`
- `GenomicRanges`
- `AnnotationHub`
- `EnsDb.Hsapiens.v86`
- `BSgenome.Hsapiens.UCSC.hg38`
- `GO.db`
- `TFBSTools`
- `chromVAR`
- `multtest`
- `metap`

### From CRAN/Bioc but specialized:
- `Seurat`
- `Signac`
- `sctransform`
- `glmGamPoi`
- `batchelor`
- `monocle3`
- `JASPAR2020`
- `scCustomize`

Install all required packages with:

```r
# CRAN
install.packages(c("ggplot2", "dplyr", "tibble", "future", "irlba", "Matrix", "patchwork", "ggpubr"))

# Bioconductor core + packages
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install(c("S4Vectors", "IRanges", "GenomicRanges", "AnnotationHub",
                       "EnsDb.Hsapiens.v86", "BSgenome.Hsapiens.UCSC.hg38",
                       "GO.db", "TFBSTools", "chromVAR", "multtest", "metap"))

# Seurat/Signac ecosystem
install.packages("Seurat")
BiocManager::install(c("Signac", "sctransform", "glmGamPoi", "batchelor", "monocle3", "JASPAR2020"))

# Optional but used in the script
devtools::install_github("samuel-marsh/scCustomize")
