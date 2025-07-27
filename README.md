# MFLS50
# Abstract
Multibeam forward-looking sonar object tracking is a fundamental task in underwater robotics, with numerous essential applications, such as autonomous underwater docking, inspection of subsea pipelines, and biological investigation, etc. However, progress in this area has been limited compared to other video tracking problems due to the lack of specialized benchmarks. In this paper, we introduce MFS2oT, the first multibeam forward-looking sonar single object tracking benchmark dataset. MFS2oT contains 50 videos and 15,842 frames, and covers 11 scenario attributes. A key feature of MFS2oT is its inclusion of challenging real-world underwater scenarios, such as fake target, tugboat wake, and random rays interfere. We benchmark the performance of 25 state-of-the-art tracking algorithms. Additionally, we introduce a self-correction tracking baseline to improve the performance that leverages temporal context information and a correlation filter based tracker with hybrid regularizers. Extensive qualitative and quantitative results show that our approach achieves superior tracking performance on the proposed benchmark. The proposed MFS2oT will significantly advance research in intelligent sonar object tracking and related applications. The dataset and the evaluation as well as our analysis are available at https://github.com/phan1007/MFLS50.
# Contact
hanpan@sjtu.edu.cn
# Proposed Method
In this paper, an efficient temporal contextual tracker with truncated $\ell_{1}$-$\ell_{2}$ sparsity and aberrances repression regularization (TCL1-L2ARDCF) is developed within the framework. The main idea of the proposed tracker is to utilize the temporal context information of multiple trackers when model drifting by inappropriate model updates. The proposed method is composed of six steps:1) parameters initialization; 2) determine $n$ trackers using different model updating strategies; 3) forward tracking; 4) backward tracking; 5) robustness evaluation; 6) initialization of a group of trackers with the results of the best tracking trajectory, then next track. 
## An example for the update strategies of 4 trackers in the interval is:
![image](https://github.com/phan1007/MFLS50/blob/main/figs/update_strategies.png)
## Comparison of forward-backward tracking trajectory results for different trackers on the same sequence.
![image](https://github.com/phan1007/MFLS50/blob/main/figs/fbttr.png)
# MFS2oT Dataset
Two multibeam forward-looking sonars are used in our experiments, i.e., Blueview M900-130 and Blueprint M750d. The acoustic specifications of these two sonars are provided as follows
| Acoustic Specifications  | Blueview M900-130 | Blueprint M750d |
| ------------- | ------------- |------------- |
|  Operating frequency | 750kHz  | 900kHz |
|  Angular resolution | $1^{o}$ | $0.18^{o}$ |
|  Range | 0.1m-120m | 2.0m-100m |
|  Number of beams | 512 | 768 |
|  Horizontal beamwidth | $130^{o}$ | $130^{o}$ |
|  Vertical beamwidth | $20^{o}$ | $20^{o}$ |
|  Range resolution | 4mm | 1.4cm |
|  Update rate | 40Hz | 25Hz |
## Schematic diagram and data collection scenarios for autonomous underwater dynamic docking experiment
It can be seen that the captured sonar image contains complex clutters.
![image](https://github.com/phan1007/MFLS50/blob/main/figs/Scenarios.png)

## Mechanical structure for data collection
![image](https://github.com/phan1007/MFLS50/blob/main/figs/FM.png)

## The UUV during the experiments
![image](https://github.com/phan1007/MFLS50/blob/main/figs/UUV-exp.png)

The experiments have 6 objects including UUV, aluminium metal box, grey box, plane model, red bucket, and submarine model. The parameters of the UUV is presented as follows
| Parameters  | Specific values |
| ------------- | ------------- |
|  Size | Diameter: 324mm, Length: 3300mm  |
|  Weight | 450m |
|  Depth | 0.1m-120m |
|  Endurance | >60Km |
|  Speed | 0-6Knots |

## 5 objects recorded by the visible camera
![image](https://github.com/phan1007/MFLS50/blob/main/figs/optical_img.png)

# Experiments and Results
## 25 trackers are benchmarked. Precision and success plots for OPE
![image](https://github.com/phan1007/MFLS50/blob/main/figs/OPE.png)

## Qualitative results of five trackers (ARCF, The proposed method, STRCF, CSRDCF, and TADT) on MFLS image sequences
![image](https://github.com/phan1007/MFLS50/blob/main/figs/results.png)

## Top 10 tracker results for the challenge attributes of Tugboat Wake (TW), Random Rays(RRI) and Fake Targets(FT)
![image](https://github.com/phan1007/MFLS50/blob/main/figs/TW-RRI-FT.png)

## Top 10 tracker results for the challenge attributes of Low Resolution(LR) and Ambiguous Target(AT)
![image](https://github.com/phan1007/MFLS50/blob/main/figs/LR-AT.png)

## Precision and success plots for TRE and SRE
![image](https://github.com/phan1007/MFLS50/blob/main/figs/TRE-SRE.png)
# References
Xueqiong Sui, Han Pan, Zhongliang Jing and Henry Leung, "Multibeam Forward-Looking Sonar Video Object Tracking Using Truncated L1-L2 Sparsity and Aberrances Repression Regularization," in IEEE Robotics and Automation Letters, vol. 9, no. 2, pp. 1122-1129, Feb. 2024, doi: 10.1109/LRA.2023.3342669.
# Acknowledgements
This work is jointly supported by National Natural Science Foundation of China (Grant Nos. 61603249, 61673262), the Wuhan Second Ship Design and Research Institute, National GF Basic Research Program under JCKY2021110B134, and the Fundamental Research Funds for the Central Universities. The authors especially thank Yongsheng Li, Meng Xu, Yu Yuan, Yang Liu, Buer Song, Shuangjie Fu, Kaiyao Ling, Zhouchu Zhang, Lijie Xie, Chunfang Pan, Pei Pan, Jie Pan, Jihe Pan, Hong Chen, Hao Zhang, Mo Tao, Shaobo Fu, Zesong Ma, Kun Wei, Xianbo Xiang, Shaolong Yang, Zhao Wang, Xinyang Xiong, and Chuan Liu for helping them to complete the field experiments.

