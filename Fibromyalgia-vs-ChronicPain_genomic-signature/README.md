# Genomic Signature in Fibromyalgia 

## Project Overview
Fibromyalgia is a complex chronic pain disorder often misdiagnosed due to symptom overlap with conditions like arthritis and chronic fatigue syndrome. Without objective diagnostic markers, current assessments rely on clinical evaluation, leading to inconsistent diagnoses and treatments. This project seeks to identify a genomic signature unique to fibromyalgia, aiming to improve diagnostic accuracy and guide the development of more effective, personalized therapies.

## Main Objectives

- Identify genomic markers unique to fibromyalgia: to differentiate fibromyalgia from other chronic pain disorders, to enhance diagnostic accuracy.
- Develop biological pathways for potentialy novel targeted therapeutic strategies, including non-opioid options.
- Improve clinical outcomes by reducing misdiagnoses and optimizing treatment approaches

## Dataset

- **Data Source**: NCBI Gene Expression Omnibus (GSE221921)
- **Data Content**: FPKM (Fragments Per Kilobase of transcript per Million mapped reads) values generated from RNA sequencing, including data from 96 fibromyalgia patients and 93 control cases.

## Findings and Insights  
With the volcan plot representing of the proportion of upregulated and downregulated genes based on their gene expression values:<br>
![Figure 1: Gene Regulation Analysis with Volcano plot](https://github.com/chinguyen19/Data-Science-Bioinformatics-projects/blob/main/Fibromyalgia-vs-ChronicPain_genomic-signature/volcano.png) <br>
- **Is fibromyalgia characterized by widespread gene regulation changes?**  
  Yes, the presence of numerous red dots suggests broad and subtle changes in gene regulation, reflecting the complex nature of fibromyalgia’s genomic signature.  

- **Are there key genes central to fibromyalgia biology?**  
  The number of green dots highlights a smaller set of genes with strong, consistent changes, potentially identifying key regulatory elements central to disease mechanisms. 2671 genes were identified as upregulated, while only 120 genes were downregulated in fibromyalgia compared to control.
 <br>   
 <br>
 
With the heatmap of the top 50 genes from differential expression analysis:<br>

![Figure 2: Sample Clustering with Heatmap](https://github.com/chinguyen19/Data-Science-Bioinformatics-projects/blob/main/Fibromyalgia-vs-ChronicPain_genomic-signature/heatmap_30DEGs_manhattan.png) <br>
- **Can genomic expression distinguish fibromyalgia patients from controls?**  
  The distinct clustering of FM and control samples supports the idea that fibromyalgia has a unique genomic expression pattern.  

- **Why do some controls cluster with FM samples?**  
  This may indicate potential pre-symptomatic states, shared gene expression profiles, or variability introduced by noise in the data, warranting further investigation into these outliers.  
 <br>   
 <br>
 
Summary of some highlighted pathways enriched for fibromyalgia:<br>

![Figure 3: Some key enriched pathways in Fibromyalgia](https://github.com/chinguyen19/Data-Science-Bioinformatics-projects/blob/main/Fibromyalgia-vs-ChronicPain_genomic-signature/key_enrichedPathways.png)  <br>
- **What are the genomic signatures through enriched biological pathways in Fibromyalgia?**
 Several enriched pathways, including those involved in energy metabolism, protein synthesis, stress responses, and neuroinflammation, provides valuable insights into the underlying mechanisms of FM, specifically related to fatigue, pain, and cognitive dysfunction.

## Methods
- **Differential expression analysis**
  - Limma package in R was used on given FPKM-normalized counts
  - Voom was apllied to improve the limitation of Limma's assumption
- **Pathways analysis**
  - Gene IDs were mappped to KEGG pathways using Entrez gene indentifiers
  - Fisher's exact test was applied to identify pathways with a statiscally significantu6hb 56  

