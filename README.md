# Review and Evaluation of Similarity Measures for Query-by-sketch Pattern Matching in Time Series
CS8803-MDS Project

## Project Description

Query-by-sketching in time series is essential in many application scenarios. The most general approaches for this pattern-matching task usually define a specific time series distance measure and obtain the matching prediction based on that. Considerable distance measurement methods exist, making it challenging for practitioners to decide the most appropriate methods to utilize in practice. To address such issues, we propose concrete experimental evaluations in which the most commonly used matching approaches are examined under different scenarios. Several performance metrics, such as accuracy, precision, running time, and noise sensitivity, are depicted and further analyzed thoroughly. Finally, we summarize the best choices of the pattern-matching algorithms in different scenarios based on these experimental results.


### Similarity Measures:

- Euclidean Distance(ED)
- Manhattan Distance(MD)
- Dynamic Time Warping(DTW) Distance
- Soft-DTW Distance
- Longest Common Subsequence(LCSS) 
- Global Alignment Kernel(GAK)
- Qetch Distance

### Performqnce Metrics:

- Accuracy and Running Time 
- Precision @ k
- Sensitivity to Frequency Components
- Sensitivity to Noise

## Code Locations

- Jupyter Notebook for Data Preprocessing: [Qetch_Plus/Crowd-Study Data/Preprocessing.ipynb](Qetch_Plus/Crowd-Study Data/Preprocessing.ipynb)
- Jupyter Notebook for Evaluations: [Qetch_Plus/Crowd-Study Data/Experiment.ipynb](Qetch_Plus/Crowd-Study Data/Experiment.ipynb)


## Repository content

This repository contains:

- Qetch's source code, contained in the folder `Server`

- The datasets we used to compute our user studies, and our performance evaluations are contained in the folder `Datasets`

- The collected queries from our crowd study are in the folder `Crowd-Study Data`
