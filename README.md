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

### Which Measure Matters

In order to select the best model, it's important to assess which measure of validity is best for for this task. The balanced accuracy score gives us an overall idea of if the loans are being classified correctly or not. The precision score assesses how reliable our positive classification is--ie, how likely loan marked high risk is to actually be high risk. The recall score tells us what percentage of the *actual* categories were correctly classified--ie, what percent of the high risk loans were marked as high risk. 

Accuracy does not give us enough information for this problem. In cases of low precision, some low risk loans may be incorrectly marked high risk and denied. In cases of low recall, some high risk loans may be incorrectly marked low risk and approved. The risk of financial loss to the business if a high risk loan is erronously marked and approved and then defaults is likely higher than the financial risk to the business of some low risk loans being mistakenly denied as high risk. Therefore, recall is the most important measure to use to assess these models.

### Model Performance

The model with the highest overall recall score is the Easy Ensemble Classifier, with a overall score of 0.94. However, it has a *very* low precision score for high risk loans, 0.07. The amount of low risk loans being incorrectly classified by this model may be too high, even with good validity for high risk loans being correclty classified. The model with the next highest recall score, Balanced Random Forest Classifier, has the same problem. 

The next highest recall score is the Logisitic Regression with Cluster Centroids Undersampling, with a overall recall score of 0.76. The overall precision score is a comparable 0.77. For high risk loans, the recall score is 0.69 with a precision score of 0.81. This is a much more balanced model, but the degree of risk of up to 30% of high risk loans being misclassified as low risk may be too great.

### Recommendations

Based on this, the analyst does not recommend any of these models for use yet. With both the Easy Ensemble and Balanced Random Forest Classifier models offer good protection against high risk loans being approved, they likely misclassify too many low risk loans and risk significant drops in revenue. The Cluster Centroid Undersampled Logisitc Regression offers more balanced results, but the margin of error on the high risk loans remains unacceptably high.

For potential next steps, the analyst would recommend finding the top 10 most impactful factors from the Balanced Random Forest Classifier model, and rerunning all models using just those predictor variables. It may be that the large amount of predictor variables, over 80, introduced too much noise into the models. The analyst is optimistic that a better fitting model may be found with further exploration.

