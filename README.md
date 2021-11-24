# Fraud_Detection

## Table of contents
* [General info](#general-info)
* [Requirements](#requirements)
* [Project details](#project-details)

## General info

This project goal is to classify fraudulent transactions from normal ones through the usage of unsupervised learning, autoencoder (anomaly detection) and data clustering.

The dataset is from Vesta Corporation (on kaggle) through the competition: IEEE-CIS Fraud Detection

(https://www.kaggle.com/c/ieee-fraud-detection)

The network is a fully connected layer with L1 regularisation and relu activations.

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

<p align="center">
<b>Autoencoder Architecture</b>
<img src="https://user-images.githubusercontent.com/65224852/143266328-39932c78-64f8-49a5-bb7e-deb7226b7cec.png">
</p>

Then we compute the reconstruction error between the prediction and the original data with a Mean Squared Error.

And finally we set a threshold error between normal and fraudulent transactions, normal transactions should be smaller and fraudulents bigger than the threshold.
