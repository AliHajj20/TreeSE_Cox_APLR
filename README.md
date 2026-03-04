# TreeSummarizedExperiment_Coxmodel
The aim of this project is to implement a Cox proportional hazards regression model on a microbiome survival study stored in a TreeSummarizedExperiment object. The microbial abundance table is transformed using the all-pairs log-ratio (APLR) transformation.

1. Install Required Packages
To facilitate reproducibility, this project relies on a Docker image that includes many of the required dependencies. Instructions for installing and running the Docker image can be found here:
https://microbiome.github.io/OMA/docs/devel/pages/session_info.html#sec-docker-image

Additionally, users should install any remaining R packages listed at the beginning of the script if they are not already installed.

2. The data on which the analysis is performed can be found in this repository "biom.Rdata".

--
Project Context 
Master’s Thesis Research 
Master’s Program: Molecular Biology and Genetics 
University: University of Pavia 
Location: Turku Data Science Group, Turku, Finland
--
Data Description
Data Type: Survival data from a microbiome study
Source: Public dataset
Data File: biom.Rdata (included in this repository)
Data Structure: TreeSummarizedExperiment object
No additional data preprocessing is required beyond what is implemented in the analysis scripts.
--
Methods:
Statistical Model: Cox Proportional Hazards Model
Evaluation Metric: Harrell's Concordance Index (C-index)
--
##Analysis Goal

This project builds on and extends the supplementary analysis from the article
“Microbiome compositional data analysis for survival studies”
([paper]([url](https://pmc.ncbi.nlm.nih.gov/articles/PMC11044448/)) | [original code]([url](https://zenodo.org/records/10554488)))

After independently reproducing the supplementary analysis, the goal of this project was to evaluate how specific methodological choices influence Cox proportional hazards model performance in microbiome survival studies.
###Specifically, this project investigates:
1- The impact of the data structure used to store microbiome data
2- The effect of introducing a train–test split, where models are trained on a training subset and evaluated on an unseen testing subset

###Key differences from the original study
####Data structure
1- Original study: phyloseq
2- This project: TreeSummarizedExperiment
####Model evaluation strategy
1- Original study: No explicit training/testing split
2- This project: Explicit train–test split to assess generalization performance
Model performance is evaluated using the concordance index (C-index) to assess whether these methodological differences affect predictive performance.
--
performance assessed using the C-index.
The results obtained represent:
i) signature plot that represents the selected taxa with their respective coefficient:

ii) risk score plot that represents the risk score of each taxa:

iii) Kaplan–Meier survival can be generated separately using the plot_survival() function, Kaplan–Meier survival curve illustrating the probability of survival among participants, stratified by their microbial risk score. Participants are divided into two groups: those with a high microbial risk score (red) and those with a low microbial risk score (blue). The x-axis represents time, while the y-axis shows the survival probability. 
