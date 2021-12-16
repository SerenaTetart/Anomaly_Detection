# Fraud_Detection

## Table of contents
* [General info](#general-info)
* [Requirements](#requirements)
* [Project details](#project-details)

## General info

This project goal is to classify fraudulent transactions from normal ones through the usage of unsupervised learning and data clustering for anomaly detection.

The dataset is from Vesta Corporation (on kaggle) through the competition: <a href= https://www.kaggle.com/c/ieee-fraud-detection> IEEE-CIS Fraud Detection</a>

The dataset is quite heavy, you might experience issues with your RAM.

## Requirements

The basic libraries for machine learning 😃

Libraries:
* Scikit-learn
* Numpy
* Pandas
* Tensorflow
* Keras

## Project details

Since the dataset is composed of 96.5% normal transactions and of only 3.5% fraudulent ones we are going to make an Anomaly Detection algorithm based on Novelty Detection (we train only on normal transactions).

For that we need an autoencoder which is an unsupervised Artificial Neural Network that attempts to encode the data by compressing it into the lower dimensions (bottleneck layer or code) and then decoding the data to reconstruct the original input.

<p align="center"> <b>Autoencoder Architecture</b> </p>
<p align="center">
<img src="https://user-images.githubusercontent.com/65224852/143266758-c5f101bc-1787-4694-a30c-596f8b5df599.png">
</p>

Then we compute the reconstruction error between the prediction and the original data with a Mean Squared Logarithmic Error.

And finally we set a threshold error between normal and fraudulent transactions, normal transactions should be smaller and fraudulents bigger than the threshold.

The results are 81.11% of True positive and 60.71% of False positive.

Which mean frauds will be detected 60.71% of the time and normal transactions misclassified 18.89% of the time

In order to improve it we'll use a One Class Support Vector Machine (OneClassSVM) in the next notebook.

For more informations check the .ipynb file !
