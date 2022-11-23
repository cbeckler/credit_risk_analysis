# Supervised ML and Credit Risk

## Overview of Project

### Purpose

The analyst was asked to assess whether or not loans should be classified as low or high risk based on several factors derived from the characteristics of the loans and their borrowers. The data had an imbalanced sample, with many more low risk loans than high risk loans. To minimize the impact of the imbalance, the analyst tested several statistical models to see which might have the best predictive accuracy, including logistic regression with a variety of sampling types, balanced random forest classifier, and easy ensemble classifier models. 

### Results

#### Logistic Regression--Random Oversampling

![random oversampling logistic regression results](https://github.com/cbeckler/credit_risk_analysis/blob/main/Resources/random_oversampler_log_reg.png)

* The balanced accuracy score (not pictured) was 0.65.
* The precision score was 0.65 overall, 0.64 for high risk loans, and 0.66 for low risk loans.
* The recall score was 0.65 overall, 0.69 for high risk loans, and 0.61 for low risk loans.

#### Logistic Regression--SMOTE Oversampling

![SMOTE oversampling logistic regression results](https://github.com/cbeckler/credit_risk_analysis/blob/main/Resources/smote_oversampler_log_reg.png)

* The balanced accuracy score (not pictured) was 0.67.
* The precision score was 0.67 overall, 0.65 for high risk loans, and 0.69 for low risk loans.
* The recall score was 0.67 overall, 0.73 for high risk loans, and 0.61 for low risk loans.

#### Logistic Regression--Cluster Centroids Undersampling

![cluster centroids undersampling logistic regression results](https://github.com/cbeckler/credit_risk_analysis/blob/main/Resources/cluster_undersampler_log_reg.png)

* The balanced accuracy score (not pictured) was 0.76.
* The precision score was 0.77 overall, 0.81 for high risk loans, and 0.73 for low risk loans.
* The recall score was 0.76 overall, 0.69 for high risk loans, and 0.84 for low risk loans.

#### Logistic Regression--SMOTEENN Combo Sampling

![SMOTEENN combo sampling logistic regression results](https://github.com/cbeckler/credit_risk_analysis/blob/main/Resources/smoteenn_combo_log_reg.png)

* The balanced accuracy score (not pictured) was 0.66.
* The precision score was 0.66 overall, 0.67 for high risk loans, and 0.66 for low risk loans.
* The recall score was 0.66 overall, 0.71 for high risk loans, and 0.61 for low risk loans.

#### Balanced Random Forest Classifier

![balanced random forest classifier results](https://github.com/cbeckler/credit_risk_analysis/blob/main/Resources/balanced_random_forest.png)

* The balanced accuracy score (not pictured) was 0.77.
* The precision score was 0.99 overall, 0.03 for high risk loans, and 1.00 for low risk loans.
* The recall score was 0.88 overall, 0.66 for high risk loans, and 0.89 for low risk loans.

#### Easy Ensemble Classifier

![easy ensemble classifier results](https://github.com/cbeckler/credit_risk_analysis/blob/main/Resources/easy_ensemble_classifier.png)

* The balanced accuracy score (not pictured) was 0.93.
* The precision score was 0.99 overall, 0.07 for high risk loans, and 1.00 for low risk loans.
* The recall score was 0.94 overall, 0.91 for high risk loans, and 0.94 for low risk loans.

## Summary

