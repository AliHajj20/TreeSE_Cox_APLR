# TreeSummarizedExperiment_Coxmodel
This repository implements a Cox proportional hazards regression model on a microbiome survival study stored in a TreeSummarizedExperiment object. The microbial abundance table is transformed using the all-pairs log-ratio (APLR) transformation

1. Install Required Packages
To facilitate reproducibility, this project relies on a Docker image that includes many of the required dependencies. Instructions for installing and running the Docker image can be found here:
https://microbiome.github.io/OMA/docs/devel/pages/session_info.html#sec-docker-image

Additionally, users should install any remaining R packages listed at the beginning of the script if they are not already installed.

2. The data on which the analysis is performed can be found in this repository "biom.Rdata".

--

The results obtained represent:
i) signature plot that represents the selected taxa with their respective coefficient:

ii) risk score plot that represents the risk score of each taxa:

iii) Kaplan–Meier survival can be generated separately using the plot_survival() function, Kaplan–Meier survival curve illustrating the probability of survival among participants, stratified by their microbial risk score. Participants are divided into two groups: those with a high microbial risk score (red) and those with a low microbial risk score (blue). The x-axis represents time, while the y-axis shows the survival probability. 
