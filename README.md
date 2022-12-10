# Grasp and Lift EEG Detection

For a complete report of the project with ablation study and design details, please refer to [report.pdf](https://github.com/williamcfrancis/Grasp-and-Lift-EEG-Detection-using-ML-algorithms/blob/main/Report.pdf)

## Overview
Certain hand movements like grasping, lifting or replacing an object create unique identifiable artifacts in the EEG signals. Learning these patterns using machine learning techniques open the gates to using them as control inputs for a robotic prosthetic arm. 

We experimented with three data pre processing techniques for EEG signals: 
* Butter low pass filtering
* Wavelet denoising
* Stacking butter low pass filters 

Further, we experimented with different classification models: 

* Support Vector Machines \
* Logistic Regression\
* Random Forest\
* Linear Discriminant Analysis\
* Quadratic Discriminant Analysis

We tried 3 different weighted ensembles of these traditional models as well.

* PCA + Random Forests\
* Linear Discriminant Analysis + Random Forest + Logistic Regression\
* Linear Discriminant Analysis + Logistic Regression\
* Random Forest + Logistic Regression + Quadratic Discriminant Analysis + Linear Discriminant Analysis

And finally, we used a deep learning technique,

* Convolutional Neural Networks

## Data
The  $10,000 Kaggle competition 
