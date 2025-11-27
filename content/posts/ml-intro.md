---
title: "Introduction to Machine Learning"
date: 2025-10-06T11:00:44+08:00
draft: true
params:
  math: true
---

# What is Machine Learning


Machines improving **performance(P)** at a **task(T)** from **experience(E)**

How to go about solving Machine Learning problems, in a retrospect

Type of learning

* Supervised: labeled data inputs, to create a model for better pridiction
  eg:
    - Regressions: if the input's output are real numbers
    - Classification: when the input's output are categories
* Unsupervised: datas without the output as inputs, to create a model that best describes/represents a structures in the datas
  eg:
    - clusstering: structures the data into cluster/groups, sub group groups for better understanding of the data
* Reinforcement learning: no data at the beginning, learn by interaction with the Task, like a robot trying to learn by experience
  eg:

1. Framing Learning Chess
  T = playing Chess
  P = win rate against opponents
  E = playing games agains itself, or players playing the bot with its task

2. Data Curation and Analysis
  curation
    source/scrape
    collections
    labeling
  Data analysis & visialization
    updating the curated datas missing values, false encodings, and more wrong and incosistencies 

3. Designing ML
 hypothesis class: model family
 loss function: formalize performance matrix
 optimization: take the data, and learn the model
 hyperparameters: parameters we choose for better outputs
 features

4. Train
5. Validate and Evaluate

## Linear Regression(Supervised Learning)

we take a linear line to classify points

### Loss functions

* **MSE**: is better for computations, because it has a convex shape
* **MAE(Mean Absolute Error)**: better for removing the outliers
$$
\frac{1}{n} \sum_{i=1}^n |y_i - \hat{y}_i|
$$
* **Mean Relative Error**: 
$$ \frac{1}{n} \sum_{i=1}^n \frac{|y_i - \hat{y}_i|}{|y_i|} $$
* $R^2$ **Score**: better for showing how much variation is in the data
$$ 1 - \frac{\text{MSE}}{\text{Variance}}$$
* **Pearson correlation**:
* **Rank-order correlations**:
