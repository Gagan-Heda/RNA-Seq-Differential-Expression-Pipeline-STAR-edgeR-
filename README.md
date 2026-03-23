# RNA-Seq Differential Expression Pipeline (STAR + edgeR)

An end-to-end RNA-seq analysis workflow for gene expression quantification and differential expression analysis. Integrates preprocessing, alignment, normalization, statistical testing, and visualization.

---

## Overview

This pipeline processes raw RNA-seq reads to generate high-quality gene expression data and identify differentially expressed genes (DEGs) between conditions. Designed for reproducibility and high-throughput datasets, it combines Unix-based preprocessing with R-based statistical modeling.

**Core Goals:**

- Process and trim RNA-seq reads  
- Align reads to a reference genome  
- Quantify gene-level expression  
- Normalize and filter expression data  
- Identify DEGs using robust statistical methods  
- Visualize sample relationships and expression trends  

---

## Workflow

### 1. Preprocessing
- Adapter trimming with Cutadapt  
- Quality filtering of reads  

### 2. Alignment & Quantification
- STAR two-pass alignment for accurate splice junction detection  
- Output:
  - Sorted BAM files  
  - Gene-level count tables (`ReadsPerGene.out.tab`)  

### 3. Data Integration
- Merge counts across samples into a single matrix  
- Format: genes × samples  

### 4. Normalization & Filtering
- Create DGEList object in edgeR  
- Filter lowly expressed genes  
- Apply normalization for library size differences  

### 5. Exploratory Analysis
- Multidimensional scaling (MDS) plots  
- Sample clustering based on expression profiles  

### 6. Dispersion Estimation
- Common, tagwise, and GLM-based dispersion  
- Visualize trends with BCV plots  

### 7. Differential Expression
- edgeR exact test for DEGs  
- Multiple testing correction (Benjamini–Hochberg)  
- Generate significant gene lists  

### 8. Visualization
- MDS plots for sample relationships  
- BCV plots for dispersion trends  
- Smear plots (log fold change vs expression)  

---

## Technologies

- Bash & Unix (workflow automation)  
- SLURM (HPC scheduling)  
- STAR (alignment)  
- Cutadapt (read trimming)  
- R (edgeR, baySeq, data.table)  

---

## Key Features

- Fully automated, reproducible workflow  
- Integration of alignment, quantification, and statistical analysis  
- Handles multi-sample datasets efficiently  
- Produces publication-ready visualizations  

---

## Skills Demonstrated

- RNA-seq data processing and QC  
- Differential expression analysis  
- Statistical modeling in R  
- High-throughput data workflow automation  
- Data visualization for transcriptomics  

---

## Notes

- Designed for comparing two biological conditions (e.g., HBR vs UHR)  
- Filters low-expression genes before analysis  
- Multiple normalization and dispersion estimation methods ensure robust results  

---

## Author

**Gagan Heda**
