# MSENet: A Lightweight Network for Portable Fry Counting Devices
The official resources of the paper：
>  [**MSENet: A Lightweight Network for Portable Fry Counting Devices**](https://doi.org/10.1016/j.asoc.2023.110140)  
>  Weiran Li, Qian Zhu, Hanyu Zhang, Ziyu Xu, Zhenbo Li  
>  [**\[Paper\]**](https://doi.org/10.1016/j.asoc.2023.110140) [**\[Code\]**](https://github.com/vranlee/MSENet/)

<img src="assets/Framework.png" width="750"/>

Contact: vranlee@cau.edu.cn. Any questions or discussion are welcome!

-----

## Updates
+ [2021.1.18] We updated the sample official resources of the [**MSENet**](https://github.com/vranlee/MSENet).

-----

## Counting performance

+ Density Map
<img src="assets/Density Map.png" width="750"/>

+ Outputs Images
<img src="assets/Outputs.png" width="750"/>

+ Results on the **NCAUF** Dataset

   Dataset | MAE ↓| MSE ↓|
   --------|------|------|
   NCAUF   | 3.33 | 4.58 |

## Abstract
Estimating the number of fries plays a critical role in the maintenance of fish breeding, transportation, and the preservation of marine resources in aquaculture. Generally speaking, statistics are recorded manually by fishers and government units. Manual recording is time-consuming and increases the workload of fishers. Compared with traditional physical shunt devices, visual-based algorithms have benefits such as non-restriction of labors, minimal equipment installation, and maintenance costs. However, these methods generally come with massive calculations and model parameters, or poor abilities of aggregation handles and counting precision. This paper proposes a fry counting method named MSENet for portable fry counting devices. Firstly, the lightweight network is designed with simpler parameters (Params: 139.46 kB) for portable embedding. The visualized single-channel fry density maps are predicted by feeding the original images and the number of fries is calculated through integration. Then, the Squeeze-and-Excitation block is utilized to strengthen the features of weighty channels. The model training is refined by hyperparameter studies, the shortened preparation stage enhances the portability. What’s more, a fry counting dataset NCAUF and an extra set NCAUF-EX are built for verifications of network generalization. The results demonstrate that the lightweight MSENet outperforms in fry counting with higher precision and competently solves the issue of fry aggregation (MAE: 3.33).

## Contributions
+	A lightweight (Params: 139.46 kB) network MSENet is designed especially for portable devices of fry counting in feeding pond scenarios. The model is implemented based on the density map regression, which efficiently handles the adhesion phenomenon in high-density scenarios.
+	The Squeeze-and-Excitation block is embedded into the network, the precision is further improved (MAE: 3.33) by maintaining the model lightweight.
+	A fry counting dataset NACUF is built and augmented with an extra set NCAUF-EX to verify the generalization of the fry count model.

## Preparation
+ **Step.1** Clone this repo.
+ **Step.2** Install dependencies. We use **python 3.9.7** and **CUDA 11.3**.
   ```
   conda create -n MSENet
   conda activate MSENet
   conda install pytorch torchvision torchaudio cudatoolkit=11.3 -c pytorch
   cd {Repo_ROOT}
   pip install -r requirements.txt
   ```

## Baseline model
Our pretrained **MSENet** model can be downloaded here:   

+  **MSENet_NCAUF_SC.pth: [[Onedrive]](https://1drv.ms/u/s!AiAYwd6-_n-fmmRV_KcCuopz8RzS?e=g12QAe) [[BaiduYun: b910]](https://pan.baidu.com/s/15_PSajF8mk282DmFMNJ7xw)**


## Data Preparation
We provide some samples of our **NCAUF** dataset. The sample datasets can be download from: **[[Onedrive]](https://1drv.ms/u/s!AiAYwd6-_n-fmmPKYTnKDLpui-_Z?e=ruTInN) [[BaiduYun: zlxl]](https://pan.baidu.com/s/1dKWj99BuoNTOP2om5bdFCw)**

 *The **NCAUF_Samples.tar** includes sample images and corresponding annotation files.*

Class  | Sample |  Class  | Sample |  Class  | Sample |
---------|------|---------|--------|---------|--------|
<img src="assets/sparse.png" width="100"/>   | Sparse | <img src="assets/slightly dense.png" width="100"/> | Slightly Dense | <img src="assets/dense.png" width="100"/> | Dense |
 <img src="assets/original.jpg" width="100"/> | Original | <img src="assets/bright.jpg" width="100"/> | Bright+ | <img src="assets/dark.jpg" width="100"/> | Bright- |
 <img src="assets/contrast.jpg" width="100"/> | Contrast+ | <img src="assets/smooth.jpg" width="100"/> | Smoothing | <img src="assets/noise.jpg" width="100"/> | Gaussian Noise |



## Recommended Resources
+ We recommend a third-party counting framework: [gjy3035/C-3-Framework](https://github.com/gjy3035/C-3-Framework).  
Thanks for their wonderful works!
