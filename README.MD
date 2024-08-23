# Abstract
Multibeam forward-looking sonar (MFLS) has facilitated a wide range of real-word applications and attracted more and more attention in the field of underwater robotics. However, existing methods have merely focused and ignored trackers' capabilities to be deployed in multi-beam forward-looking sonar. In this paper, we first propose a new MFLS single object tracking (MFLS2oT) dataset with 50 videos and 15,842 frames under unconstrained conditions. These MFLS videos were recorded from real underwater missions and pose significant new challenges, such as fake target, ambiguous target, tugboat wake, and random rays, to the existing video tracking algorithms. Thus, 11 scenario attributes are defined for short-term tracking evaluation on MFLS. To deal with the new challenge attributes, we designed a novel correlation filter-based tracker with the combination of temporal context, truncated $\ell_{1}$-$\ell_{2}$ sparsity and aberrances repression, named TCL1-L2ARDCF. Furthermore, we benchmark the performance of 25 state-of-the-art single object tracking algorithms. Extensive qualitative and quantitative results show that our TCL1-L2ARDCF achieves superior tracking performance on the proposed benchmark. The findings of the experiments provide some guidelines for future research. Dataset and the evaluation results are available at https://github.com/phan1007/MFLS50.
# Proposed Method
In this paper, an efficient temporal contextual tracker with truncated $\ell_{1}$-$\ell_{2}$ sparsity and aberrances repression regularization (TCL1-L2ARDCF) is developed within the framework. The main idea of the proposed tracker is to utilize the temporal context information of multiple trackers when model drifting by inappropriate model updates. The proposed method is composed of six steps:1) parameters initialization; 2) determine $n$ trackers using different model updating strategies; 3) forward tracking; 4) backward tracking; 5) robustness evaluation; 6) initialization of a group of trackers with the results of the best tracking trajectory, then next track. 

An example for the update strategies of 4 trackers in the interval is:
![image](https://github.com/phan1007/MFLS2oT/blob/main/figs/update_strategies.png)

Comparison of forward-backward tracking trajectory results for different trackers on the same sequence.
![image](https://github.com/phan1007/MFLS2oT/blob/main/figs/fbttr.png)
# MFLS2oT Dataset
Two multibeam forward-looking sonars are used in our experiments, i.e., Blueview M900-130 and Blueprint M750d. The acoustic specifications of these two sonars are provided as follows
| Acoustic Specifications  | Blueview M900-130 | Blueprint M750d |
| ------------- | ------------- |------------- |
| Content Cell  | Content Cell  |------------- |
| Content Cell  | Content Cell  |------------- |










