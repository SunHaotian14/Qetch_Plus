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

- Jupyter Notebook for Data Preprocessing: [Preprocessing.ipynb]([Crowd-Study Data/Preprocessing.ipynb](https://github.com/SunHaotian14/Qetch_Plus/blob/cce5dd328c211e800927707fd1600ee6984fe1d1/Crowd-Study%20Data/Preprocessing.ipynb))
- Jupyter Notebook for Evaluations: [Experiment.ipynb](https://github.com/SunHaotian14/Qetch_Plus/blob/cce5dd328c211e800927707fd1600ee6984fe1d1/Crowd-Study%20Data/Experiment.ipynb)

## Repository content

This repository contains:

- Qetch's source code, contained in the folder `Server`

- The two jupyter notebooks containing our code are located in the folder `Crowd-Study Data`

- The collected queries from our crowd study are in the folder `Crowd-Study Data`

## Brief Discussion

Despite being an old measure, the ED-based method shows a strong proficiency in most performance tests, i.e., good accuracy and precision, short execution time, and low sensitivity to frequency and noise. Therefore, we still recommend adopting the ED-based method in most practical tasks. 

The MD-based approach can be regarded as a satisfactory substitute for the ED-based methods in some scenarios where ED distance is hard to calculate (e.g., when using embedding systems for time series with substantial differences, the square operation in ED may result in overflows.) 

On the other hand, DTW yields the most accurate and precise results, costing higher running time and raising sensitivities. It is supposed to be the best choice when accuracy and precision are relatively essential and when the frequency/noise disturbances can be eliminated (e.g., in some scientific computing scenarios). 

The GAK method improves accuracy while remaining immune to frequency and noise disturbances. Its computational cost, however, is the highest among the examined approaches. Therefore, GAK will be the most appropriate choice in some offline, accuracy-demanding scenarios where disturbances are often present. 

The Qetch algorithm shows a decent performance in the accuracy and precision tests, whereas it is also susceptible to frequency and noise. The most advantageous feature of the Qetch algorithm is that it does not harness the pointwise sliding window, which should make it suitable in cases where the sliding window is costly (e.g., matching short sketches with very long time series). 

The Soft-DTW and the LCSS methods generate poor performance in almost all test metrics, possibly because these two methods are not purposely designed for query-by-sketch tasks. Therefore, we do not recommend using these two methods in similar tasks.

Furthermore, we revisit the following discussion and summarize several possible scenarios and the corresponding similarity measures we suggest.

- In most scenarios without requirement in some specific metrics, the ED-based method should be the first choice, thanks to its balanced and good performance in all metrics;
- In the scenarios when the square operation is costly, the MD distance is worth adopting;
- In some noise-free circumstances with an emphasis on accuracy and precision, DTW is supposed to be the best candidate;
- In some circumstances, also with an emphasis on accuracy and precision, but in the presence of noise and frequency disturbance, one can trade the running time for accuracy by using the GAK-based approach;
- In the cases where the pointwise sliding window is computationally costly, the Qetch algorithm can be adopted.

## References
[1] Boualem Boashash (Ed.). 2016. Time-Frequency Signal Analysis and Processing (Second Edition) (second edition ed.). Academic Press, Oxford. iv pages. https://doi.org/10.1016/B978-0-12-398499-9.09987-8

[2] Carmelo Cassisi, Placido Montalto, Marco Aliotta, Andrea Cannata, and Alfredo Pulvirenti. 2012. Similarity Measures and Dimensionality Reduction Techniques for Time Series Data Mining. In Advances in Data Mining Knowledge Discovery and Applications, Adem Karahoca (Ed.). IntechOpen, Rijeka, Chapter 3. https://doi.org/10.5772/49941

[3] Yanping Chen, Eamonn Keogh, Bing Hu, Nurjahan Begum, Anthony Bagnall, Abdullah Mueen, and Gustavo Batista. 2015. The UCR Time Series Classification Archive. www.cs.ucr.edu/~eamonn/time_series_data/.

[4] Marco Cuturi. 2011. Fast Global Alignment Kernels. Proceedings of the 28th International Conference on Machine Learning, ICML 2011, 929–936.

[5] Marco Cuturi and Mathieu Blondel. 2017. Soft-DTW: a Differentiable Loss Function for Time-Series. In Proceedings of the 34th International Conference on Machine Learning (Proceedings of Machine Learning Research), Doina Precup and Yee Whye Teh (Eds.), Vol. 70. PMLR, 894–903. https://proceedings.mlr.press/v70/cuturi17a.html

[6] Chaoran Fan, Kresimir Matković, and Helwig Hauser. 2020. Sketch-based fast and accurate querying of time series using parameter-sharing LSTM networks. IEEE Transactions on Visualization and Computer Graphics 27, 12 (2020), 4495–4506.

[7] Ian Goodfellow, Yoshua Bengio, and Aaron Courville. 2016. Deep learning. MIT press.

[8] David Maier. 1978. The Complexity of Some Problems on Subsequences and Supersequences. J. ACM 25, 2 (apr 1978), 322–336. https://doi.org/10.1145/
322063.322075 

[9] Miro Mannino and Azza Abouzied. 2018. Expressive Time Series Querying with Hand-Drawn Scale-Free Sketches. In Proceedings of the 2018 CHI
Conference on Human Factors in Computing Systems (Montreal QC, Canada)(CHI ’18). Association for Computing Machinery, New York, NY, USA, 1–13. https://doi.org/10.1145/3173574.3173962

[10] K.K. Paliwal, Anant Agarwal, and Sarvajit S. Sinha. 1982. A modification over Sakoe and Chiba’s dynamic time warping algorithm for isolated word recognition. Signal Processing 4, 4 (1982), 329–333. https://doi.org/10.1016/0165-1684(82) 90009-3

[11] AP Ruiz, M Flynn, J Large, M Middlehurst, and A Bagnall. 2021. The great multivariate time series classification bake off: a review and experimental evaluation of recent algorithmic advances. Data Min Knowl Discov 35, 2 (2021), 401–449.

[12] Mallat Stéphane. 2009. CHAPTER 6 - Wavelet Zoom. In A Wavelet Tour of Signal Processing (Third Edition) (third edition ed.), Mallat Stéphane (Ed.). Academic Press, Boston, 205–261. https://doi.org/10.1016/B978-0-12-374370-1.00010-0

[13] Romain Tavenard, Johann Faouzi, Gilles Vandewiele, Felix Divo, Guillaume Androz, Chester Holtz, Marie Payne, Roman Yurchak, Marc Rußwurm, Kushal
Kolar, and Eli Woods. 2020. Tslearn, A Machine Learning Toolkit for Time Series Data. Journal of Machine Learning Research 21, 118 (2020), 1–6. http:
//jmlr.org/papers/v21/20-091.html

[14] Ricardo Emanuel Vaz Vargas, Celso José Munaro, Patrick Marques Ciarelli, André Gonçalves Medeiros, Bruno Guberfain do Amaral, Daniel Centurion Barrionuevo, Jean Carlos Dias de Araújo, Jorge Lins Ribeiro, and Lucas Pierezan Magalhães. 2019. A realistic and public dataset with rare undesirable real events in oil wells. Journal of Petroleum Science and Engineering 181 (2019), 106223. https://doi.org/10.1016/j.petrol.2019.106223

[15] Shujia Yang, Yi Wang, and Jun Zhang. 2020. A similarity measure for time series based on symbolic aggregate approximation and trend feature. In 2020
39th Chinese Control Conference (CCC). 6386–6390. https://doi.org/10.23919/CCC50068.2020.9189060

[16] Yufeng Yu, Yuelong Zhu, Dingsheng Wan, Qun Zhao, and Huan Liu. 2019. A Novel Trend Symbolic Aggregate Approximation for Time Series. https://doi.org/10.48550/ARXIV.1905.00421

[17] Yunsheng Zhang, Qingzhang Shi, Jiawei Zhu, Jian Peng, and Haifeng Li. 2021.Time Series Clustering with Topological and Geometric Mixed Distance. Mathematics 9, 9 (May 2021), 1046. https://doi.org/10.3390/math9091046

