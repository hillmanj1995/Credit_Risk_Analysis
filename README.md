lysis

## Overview
The analyst was tasked with running an analysis on credit risk using different techniques to train and evaluate models with unbalanced classes. Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, the Analyst oversampled the data using the RandomOverSampler and SMOTE algorithms, and undersampled the data using the ClusterCentroids algorithm. Then, they used a combinatorial approach of over and undersampling using the SMOTEENN algorithm. Next, they compared two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk.  An evaluation of the performance of the models was made at the end of the analysis to determine whether they should be used to predict credit risk.

## Results

### Naive Random Oversampling
The Analyst used the RandomOverSampler to randomly select instances of the minority class to add to the training set until the majority and minority classes are balanced.  The count of values classified 51,369 values as high risk and 51,369 values as low risk.  The code for count of values and results of the analysis are shown below:

![random_over_count.png](https://github.com/hillmanj1995/Credit_Risk_Analysis/blob/main/Resources/random_over_count.png)

#### Results:

![random_over_report.png](https://github.com/hillmanj1995/Credit_Risk_Analysis/blob/main/Resources/random_over_report.png)

1. Balanced Accuracy Score: 57.97%
2. Precision: 1%/100% (high risk/low risk)
3. Recall: 45%/71% (high risk/low risk)

### SMOTE (Synthetic Minority Oversampling Technique) Oversampling
Similar to the RandomOverSampler, synthetic minority oversampling technique (SMOTE) is another oversampling approach the Analyst used to deal with unbalanced datasets.  Using SMOTE, the size of the minority is increased, but instead of adding randomly selected instances to the minority class, SMOTE interpolates new instances between the existing minority values.  The results of the analysis are shown below:

#### Results:

![SMOTE_report.png](https://github.com/hillmanj1995/Credit_Risk_Analysis/blob/main/Resources/SMOTE_report.png)

1. Balanced Accuracy Score: 64.44%
2. Precision: 1%/100% (high risk/low risk)
3. Recall: 55%/74% (high risk/low risk)

### Undersampling - Cluster Centroid Method
Another method of evaluating unbalanced models is to undersample using the Cluster Centroid method.  The Analyst used this algorithm to identify clusters of the majority class, then generate synthetic data points, called centroids, that are representative of the clusters. The majority class is then undersampled down to the size of the minority class. The count of values classified 243 values as high risk and 243 values as low risk.  The count of the undersampled values and the results of the analysis are shown below:

![CC_count.png](https://github.com/hillmanj1995/Credit_Risk_Analysis/blob/main/Resources/CC_count.png)

#### Results:

![CC_report.png](https://github.com/hillmanj1995/Credit_Risk_Analysis/blob/main/Resources/CC_report.png)

1. Balanced Accuracy Score: 54.10%
2. Precision: 1%/99% (high risk/low risk)
3. Recall: 54%/54% (high risk/low risk)

### Combination (Over and Under) Sampling - SMOTEENN
SMOTEENN is a method of analysis that combines the SMOTE and Edited Nearest Neighbors (ENN) algorithms.  SMOTEEN works in 2-steps: 1.) Oversample the minority class with SMOTE, 2.) Clean the resulting data with an undersampling strategy. If the two nearest neighbors of a data point belong to two different classes, that data point is dropped.  The Analyst found that the count of values classified 68,458 values as high risk and 62,022 values as low risk.  The count of the undersampled values and the results of the analysis are shown below:

![combo_count.png](https://github.com/hillmanj1995/Credit_Risk_Analysis/blob/main/Resources/combo_count.png)

#### Results:

![combo_report.png](https://github.com/hillmanj1995/Credit_Risk_Analysis/blob/main/Resources/combo_report.png)

1. Balanced Accuracy Score: 65.24%
2. Precision: 1%/100% (high risk/low risk)
3. Recall: 69%/61% (high risk/low risk)

### Balanced Random Forest - Classifier
A classifier in machine learning is an algorithm that automatically orders or categorizes data into one or more of a set of “classes.”  This is a way used by many analysts to reduce bias in a prediction.  For this analysis, The Analyst used a BalancedRandomForestClassifier Model to predict credit risk. The BalancedRandomForestClassifier Model will sample the data and build several smaller, simpler decision trees to create a prediction.  The results of the analysis are shown below:

#### Results:

![rbf_report.png](https://github.com/hillmanj1995/Credit_Risk_Analysis/blob/main/Resources/rbf_report.png)

1. Balanced Accuracy Score: 67.30%
2. Precision: 90%/100% (high risk/low risk)
3. Recall: 35%/100% (high risk/low risk)

### Easy Ensemble AdaBoost - Classifier
The EasyEnsembleClassifier is a method of prediction that uses iteration to build a more robust model based on past model/decisions and eliminate error and bias. The results of the analysis are shown below:

#### Results:

![eec_report.png](https://github.com/hillmanj1995/Credit_Risk_Analysis/blob/main/Resources/eec_report.png)

1. Balanced Accuracy Score: 91.79%
2. Precision: 9%/100% (high risk/low risk)
3. Recall: 89%/94% (high risk/low risk)

## Summary
The analysis of all six predictive models showed The Analyst that the EasyEnsembleClassifer model yielded the best results with an accuracy rate of 91.79% and a precision of 9% when predicting high risk clients.  The recall for the model was also the highest at 89% recall for high risk and 94% recall for low risk clients.  The Analyst would recommend this model as it is the most accurate and sensitive when making its predictions.
