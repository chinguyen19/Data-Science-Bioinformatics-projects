# Prostate Cancer Transcriptome Analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Findings](#findings)

## Project Overview
This project investigates the **transcriptome differences** between untreated prostate cancer (PC) and locally recurrent castration-resistant prostate cancer (CRPC) samples. By analyzing gene expression profiles using RNA-seq data, we aim to identify specific genetic factors and pathways associated with disease progression and treatment resistance in **prostate cancer**.

### Data Sources

- **Data Source**: RNA-seq experiment on prostate cancer patient samples. Available as 'RNA_expressions.RDS' file.
- **Sample Groups**: 13 samples in the PC group and 30 samples in the CRPC group.
  
### Tools

- R - Data cleaning - Data Analysis - Creating reports

### Data cleaning/ Preparation

In the initial phase, we performed the following tasks:
1. Data loading and inspection
2. Data normalization

### Exploratory Data Analysis

EDA involved exploring the transcript data to answer key questions, such as:

- Are the sample groups clustered as the way we expect?
- What are the differential expressed (DE) genes between the two sample groups?
- Any interesting biological information derived from KEGG analysis that can be relevant to 
 the differences between PC and CRPC?

### Data analysis

1. **Filtering and Normalization**: 
   - Low-expression genes were filtered out (those with counts below the 25th percentile).
   - Genes with zero transcript counts across all samples were removed.

2. **Clustering and Outlier Detection**:
   - Hierarchical clustering using **Canberra distance** and **single linkage** methods identified outliers within sample groups.
   - Principal Component Analysis (PCA) confirmed clustering results, showing distinct expression profiles between PC and CRPC groups.

3. **Differential Expression Analysis**:
   - Conducted using DESeq2 and **Student's t-test**.
   - Significance criteria: with obtained **p-value < 0.0001** and **effect size > 1**.
   - Identified 506 genes as significantly differentially expressed.

4. **Pathway Enrichment**:
   - Enriched **KEGG pathways** were analyzed from the list of differentially expressed genes, using a threshold p-value of 0.05 for significance.

### Findings

#### <1> Clustering and PCA Analysis
- **Outliers Identified**: Samples **PC 6864** and **PC 9324** from the PC group clustered separately, aligning more closely with the CRPC group. This suggests potential molecular similarities with CRPC.
- **PCA Visualization**: Differentiated expression levels were visually evident, with **green dots representing CRPC** and **red dots representing PC**, confirming the clustering patterns.

<p align="center">
  <img src="https://github.com/user-attachments/assets/edf84705-4802-4d5a-a8b5-0e326d9f934b" width="500">
</p>

#### <2> Differential Expression and Volcano Plot
- **Differential Expression**:
  - **506 genes** met the significance criteria (p-value < 0.0001 and effect size > 1).
  - The **volcano plot** shown below highlights upregulated and downregulated genes in distinct colors, with significantly expressed genes listed at the top by ascending adjusted p-value.

<p align="center">
  <img src="https://github.com/chinguyen19/Bioinformatics-projects/assets/66997827/09b32518-6940-43a7-aeb5-7c1539f8887e" width="500">
</p>

- **Significant Genes**: 
  - The list of top differentially expressed genes provides insights into key genetic changes between PC and CRPC samples.
  - Genes predominantly **downregulated** in the PC group may indicate reduced expression as a possible mechanism of treatment resistance.

#### <3> Pathway Enrichment Analysis
- Enriched pathways reveal biological processes potentially underlying CRPC progression, including:
  - **Cell Division Regulation**, **Hormone Regulation**, **Stress Response**, **Infection Response**, **Blood Regulation**

<table align="center">
  <tr>
    <th style="text-align:center;">KEGG Pathway ID</th>
    <th style="text-align:center;">Pathway Name</th>
    <th style="text-align:center;">p-value</th>
  </tr>
  <tr>
    <td style="text-align:center;">05146</td>
    <td style="text-align:center;">Amoebiasis</td>
    <td style="text-align:center;">1.13e-4</td>
  </tr>
  <tr>
    <td style="text-align:center;">04512</td>
    <td style="text-align:center;">ECM-receptor interaction</td>
    <td style="text-align:center;">1.58e-4</td>
  </tr>
  <tr>
    <td style="text-align:center;">00140</td>
    <td style="text-align:center;">Steroid hormone biosynthesis</td>
    <td style="text-align:center;">1.63e-4</td>
  </tr>
  <tr>
    <td style="text-align:center;">04110</td>
    <td style="text-align:center;">Cell cycle</td>
    <td style="text-align:center;">2.39e-4</td>
  </tr>
  <tr>
    <td style="text-align:center;">05150</td>
    <td style="text-align:center;">Staphylococcus aureus infection</td>
    <td style="text-align:center;">2.75e-4</td>
  </tr>
  <tr>
    <td style="text-align:center;">04974</td>
    <td style="text-align:center;">Protein digestion and absorption</td>
    <td style="text-align:center;">3.04e-4</td>
  </tr>
</table>
  
      
## Discussion
- Our analyses consistently highlight **PC 6864** and **PC 9324** as **outliers**, aligning these samples more closely with CRPC than the untreated PC group. This suggests the presence of specific **genetic alterations** that could contribute to **treatment resistance** and **molecular similarity** with CRPC.
- The **differential expression and pathway enrichment** results support the hypothesis that particular pathways related to stress, infection, and hormone regulation may play key roles in CRPC development. These findings offer a foundation for further research on therapeutic strategies to address treatment resistance in prostate cancer.


