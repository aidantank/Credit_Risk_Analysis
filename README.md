# Credit_Risk_Analysis

## Overview
This report attempts to use machine learning to predict which credit card transactions are high risk. Using a large loan stats dataset, we will run several machine learning models and see which is best at predicting whether a credit card transaction is low or high risk. The models will include oversampling, undersampling, forest tree, and ensemble. The training and testing of the models will happen in a 75/25 split. The models will be trained on 75% of the sample data and will be tested using the other 25% of the sample. 

## Resources
Software: Visual Studio Code 1.71.2, Python 3.7.13, Jupyter Notebook 6.4.8  
Python Libraries: numpy, pandas, sklearn, imblearn  
Machine Learning Algorithms: RandomOverSampler, SMOTE, ClusterCentroids, SMOTEENN, BalancedRandomForestClassifier, EasyEnsembleClassifier

## Results
The number of high risk credit card transactions are considerably lower than the low risk transactions.
- Total Values Tested Low Risk: 17,104
- Total Values Tested High Risk: 101

The results by each model focus on the summary of a confusion matrix. The matrix details the number of true positive, true negative, false positive, and false negative results by each model. In this case, the low risk and high risk represent positive/negative. To determine the predictive nature of each model we will use the below statistics:
- Accuracy: Percentage of the total predictions the model got correct.
- Precision: Percentage of the positive predictions the model got correct.
- Sensitivity: Percentage of the actual positive results the model predicted correct.
- F1: Blended score using precision and sensitivity together.

### Oversampling
#### Random Oversampling
The random oversampling machine learning model focuses on changing the sampling size then using a logistic regression model. This sampling method randomly selects values from the smaller sample and adds them to it so that the two sample sizes are equal. Below is the confusion matrix that display the predicted results versus the actual ones.

![](Images/oversampling_cm.PNG)

Model Results<br>
- Accuracy Score: 0.64640

- Precision Low Risk: 1.00
- Sensitivity Low Risk: 0.58
- F1 Score Low Risk: 0.73

- Precision High Risk: 0.01
- Sensitivity High Risk: 0.71
- F1 Score High Risk: 0.02

#### SMOTE Oversampling
SMOTE or synthetic minority oversmapling technique is another way of adding values to the lower sample (high risk transactions). Instead of using random sample values, SMOTE creates new values to add to the original same that are equidistant from existing sample values until the two sample are the same size. Below is the confusion matrix:

![](Images/smote_cm.PNG)

Model Results<br>
- Accuracy Score: 0.65862

- Precision Low Risk: 1.00
- Sensitivity Low Risk: 0.40
- F1 Score Low Risk: 0.57

- Precision High Risk: 0.01
- Sensitivity High Risk: 0.69
- F1 Score High Risk: 0.01

### Undersampling
Undersampling is the other sample techinque that brings the larger of the two samples down by randomly removing samples. The logistic regression model is also used after the data is undersampled. Below is the confusion matrix:

![](Images/undersampling_cm.PNG)

Model Results<br>
- Accuracy Score: 0.54473

- Precision Low Risk: 1.00
- Sensitivity Low Risk: 0.40
- F1 Score Low Risk: 0.57

- Precision High Risk: 0.01
- Sensitivity High Risk: 0.69
- F1 Score High Risk: 0.01

### Combination Over/Under Sampling
The combination of over/under sampling method used is SMOTEENN or sythetic minority oversampling techinique and edited nearest neighbor. This sampling techinque creates new artifical sample values and then if those same values are closer to the other sample than their own sample, then the are removed from the sample pool. Again a logistic regression model is used to test the sampling techique. The confusion matrix of the results is below:

![](Images/smoteenn_cm.PNG)

Model Results<br>
- Accuracy Score: 0.63671

- Precision Low Risk: 1.00
- Sensitivity Low Risk: 0.89
- F1 Score Low Risk: 0.94

- Precision High Risk: 0.01
- Sensitivity High Risk: 0.70
- F1 Score High Risk: 0.02

### Balanced Random Forest Classifier
Instead of changing the samples, we can change the machine learning model from logistic to balanced random forest. The algorithm uses a lot of decision trees that predict the outcome based on a series of true and false questions. Each tree comes up with a decision and whatever decision is the highest, the model predicts that outcome. Also, the random forest model can let you know when features are most important to the model. Below is a confusion matrix of the balanced random forest model and a feature importance table noting the top five features by importance:

![](Images/brfc_cm.PNG)
![](Images/brfc_importance.PNG)

Model Results<br>
- Accuracy Score: 0.76656

- Precision Low Risk: 1.00
- Sensitivity Low Risk: 0.89
- F1 Score Low Risk: 0.94

- Precision High Risk: 0.03
- Sensitivity High Risk: 0.64
- F1 Score High Risk: 0.06
- High Feature Importance: Total Recorded Principal on the loan

### Ensemble AdaBoost Classifier
Lastly, the ensemble boosting model is a machine learning model that has a bunch of models that learn from the past models. The first model might have weaknesses, and so the second model then weights those weaknesses higher. This continues based on the number of models you specify. The confusion matrix below is for the Ensemble AdaBoost model:

![](Images/eec_cm.PNG)

Model Results<br>
- Accuracy Score: 0.93166

- Precision Low Risk: 1.00
- Sensitivity Low Risk: 0.94
- F1 Score Low Risk: 0.97

- Precision High Risk: 0.09
- Sensitivity High Risk: 0.92
- F1 Score High Risk: 0.16


## Summary
A large takeaway from the results of the machine learning models is the large disparity in low risk vs high risk credit card transactions makes it nearly impossible to have a high precision score for high risk transactions. There are so many predicted high risk values in comparison to actual high risk values. Even though that is the case, it would be preferable to determine a transaction is high risk when it is low risk than determine a transaction is low risk when it is high risk. This is because the user of the credit card could be informed of a high risk transaction and okay it. Most models have 1.00 or 100% precision for low risk. 

Based on the accuracy scores and sensitivity scores, the ensemble adaboost classifier model outpreforms the rest by quite a margin. It boasts a 93.166% accuracy level on credit card transactions with a 92% sensitvity score for high risk ones. The model is very accurate overall, and very accurate at determining if an actual high risk transaction is high risk.