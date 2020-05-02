# L-CO-Net (Learned-Condensation-Optimizaton Network)

Condensely connected architecture for Cardiac Cine MR Image Segmentation and Quantification

This repository contains code to train state-of-the-art cardiac segmentation networks as described in this paper: CondenseUNet: A Memory-Efficient Condensely-Connected Architecture for Bi-ventricular Blood Pool and Myocardium
Segmentation. This architecture is trained on [MICCAI 2017 ACDC Cardiac segmentation challenge.](https://www.creatis.insa-lyon.fr/Challenge/acdc/index.html)

In this work, we implement a fully convolutional segmenter featuring both a learned group structure and a regularized weight pruner to reduce the high computational cost in volumetric image segmentation. We validated our framework on the ACDC dataset featuring one healthy and four pathology groups imaged throughout the cardiac cycle. Our technique achieved Dice scores of 96.80% (LV blood-pool), 93.33% (RV blood-pool) and 90.0% (LV Myocardium) with five-fold cross-validation and yielded similar clinical parameters as those estimated from the groundtruth segmentation data. Based on these results, this technique has the potential to become an efficient and competitive cardiac image segmentation tool that may be used for cardiac computer-aided diagnosis, planning and guidance applications.


# Prerequisites
Our code is compatible with python 3.7 or onward.

We depend on some python packages which need to be installed by the user:

* Tensorflow
* tqdm
* SimpleITK
* sklearn
* numpy
* nibabel
* h5py

# Authors 
* S. M. Kamrul Hasan ([sh3190@rit.edu])()
* Cristian A. Linte

# Contents 

* [Data]()
* [Method]()
* [Results]()
* [How to Run]()



# [Data]()

For this study, we used the ACDC dataset, which is composed of short-axis cardiac cine-MR images acquired from 100 different patients divided into 5 evenly distributed subgroups according to their cardiac condition: normal- NOR, myocardial infarction- MINF, dilated cardiomyopathy- DCM, hypertrophic cardiomyopathyHCM, and abnormal right ventricle- ARV, available as a part of the STACOM 2017 ACDC challenge.

# [Method]()

We evaluate CondenseUNet architectures for segmentation as well as clinical parameter estimation. The output of the model is a pixel-by-pixel mask that shows the class of each pixel.

Our proposed L-CO-Net framework substitutes the concept of both standard convolution and group convolution (G-Conv) with learned group-convolution (LGConv). While the standard convolution needs an increased level of computation, i.e. O(Ii x Oo), and concurrently, the pre-defined use of filters in each group convolution restricts its representation capability, these aforementioned problems are mitigated by introducing LG-Conv that learns group convolution dynamically during training through a multi-stage scheme.

![RESULT2](https://user-images.githubusercontent.com/42282006/80854258-907b9f00-8c04-11ea-83d9-74f6011667d3.png)

# [Results]()

Figure shows segmentation results and the ground truth masks for both 2D and 3D cases. It summarizes the comparison results, which show that our proposed model significantly improved the segmentation performance against several state-of-the-art multi-class segmentation techniques in terms of Dice metrics, Hausdorff distance, and clinical parameters. Our proposed L-CO-Net architecture achieved Dice score (Hausdorff distance) of 96.8%(7.9mm) and 95.1%(6.4mm) for the LV bloodpool, 89.5%(8.9mm) and 90.0%(8.9mm) for the LVMyocardium and 93.3%(11.2mm) and 87.43%(11.9mm) for the RV blood-pool in end-diastole and end-systole, respectively.

![PLOT2](https://user-images.githubusercontent.com/42282006/80854260-940f2600-8c04-11ea-8040-a8fad6f1660d.png)

# [Table]()

Quantitative evaluation of the segmentation results in terms of Mean Dice score (%) with Hausdorff distance(in mm),
no. of parameters (×106 ), and the clinical indices evaluated on the ACDC dataset for LV, RV blood-pool and LV-myocardium compared across several best performing networks, including L-CONet. The statistical significance of the results for L-CO-Net model compared against five other base architectures.

<img width="674" alt="Screen Shot 2020-05-01 at 11 04 22 PM" src="https://user-images.githubusercontent.com/42282006/80853609-206b1a00-8c00-11ea-8d3b-77fc5a7ee8d4.png">


![healthy_rr](https://user-images.githubusercontent.com/42282006/80854262-95405300-8c04-11ea-9c4b-ff70ebb5b757.png)
![abnormal_rr](https://user-images.githubusercontent.com/42282006/80854264-96718000-8c04-11ea-98cf-19525c5eabf8.png)

# [How to Run]()

# [Preprocessing]()

# [Train]()




If you find this work useful for your publications, please consider citing:

> Hasan, SM Kamrul, and Cristian A. Linte. "CondenseUNet: a memory-efficient condensely-connected architecture for bi-ventricular blood pool and myocardium segmentation." Medical Imaging 2020: Image-Guided Procedures, Robotic Interventions, and Modeling. Vol. 11315. International Society for Optics and Photonics, 2020.'

> Kamrul Hasan, S. M., and Cristian A. Linte. "CondenseUNet: A Memory-Efficient Condensely-Connected Architecture for Bi-ventricular Blood Pool and Myocardium Segmentation." arXiv (2020): arXiv-2004.




