## ACML2023 - Early Diagnosis of Alzheimer's Disease via Deep Learning 🧠

Welcome to our research project on "Early Diagnosis of Alzheimer's Disease through a Swin-Transformer-Based Deep Learning Framework Using Sparse Diffusion Measures."

About the Project 📖
Alzheimer's disease is a prevalent neurodegenerative condition, affecting an estimated 6.2 million people in the United States alone. Our research explores the potential of Transformer-based deep learning techniques to enhance the diagnosis of Alzheimer's disease by accelerating the processing of diffusion tensor imaging (DTI) data, particularly when using sparse measurements.

Diffusion Weighted Imaging (DWI) is a time-consuming process, with each diffusion direction taking between 2-5 minutes. For routine clinical diagnosis, at least 40 diffusion directions are required, resulting in a scanning duration exceeding 3 hours for each patient. Our proposed model, leveraging attention mechanisms, generates quantitative measures of fractional anisotropy (FA), axial diffusivity (AxD), and mean diffusivity (MD) using only 5 and 21 diffusion directions. This approach significantly reduces scanning time, making it practical for clinical use.

Key Contributions 🚀
Our research presents several significant contributions:

Efficient Learning of Spatial Correlation: Our model effectively captures spatial correlation among neighboring voxels, enhancing the robustness of diffusion tensor imaging parameters.

Speeding Up DTI Parameter Estimation: We accelerate the estimation of DTI parameters using sparse measurements, streamlining the diagnostic process.

Accurate Early Diagnosis: Our model provides accurate quantitative diffusion parameters, enabling the identification of early-stage Alzheimer's disease.

Getting Started: DTI Data Preprocessing Workflow 🛠️
Here's a brief overview of our data preprocessing workflow for DTI:

DTI Model Fit: Apply the DTI model fit from the DIPY Python package to process each DWI image individually, resulting in the computation of six diffusion components.

Voxel Selection: Select 100,000 voxels from each DWI image based on their fractional anisotropy (FA) score, excluding voxels with an FA score of zero.

Dataset Generation: Generate 100,000 tuples of (input, ground-truth), where each tuple comprises an input 5x5x5 voxel patch with 41 diffusion directions per voxel and a ground-truth 5x5x5 voxel patch with a 6x1 vector per voxel.

Signal Concatenation: Combine the diffusion signals of neighboring patches to construct matrices for each input voxel.

Direction and Signal Concatenation: Combine diffusion directions with diffusion signals to create input vectors.

Zero-padding: Zero-pad the input data for each tuple.

Qball-based Interpolation: Perform Qball-based interpolation on the input data from the "ADNI-41" dataset, yielding various directional diffusion signals.

Direction and Signal Concatenation (Interpolated Data): Combine diffusion directions with the interpolated diffusion signals.

Zero-padding (Interpolated Data): Zero-pad the input data for each tuple.

Dataset Naming: Naming conventions for the resulting training datasets are provided.

Visualizations 📊
We provide visual comparisons of diffusion directions using ground truth, our proposed method, and other methods for different diffusion directions.

Visualization 1: Diffusion direction of 41 directions
Visualization 2: Diffusion direction of 21 directions
Visualization 3: Diffusion direction of 5 directions
TBSS Analysis 🧠
We showcase TBSS analysis results for specific brain regions, highlighting differences between healthy controls and patients with Mild Cognitive Impairment (MCI).

TBSS Analysis 1
TBSS Analysis 2

Citation 📝
If you find our work useful, please consider citing our research:


@InProceedings{tiwari23,
      title = {Early Diagnosis of Alzheimer through Swin-Transformer-Based Deep Learning Framework using Sparse Diffusion Measures},
      author = {Tiwari, Abhishek and Singhal, Ananya and Shigwan, Saurabh J. and Singh, Rajeev Kumar},
      pages = {},
      crossref = {acml23},
      abstract = {Alzheimer disease is one of the most common neuro-degenerative diseases, with an estimated 6.2 million cases in the United States. This research article investigates the potential of Transformer-based deep learning techniques to accelerate the processing of diffusion tensor imaging (DTI) measures and improve the early diagnosis of Alzheimer disease (AD) using sparse data. Diffusion Weighted Imaging (DWI) is a time-consuming process, with each diffusion direction taking between 2-5 minutes, and at least 40 diffusion directions are needed for routine clinical diagnosis, which needs scanning duration exceeding 3 hours for each patient. By leveraging the attention mechanism, our proposed model generates quantitative measures of fractional anisotropy (FA), axial diffusivity (AxD), and mean diffusivity (MD) using 5 and 21 diffusion directions, making it useful for clinical diagnosis through reduced scanning time of more than half. Our experimental results on the Alzheimer's Disease Neuroimaging Initiative (ADNI) dataset demonstrate that our proposed model outperforms the traditional linear least square method, achieving accurate quantitative measurement of FA, AxD, and MD scores for early diagnosis of AD patients from healthy controls using sparse diffusion directions. Our analysis highlights the potential of Swin-Transformer attention-based deep learning framework to improve the early diagnosis and treatment of Alzheimer's disease.}


**Collaborators 👥
Meet the brilliant minds behind this research:

Abhishek Tiwari	        at326@snu.edu.in
Ananya Singhal	        as146@snu.edu.in
Dr. Saurabh J. Shigwan	saurabh.shigwan@snu.edu.in
Dr. Rajeev Kumar Singh	Rajeev.kumar@snu.edu.in

Feel free to reach out to us for any inquiries or collaborations. **

Stay tuned for more updates and insights on early Alzheimer's disease diagnosis through deep learning! 🧠✨
