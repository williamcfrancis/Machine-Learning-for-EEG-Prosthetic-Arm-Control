# Machine Learning for Prosthetic Arm Control with EEG Data

## Overview
In this project, we used machine learning techniques to detect hand movements, such as grasping and lifting, in EEG data. These hand movements can be used to control robotic prosthetic arms. We experimented with three data preprocessing techniques for EEG signals: butter low pass filtering, wavelet denoising, and stacking butter low pass filters. We also utilized various classification models, including Support Vector Machines, Logistic Regression, Random Forest, Linear Discriminant Analysis, Quadratic Discriminant Analysis, and Convolutional Neural Networks. We also designed weighted ensembles of traditional models to improve performance.

For each Grasp-And-Lift trial, we detect 6 events:

1. HandStart
2. FirstDigitTouch
3. BothStartLoadPhase
4. LiftOff
5. Replace
6. BothReleased

Learning these patterns using machine learning techniques open the gates to using them as control inputs for a robotic prosthetic arm. 
For a complete report of the project with ablation study and design details, please refer to [report.pdf](https://github.com/williamcfrancis/Grasp-and-Lift-EEG-Detection-using-ML-algorithms/blob/main/Report.pdf)

## Algorithms
We experimented with three data pre-processing techniques for EEG signals: 

* Butter low pass filtering
* Wavelet denoising
* Stacking butter low pass filters 

Further, we experimented with different classification models: 

* Support Vector Machines 
* Logistic Regression
* Random Forest
* Linear Discriminant Analysis
* Quadratic Discriminant Analysis
* PCA with Random Forest

We designed three weighted ensembles of these traditional models:

* Linear Discriminant Analysis (0.4 %) + Random Forest (0.35 %) + Logistic Regression (0.25 %)
* Linear Discriminant Analysis + Logistic Regression
* Random Forest + Logistic Regression + Quadratic Discriminant Analysis + Linear Discriminant Analysis

And finally, a deep learning technique,

* Convolutional Neural Networks

## Data
The dataset for this project consists of EEG recordings of subjects performing grasp-and-lift trials. During each trial, EEG brain signals were recorded while the subject performed the hand movement. The training set includes the first 8 series of trials for each subject, while the test set includes the 9th and 10th series. There are 6 different hand movement events that take place during each trial: HandStart, FirstDigitTouch, BothStartLoadPhase, LiftOff, Replace, and BothReleased.

The dataset collection process is shown below.

https://user-images.githubusercontent.com/38180831/207253198-36e50b82-1d8b-4ad6-a854-4617df5e9056.mp4

Download the dataset here: [Grasp-and-Lift EEG Detection](https://www.kaggle.com/competitions/grasp-and-lift-eeg-detection/data)

The EEG data from three different electrodes are visualized below:
![image](https://user-images.githubusercontent.com/38180831/207249694-3473e787-21cb-4db4-987c-2d6e6ab7ce94.png)

## Run
1. Open [Grasp_and_Lift_ML.ipynb](https://github.com/williamcfrancis/Grasp-and-Lift-EEG-Detection-using-ML-algorithms/blob/main/Grasp_and_Lift_ML.ipynb) using Google colab, Jupyter Notebook or other supporting ipynb editor. 
2. Download the data and load it into the notebook.
3. Run the cells sequentially

## Model Performances
We evaluated the performance of our models using the area under the Receiver Operating Characteristic (ROC) curve on both the train and test datasets. Our models also achieved strong results in the [Grasp-and-Lift Kaggle competition](https://www.kaggle.com/competitions/grasp-and-lift-eeg-detection/overview), with a final score of 0.945.

The following table compares the area under the Receiver operating characteristic (ROC) curve on the train and test dataset. 
![image](https://user-images.githubusercontent.com/38180831/207251070-329e5aa7-1473-4491-90b8-9129844e0649.png)

The resulting scores obtained the models are compared below:

![image](https://user-images.githubusercontent.com/38180831/207251882-74acf500-a754-44a8-95c8-49c3d704cfea.png)


