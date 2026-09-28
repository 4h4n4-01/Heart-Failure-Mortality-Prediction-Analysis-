# Notebooks
This directory contains a comprehensive Jupyter notebook demonstrating an end-to-end machine learning pipeline for predicting heart failure mortality using clinical data.

The notebook covers:

## Exploratory Data Analysis (EDA)

Distribution analysis of continuous and categorical features

Correlation heatmaps and feature relationship visualisation

Outlier detection using the IQR method

## Data Preprocessing

Train–test splitting with stratification

Feature scaling for linear models

Class imbalance handling using SMOTE (applied correctly on training data only)

## Feature Selection

L1-regularized logistic regression to identify dominant predictors

Comparison between full feature set and reduced feature models

## Model Development

Logistic Regression

Random Forest Classifier

## Model Evaluation

Confusion matrices

Accuracy, precision, recall, and F1-score

ROC–AUC curve analysis

## Key Insights

Survival time, renal function (serum creatinine), and cardiac performance (ejection fraction) emerged as dominant predictors

Linear models generalized better than tree-based models under class-balanced conditions

Feature selection improved interpretability without significant loss in performance

## Notebook File

Heart Failure Analysis.ipynb: the complete workflow from data exploration to model evaluation
