# Grasp and Lift EEG Detection

## Overview
Certain hand movements like grasping, lifting or replacing an object create unique identifiable artifacts in the EEG signals. 

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

https://user-images.githubusercontent.com/38180831/207253198-36e50b82-1d8b-4ad6-a854-4617df5e9056.mp4

This data contains EEG recordings of subjects performing grasp-and-lift (GAL) trials. In order to collect this data set, 12 subjects performed 10 series of trials where every series contains 30 trials. During every trial, EEG brain signals were recorded from the subjects while they performed grasp-and-lift operations. The training set contains the first 8 series for each subject. The test set contains the 9th and 10th series. For each Grasp and Lift series, there are 6 events that take place in this order: HandStart, FirstDigitTouch, BothStartLoadPhase, LiftOff, Replace and BothReleased

Download the dataset here: [Grasp-and-Lift EEG Detection](https://www.kaggle.com/competitions/grasp-and-lift-eeg-detection/data)

The EEG data from three different electrodes are visualized below:
![image](https://user-images.githubusercontent.com/38180831/207249694-3473e787-21cb-4db4-987c-2d6e6ab7ce94.png)

## Model Performances
The following table compares the area under the Receiver operating characteristic (ROC) curve on the train and test dataset. 
![image](https://user-images.githubusercontent.com/38180831/207251070-329e5aa7-1473-4491-90b8-9129844e0649.png)

All the models were tested and the results were uploaded to the [Kaggle competition](https://www.kaggle.com/competitions/grasp-and-lift-eeg-detection/overview) on this dataset. The resulting scores obtained the models are compared below:

![image](https://user-images.githubusercontent.com/38180831/207251882-74acf500-a754-44a8-95c8-49c3d704cfea.png)


