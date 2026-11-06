# HDAC7-GBM Transcriptomics-Glioblastoma-stem-cells-on-HDAC7-knockdown-vs-CTRL-using-R

This repository presents the transcriptomic component of my doctoral research in cancer epigenetics at Brown University. Using R and Bioconductor, I examine how siRNA-mediated HDAC7 depletion changes gene expression in glioblastoma stem cells (GSCs), focusing on DNA replication, cell-cycle regulation, chromatin regulators, and stemness-associated programs.

# Project Overview :

Glioblastoma (GBM) is an aggressive brain tumor characterized by extensive cellular and epigenetic plasticity, with glioblastoma stem cells (GSCs) contributing to tumor maintenance and therapeutic resistance. While histone deacetylases (HDACs) are established therapeutic targets in cancer, the limited isoform specificity of many HDAC inhibitors can contribute to off-target effects and has motivated the development of more selective therapeutic strategies.

My doctoral research identified HDAC7, a class IIa histone deacetylase, as a potential epigenetic vulnerability in GBM. HDAC7 was found to be highly expressed in GBM and multiple other malignancies, while its inhibition impaired the self-renewal and viability of patient-derived GSCs.

This project investigates the transcriptional consequences of HDAC7 knockdown in patient-derived GSCs using RNA-seq and differential gene expression analysis. The broader research program combined transcriptomics, epigenomics, protein-interaction studies, functional assays, and therapeutic development to characterize the molecular role of HDAC7 and evaluate its potential as a selective therapeutic target in cancer.

## Biological question
Which transcriptional responses to HDAC7 knockdown are shared across patient-derived GSC models, and which depend on the individual model?

The working hypothesis is that HDAC7 supports transcriptional programs associated with GSC proliferation and stem-like state. Analyzing each model separately preserves patient-specific responses, while comparisons across models help identify recurring changes and biological heterogeneity.

This analysis forms part of a broader research program integrating transcriptomics with chromatin profiling, protein-interaction studies, and functional assays to investigate HDAC7 as a potential therapeutic target.

## Methods:
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


# Experimental Design :

RNA-seq was performed on patient-derived GSCs following HDAC7 siRNA knockdown

| Feature | Design |
|---|---|
| Biological system | Patient-derived glioblastoma stem cells |
| Models | GB2, GB11, and GB24, derived from three different patients |
| Perturbation | siRNA-mediated HDAC7 knockdown |
| Comparison | HDAC7 knockdown (`Kd`) versus control (`Ctrl`) |
| Samples | Two samples per condition per model; 8 samples in total |
| Assay | Bulk RNA-seq |
| Statistical approach | Separate DESeq2 analyses within each model |
| Primary significance threshold | Adjusted P-value < 0.05; additional thresholds explored including 0.01, 0.001|


## Analysis Strategy :

| Step | Analysis | Scientific purpose |
|---|---|---|
| 1 | Import expression matrices and define metadata | Establish sample identities, conditions, and input structure |
| 2 | Examine HDAC7 expression | Assess transcript-level evidence of the intended perturbation |
| 3 | PCA and sample-distance heatmaps | Examine replicate similarity and condition-associated variation |
| 4 | DESeq2 differential expression | Estimate expression changes and statistical support within each model |
| 5 | Volcano plots, MA plots, and gene heatmaps | Examine effect sizes, expression dependence, and sample-level patterns |
| 6 | Compare significant-gene lists across models | Identify overlapping responses for further assessment of directional agreement |
| 7 | GO overrepresentation analysis and ranked-list GSEA | Investigate functional themes beyond individual genes |
| 8 | Examine a biologically selected gene panel | Connect expression patterns with replication, mitosis, chromatin regulation, and candidate stemness mechanisms |

The notebook also documents external transcription-factor and stemness-enrichment analyses using ChEA3, StemChecker, and GSEA software.



## Biological Interpretation

- **DNA replication and cell-cycle response:** HDAC7 knockdown is associated with a coordinated decrease in expression of many genes in a selected panel across GB2, GB11, and GB24. Shared decreases include replication- and cell-cycle-associated critical genes include major regulators of DNA replication (mcm3, mcm4, mcm5, mcm7, and orc1),  G1–S phase transition of the cell cycle (MYC, E2F1, and CDC6). This pattern is consistent with reduced DNA replication and mitotic activity, supporting the cell-cycle themes identified in the GO enrichment analysis
- **Changes in key chromatin regulators and cancer stemness phenotype:** NOTCH1, NOTCH3, and DNMT1 show lower group means across the 3 models,  JMJD1C and MYC   decrease markedly in GB2 , suggesting that the response extends beyond proliferation to include changes in stemness-associated signaling and chromatin regulation
- **Embryonic Stemness Phenoytpe:** Numerous downregulated genes subsequent to HDAC7 inhibition are associated with stemness, particularly exhibiting an embryonic phenotype rather than neural stem or mesenchymal characteristics distinct from what could be anticipated. I reasoned that this suggests that HDAC7 might be involved in fundamental cellular regulation by reactivating cellular activities typically dormant post-embryogenesis. Additionally, gene enrichment analysis indicated that HDAC7 is associated with biological processes and pathways highly active during embryonic development or tumor formation. Furthermore, unsupervised clustering of RNA-seq data post-HDAC7 inhibition, as well as analysis of TCGA data against EMT signature gene sets, demonstrated that HDAC7 inhibition suppressed all GSCs subtypes indiscriminately, further indicating a more fundamental regulatory role for HDAC7 in GBM pathology.

## Final Conclusion
This analysis shows that targeted reduction of HDAC7 significantly disrupts the expression of nearly half of the genes in primary GSCs from RIH patients. Many of the genes that are downregulated following HDAC7 inhibition are known to be associated with DNA replication and stemness, particularly exhibiting an embryonic phenotype. We hypothesized that HDAC7 plays a role in fundamental cellular regulation by reactivating transcriptional programs typically active during embryonic development, which are supposed to be silenced beyond this stage of life. Consistent with this, our gene enrichment analysis indicate that HDAC7 is involved in biological processes related to cell cycle activities as well as chromatin reorganization.

### Full Analysis

**[View the complete knitted RNA-seq analysis →](https://olahassan000.github.io/HDAC7-GBM-Transcriptomics--R/)**

The full R Markdown workflow includes DESeq2 differential
expression analysis, visualization, pathway analysis, and biological
interpretation.


## Study context and disclosure

This repository accompanies the [published HDAC7 study in the Journal of Biological Chemistry](https://www.jbc.org/article/S0021-9258(25)02584-0/fulltext). Interpret this portfolio analysis alongside the paper's methods, data-access information, and experimental findings.

A patent application, **PCT/US2022/077910**, concerns HDAC7-specific inhibitors. Homer Therapeutics, Inc. is developing cancer therapeutics targeting HDAC7.
