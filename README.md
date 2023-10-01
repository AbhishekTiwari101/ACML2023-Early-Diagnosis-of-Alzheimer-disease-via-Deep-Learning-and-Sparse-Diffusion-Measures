# ACML2023-Early-Diagnosis-of-Alzheimer-disease-via-Deep-Learning
Early Diagnosis of Alzheimer through Swin-Transformer-Based Deep Learning Framework Using Sparse Diffusion Measures

Alzheimer disease is one of the most common neuro-degenerative diseases, with an estimated 6.2 million cases in the United States. This research article investigates the potential of Transformer-based deep learning techniques to accelerate the processing of diffusion tensor imaging (DTI) measures and improve the early diagnosis of Alzheimer disease (AD) using sparse data. Diffusion Weighted Imaging (DWI) is a time-consuming process, with each diffusion direction taking between 2-5 minutes, and at least 40 diffusion directions are needed for routine clinical diagnosis, which needs scanning duration exceeding 3 hours for each patient. By leveraging the attention mechanism, our proposed model generates quantitative measures of fractional anisotropy (FA), axial diffusivity (AxD), and mean diffusivity (MD) using 5 and 21 diffusion directions, making it useful for clinical diagnosis through reduced scanning time of more than half. Our experimental results on the Alzheimer's Disease Neuroimaging Initiative (ADNI) dataset demonstrate that our proposed model outperforms the traditional linear least square method, achieving accurate quantitative measurement of FA, AxD, and MD scores for early diagnosis of AD patients from healthy controls using sparse diffusion directions. Our analysis highlights the potential of Swin-Transformer attention-based deep learning framework to improve the early diagnosis and treatment of Alzheimer's disease.

**Data used in preparation of this article were obtained from the Alzheimer’s Disease
Neuroimaging Initiative (ADNI) database (\url{adni.loni.usc.edu}). As such, the investigators
within the ADNI contributed to the design and implementation of ADNI and/or provided data
but did not participate in analysis or writing of this report. A complete listing of ADNI
investigators can be found at:\href{http://adni.loni.usc.edu/wp-content/uploads/how_to_apply/ADNI_Acknowledgement_List.pdf}{ADNI Acknowledgement List}

**The main contributions of this research are:**
The proposed model efficiently learns spatial correlation in neighboring voxels, thereby improving the robustness of diffusion tensor imaging parameters.
The proposed method speeds up the estimation of DTI parameters using sparse measurements.
The proposed model exhibits the capability to quantitative diffusion parameters and identify early-stage Alzheimer's disease.

Getting Started: DTI Data Preprocessing Workflow
The following steps outline the data preprocessing workflow for DTI (Diffusion Tensor Imaging):

Step 1: DTI Model Fit
Apply the DTI model fit from the DIPY Python package Garyfallidis et al., 2014 to process each DWI (Diffusion-Weighted Imaging) image individually. This results in the computation of six diffusion components: Dxx, Dxy, Dyy, Dxz, Dyz, and Dzz of the diffusion tensor.

Step 2: Voxel Selection
Select 100,000 voxels from each DWI image based on their fractional anisotropy (FA) score. Voxels with an FA score of zero are excluded, and the selection is uniformly distributed within the range (0, 1).

Step 3: Dataset Generation
Generate 100,000 tuples of (input, ground-truth), where each tuple comprises:

An input 5 × 5 × 5 voxel patch with 41 diffusion directions per voxel.
A ground-truth 5 × 5 × 5 voxel patch with a 6 × 1 vector per voxel, representing the corresponding six diffusion components of the diffusion tensor.
Step 4: Signal Concatenation
Concatenate the diffusion signals of the neighboring 5 × 5 × 5 patches to construct a 125 × 41 matrix for each input voxel.

Step 5: Direction and Signal Concatenation
Combine the diffusion directions (3 × 41) with the diffusion signals to create a 128 × 41 matrix for each input voxel.

Step 6: Zero-padding
Zero-pad the input data for each tuple to form a 128 × 100 matrix. The corresponding ground truth is represented as a 125 × 6 matrix. This processed dataset is denoted as "ADNI − 41."

Step 7: Qball-based Interpolation
Perform Qball-based interpolation Tuch, 2004; Garyfallidis et al., 2014 on the 41-directional input data from the "ADNI − 41" dataset. This step yields 41-directional, 21-directional, and 5-directional diffusion signals, utilizing the DIPY package.

Step 8: Direction and Signal Concatenation (Interpolated Data)
Combine the diffusion directions with the interpolated diffusion signals for each tuple. This results in input vectors of sizes 125 × 41, 125 × 21, and 125 × 5, along with a ground truth matrix of size 125 × 6.

Step 9: Zero-padding (Interpolated Data)
Zero-pad the input data for each tuple to create a 128 × 100 matrix.

Step 10: Dataset Naming
The resulting training datasets are named as follows:

"41diff_proposedModel" generated 41 diffusion directions using the SwinTransformer model.
"41diff_transformerDTI" generated 41 diffusion directions using the Davood Transformer model.
"21diff_proposedModel" generated 21 diffusion directions using the SwinTransformer model.
"21diff_transformerDTI" generated 21 diffusion directions using the Davood Transformer model.
"5diff_proposedModel" generated 5 diffusion directions using the SwinTransformer model.
"5diff_transformerDTI" generated 5 diffusion directions using the Davood Transformer model.
Visualisation of the Ground Truth, Proposed Method, LLS Fitting (Traditional) and Transformer DTI
The paper compares the diffusion direction of 41 using ground truth, proposed method, and LLS fitting Koay et al. (2006)
41diff_comparison
The paper compares the diffusion direction of 21 using ground truth, pro-posed method, LLS fitting Koay et al. (2006), and Transformer-DTI Karimi and Gholipour (2022)
21diff_comparison
The paper compares the diffusion direction of 5 using ground truth, proposed method, LLS fitting Koay et al. (2006), and Transformer-DTI Karimi and Gholipour (2022)
5diff_comparison
TBSS Analysis
Axial brain slice representing the Cingulum region, highlighted with p-value of two sample t-test(df=22). Green color: hypothesis testing tstat1 - Healthy CN > MCI, Red color: hypothesis testing tstat2 - Healthy CN < MCI.
TBSS_PT1
Coronal brain slice representing the Uncinate fasciculus region, highlighted with p-value of two sample t-test(df=22). Green color: hypothesis testing tstat1 - Healthy CN > MCI, Red color: hypothesis testing tstat2 - Healthy CN < MCI.
TBSS_pt2

.....................................................................................................
**Collaborators
....................................................................................................
Name	                 and   Email ID: 
Abhishek Tiwari	        at326@snu.edu.in
Ananya Singhal	        as146@snu.edu.in
Dr. Saurabh J. Shigwan	saurabh.shigwan@snu.edu.in
Dr. Rajeev Kumar Singh	Rajeev.kumar@snu.edu.in
**

