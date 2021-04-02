---
title: Stroke Classification from Wearable Motion Sensors
layout: project
date: 2020-05-13
tagline: Course project for CIS 640 Data-Driven IoT/Edge Computing @ SEAS University of Pennsylvania (2020)
description: Identifying patients with stroke history using wrist-worn sensor data
---

This is a class project for CIS 640 Data-Driven IoT/Edge Computing (Spring 2020) at University of Pennsylvania, advised by Dr. Insup Lee, Dr. Ivan Ruchkin and Dr. James Weimer.

**Abstract**  
The goal of this project is to classify whether a patient has had a stroke before based on motion sensor data collected from wrist-worn devices on both hands. The problem can be formulated as a multivariate time series (MTS) binary classification task. To deal with varying length time serie data and small sample size, I experimented mainly with 6 different models, including 4 distance based machine learning and 2 deep learning models, paired with a specific data preprocessor (no processing or keeping the data varying length, trimming to equal length and data augmentation by randomly sampling 10 minute segements). Applying multidimensional scaling (MDS) on pairwise Dynamic Time Warp (DTW) distances, and using an support vector machine (SVM) classifier yields the best results among the non deep learning models. However, its slow running time points to the need to use deep neural network to efficiently extract high level information for classification. Overall, the Separable Convolution model on augmented data performs the best, in terms of accuracy and running time. Depth-wise convolution provides a efficient and effective method to transform multivariate time series and extract a more compact feature representation for classification. Its ability to accurately classify patient based on 10 minutes of motion sensor data can potentially be used in online learning with streaming data. Validation has yet to be completed on a larger dataset to test the robustness and stability of this model.

See the full report [here](/assets/projects/stroke-clf-report.pdf)!