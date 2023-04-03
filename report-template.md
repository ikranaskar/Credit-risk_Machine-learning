# Module 12 Report Template

## Overview of the Analysis

Lending companies lend money or properties to borrowers with the expectation that they will either return the asset or repay the lender, but there is always a risk that the borrower will default. Credit risk is the risk of loss to the lender from a borrower's failure to repay a loan. In this analysis, historical lending activity data from a peer-to-peer lending service is used to build a machine learning model that can identify the creditworthiness of borrowers using the Logistic Regression algorithm. The goal is to predict which loans are low-risk and high-risk based on their status.

In this report, loan status is the target to predit.
A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting.

# Check the balance of our target values
y_variable.value_counts()
0    75036
1     2500
Name: loan_status, dtype: int64

Stages of machine learning in this repost consist of:
1.Importing data.
2.Import libraries
3.Data cleaning.
4.Separate the y variable.
5.Split the data into training and testing datasets by using train_test_split
6.Create a Logistic Regression Model with the Original Data and with Resampled Training Data.
7.Training the Model.
8.Model Evaluation


## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model with original data: 99% accurate. The Logistic Regression model fitted with the Original data predicted healthy loans 100% of the time and predicted high-risk loans 85% of the time.

 

# Print the classification report for the model
print(classification_report(y_test,predictions))
              precision    recall  f1-score   support

           0       1.00      0.99      1.00     18765
           1       0.85      0.91      0.88       619

    accuracy                           0.99     19384
   macro avg       0.92      0.95      0.94     19384
weighted avg       0.99      0.99      0.99     19384



* Machine Learning Model with Resampled Training Data: 99% accurate. The Logistic Regression model fitted with the OverSampled DataSet predicted healthy loans 99% of the time and predicted non-healthy loans 99% of the time.
 
# Print the classification report for the model
print(classification_report(y_train_sampled, r_prediction))
              precision    recall  f1-score   support

           0       0.99      0.99      0.99     56271
           1       0.99      0.99      0.99     56271

    accuracy                           0.99    112542
   macro avg       0.99      0.99      0.99    112542
weighted avg       0.99      0.99      0.99    112542
## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. 
Overall with the OverSampled DataSet accuracy has remained constant. The model does a great job of predicting and classifying high-risk loans.
