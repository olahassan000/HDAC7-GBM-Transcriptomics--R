# HDAC7-GBM Transcriptomics-Glioblastoma-stem-cells-on-HDAC7-knockdown-vs-CTRL-using-R
Transcriptomic analysis of patient-derived glioblastoma stem cells following HDAC7 knockdown, performed as part of my PhD research in cancer epigenetics at Brown University.
This project investigates how HDAC7 depletion alters transcriptional programs associated with glioblastoma stem-cell state, tumor progression, and therapeutic response.


# Methods:
- R (Markdown)
- DESeq2
- Bioconductor
- PCA
- Pheatmap
- ClusterProfiler
- ggplot2
- enrichplot
- Gene Ontology enrichment
- GSEA


# Project Overview :

Glioblastoma (GBM) is an aggressive brain tumor characterized by extensive cellular and epigenetic plasticity, with glioblastoma stem cells (GSCs) contributing to tumor maintenance and therapeutic resistance. While histone deacetylases (HDACs) are established therapeutic targets in cancer, the limited isoform specificity of many HDAC inhibitors can contribute to off-target effects and has motivated the development of more selective therapeutic strategies.

My doctoral research identified HDAC7, a class IIa histone deacetylase, as a potential epigenetic vulnerability in GBM. HDAC7 was found to be highly expressed in GBM and multiple other malignancies, while its inhibition impaired the self-renewal and viability of patient-derived GSCs.

This project investigates the transcriptional consequences of HDAC7 knockdown in patient-derived GSCs using RNA-seq and differential gene expression analysis. The broader research program combined transcriptomics, epigenomics, protein-interaction studies, functional assays, and therapeutic development to characterize the molecular role of HDAC7 and evaluate its potential as a selective therapeutic target in cancer.


# Research Question :

How does HDAC7 inhibition alter transcriptional programs in patient-derived glioblastoma stem cells, and what do these changes reveal about its role in cancer stemness and tumor-associated pathways?

# Hypothesis :

HDAC7 functions as an important epigenetic regulator of glioblastoma stem-cell state, and its inhibition will disrupt transcriptional programs associated with cancer stemness and tumor progression.

# Experimental Design :

RNA-seq was performed on patient-derived GSCs following HDAC7 siRNA knockdown

- Biological system: Patient-derived GSCs
- Perturbation: HDAC7 knockdown using siRNA
- Comparison: siHDAC7 vs. sicontrol
- Assay: Bulk RNA-seq
- Primary analysis: Differential gene expression using DESeq2
- Downstream analyses: PCA, differential expression visualization, gene-level interrogation, and pathway enrichment/GSEA

## Analysis Strategy :

Raw/counts RNA-seq data were processed into gene-level expression matrices, QC'ed and analyzed using an R/Bioconductor workflow. Differential expression was evaluated independently across GSC models to identify transcriptional responses to HDAC7 inhibition, followed by pathway-level analyses to determine the biological programs affected by HDAC7 knockdown.

### GSC model: GSCs from 3 diffrent GBM patients, 2 replica each
- GSC 1 (GBM2): siHDAC7 vs CTRL
- GSC 2 (GBM11): siHDAC7 vs CTRL
- GSC 3 (GB24): siHDAC7 vs CTRL

### Full Analysis

**[View the complete knitted RNA-seq analysis →]([[(https://olahassan000.github.io/HDAC7-GBM-Transcriptomics-)])**

The full R Markdown workflow includes DESeq2 differential
expression analysis, visualization, pathway analysis, and biological
interpretation.


### Confidentiality

This work is part of the  published study (https://www.jbc.org/article/S0021-9258(25)02584-0/fulltext), the data used here are publicly available.


### Conflict of interest

There is a patent application (PCT/US2022/077910) for HDAC7-specific inhibitors. Homer Therapeutics, Inc, is working to develop cancer therapeutics, specifically targeting HDAC7. 
