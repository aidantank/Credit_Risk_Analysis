# Credit_Risk_Analysis

## Overview

## Resources
Data: [Loan Stats](Resources/LoanStats_2019Q1.csv)
Software: Visual Studio Code 1.71.2, Python 3.7.13, Jupyter Notebook 6.4.8
Python Libraries: numpy, pandas, sklearn, imblearn
Machine Learning Algorithms: RandomOverSampler, SMOTE, ClusterCentroids, SMOTEENN, BalancedRandomForestClassifier, EasyEnsembleClassifier

## Results

### Oversampling
#### Random Oversampling
![](Images/oversampling_acc.PNG)
![](Images/oversampling_cm.PNG)
![](Images/oversampling_classreport.PNG)

#### SMOTE Oversampling
![](Images/smote_acc.PNG)
![](Images/smote_cm.PNG)
![](Images/smote_classreport.PNG)

### Undersampling
![](Images/undersampling_acc.PNG)
![](Images/undersampling_cm.PNG)
![](Images/undersampling_classreport.PNG)

### Combination Over/Under Sampling
![](Images/smoteenn_acc.PNG)
![](Images/smoteenn_cm.PNG)
![](Images/smoteenn_classreport.PNG)

### Balanced Random Forest Classifier
![](Images/brfc_acc.PNG)
![](Images/brfc_cm.PNG)
![](Images/brfc_classreport.PNG)
![](Images/brfc_importance.PNG)

### Ensemble AdaBoost Classifier
![](Images/eec_acc.PNG)
![](Images/eec_cm.PNG)
![](Images/eec_classreport.PNG)


## Summary
Summarize and Recommend