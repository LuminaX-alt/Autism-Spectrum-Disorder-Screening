# Autism-Spectrum-Disorder-Screening
These is are the mandatory requirements for this code repository:

Python >= 3.6
Pytorch >= 1.0
Look both packages are compatible before doing the installation and avoid unnecessary forced errors.

If you want to use this pipeline and/or request the dataset associated to this repository please cite our paper Mayor-Torres, J. M., Ravanelli, M., Medina-DeVilliers, S. E., Lerner, M. D., & Riccardi, G. (2021). Interpretable SincNet-based Deep Learning for Emotion Recognition from EEG brain activity. 2021 43rd Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC)
<img width="624" alt="image" src="https://github.com/user-attachments/assets/0386c80b-88fb-4933-bba2-e81b3c25e2c9" />
his system is composed of a SincConv layer, three standard conv-pool blocks such as Conv1, Conv2, and Conv3, and a fully-connected DNN1 coupled and connected to a softmax classifier. The three 2D convolutional blocks are composed of 32, 64, and 128 channels with kernel sizes of (100 x 10), (20 x 5), (5 x 2), respectively. Max-pooling used kernel sizes of (10 x 5), (5 x 2), (2 x 2) are also included in the pipeline. All the DNN units were ReLUs.
<img width="521" alt="image" src="https://github.com/user-attachments/assets/0af2a6f8-7939-43b8-bfb0-3070a6606bf7" />
![image](https://github.com/user-attachments/assets/492c423c-07b5-483d-826f-b1083b55df9e)
An important feature of our proposed SincNet-based system is to learn the frequency responses from TD and ASD participants using a by-design interpretability resource. This consists in an application of a Fast-Fourier-Transform on each filters' impulse-response learned from the SincConv layer. The following .gif loop shows the Power-Spectral-Density (PSD) for TD (blue) and ASD (red) individuals across all the 400 training loops we used on this experiment. This information is learned in unsupervised (implied) way without adding any diagnosis label.

To evaluate the SincLayer filter weights after training, we attached them for each 400 iterations (as training loops) and for each trial per participant (1-48) ids. You can calculate the PSD from the read_filters_act_more.m code. These SincLayer's weights and its corresponding files are located in the following two Google Drive links. These files are developed with an experiment implement with a size of the filters in the SincLayer of 50. You can calculate your own filters using the line 426 of the main_EEG_SincNet.py code
https://drive.google.com/file/d/1oRFI0lGdqxDOMsLhNyO8bLSfVB8-U4E-/view?usp=sharing
https://drive.google.com/file/d/1Xn1xJuYDOJnlh5YrB8jSt05p9wsVfrAi/view?usp=sharing
To process all the results for filter activation, metrics and results wrapping use all the code released in the m_files directory. To find the statistical difference between the frequency responses you need to run the read_filters_act_more.m function for each subject in the dataset, and subsequently you need to run the evaluate_differences_filters.m function, before you identify the folders you saved the filters files for TD and ASD groups.
