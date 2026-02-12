Tumor Clonality deconvolution

The RNotebook html file with codes and outputs can be accessed here https://parulkuls26.github.io/Tumor-clonality-deconvolution/tumor-clonality-deconvolution.html


Overview
This project investigates tumour clonality using variant allele frequency (VAF)–based clustering of somatic SNVs from the LU-4 tumour sample. Because only SNV data were provided (without copy number segmentation, B-allele frequency, tumour purity, or ploidy information), tumour evolution was inferred using:
Raw VAF values
Gaussian finite mixture modelling (mClust)
Dimension reduction clustering and classification
The objective was to identify clonal and subclonal populations and reconstruct tumour evolutionary structure in both single-sample and paired metastasis analyses.

Part 1 — Single Sample Analysis (LU-4)
Data :LU-4.snv.txt, This dataset contains somatic SNVs and corresponding raw VAF values. No copy number or tumour purity information was available.

VAF Distribution
A histogram of all VAF values revealed a multimodal distribution:
Low-VAF peak (~0.05–0.1)
Broader peak (~0.20–0.30)
Right-hand tail extending to ~0.6
Interpretation
The multimodal distribution indicates the presence of multiple mutation populations rather than a single dominant clonal peak. Because tumour purity and copy number data are unavailable, tumour purity cannot be directly inferred from the raw histogram. Therefore, model-based clustering (mClust) was used to separate mutation populations.

mClust Results (Single Sample)
Gaussian finite mixture modelling identified 4 clusters (G = 4).
Cluster Summary
Cluster	Mean VAF	Size (n)	CCF	Interpretation
3	0.249	2823	1.00	Clonal (heterozygous)
4	0.507	165	1.00	Clonal (homozygous/LOH-like)
2	0.093	600	0.37	Subclonal
1	0.056	619	0.23	Subclonal

CCF Estimation
Cancer cell fraction (CCF) was calculated as:
CCF = Mean VAF_cluster / Mean VAF_dominant_clonal_cluster
Cluster 3 (mean VAF ≈ 0.249) was assumed to represent the dominant heterozygous clonal population.
Under a diploid heterozygous assumption:
Tumour purity ≈ 2 × 0.249 ≈ 0.50
Cluster 4 (mean VAF ≈ 0.507) is approximately double the heterozygous peak and is therefore consistent with:
Homozygous mutation
Loss of heterozygosity (LOH)
Allele-specific amplification

Biological Interpretation
Clusters 3 and 4 represent truncal (founding) mutations
Clusters 1 and 2 represent subclonal expansions
The decreasing CCF values suggest sequential subclonal evolution
This supports a model of intratumour heterogeneity with one dominant clone and multiple minor subclones.

Part 2 — Paired LN1–LN2 Analysis
Shared Mutations
A total of 112 shared mutations were identified between LN1 and LN2 metastases.
Mean VAF:
LN1: 29.5%
LN2: 22.9%
Median VAF:
LN1: 32.9%
LN2: 27.1%
Correlation: r = 0.78
This strong positive correlation indicates shared trunk mutations with differential clonal expansion between metastases.

mClust Results (Paired Analysis)
Four clusters (G = 4) were identified:
Cluster	LN1 Mean VAF (%)	LN2 Mean VAF (%)	Size	Interpretation
1	40.4	30.2	44	Clonal heterozygous (shared trunk)
2	23.2	25.1	37	Shared subclone
3	8.4	0.16	24	LN1-enriched subclone
4	80.9	45.9	7	Clonal homozygous/LOH-like

Evolutionary Structure
Trunk (Shared Clonal Events)
Cluster 1 (heterozygous clonal)
Cluster 4 (homozygous/LOH-like)
Branch Evolution
Cluster 2: shared but expanded differently between LN1 and LN2
Cluster 3: LN1-specific minor subclone
This pattern suggests:
A common ancestral tumour clone
Divergent evolution in LN1 and LN2
Additional subclonal expansion in LN1

Key Takeaways
LU-4 shows clear intratumour heterogeneity
mClust effectively separates clonal and subclonal populations
Paired metastasis analysis reveals trunk mutations and branch-specific evolution
Absence of copy number data limits precise purity-adjusted inference
Evolution follows a trunk–branch model consistent with metastatic divergence

Methods
R
mclust package (Gaussian finite mixture modelling)
VAF-based clustering
CCF approximation using dominant clonal peak

Limitations
No copy number segmentation
No tumour purity estimate
Raw VAF used for CCF calculation
No functional annotation of SNVs

Author
Dr. Parul Kulshreshtha
