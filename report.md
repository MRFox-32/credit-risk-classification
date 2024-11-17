# Module 12 Report

## Overview of the Analysis

### Purpose
The purpose of this analysis is to train and evaluate a model based on loan risk that can identify the creditworthiness of borrowers. The analysis utilized lending data with the following attributes: loan_size, interest_rate, borrower_income, debt_to_income, num_of_accounts, derogatory_marks, total_debt, loan_status. In order to predict the number of healthy and high-risk loans, the loan_status variable was used for the value_counts to help understand the distribution of healthy versus high-risk loans.

### Process
The process utilized to analyze this dataset was:
1. Read the data
2. Data cleaning and preprocessing, if applicable
3. Split the data into training and testing sets
4. Scale the training and testing data sets using the StandardScaler
5. Fit a Logistic Regression model with the scaled training data
6. Make a prediction with the scaled test data
7. Generate a confusion matrix and print the classification report
8. Explore feature importance

### Methods
The analysis utilized the Logistic Regression algorithm to perform classification. Logistic regression does not provide feature importance; however, the coefficients can be interpreted in terms of odds ratios, which can provide insights into the impact of each feature.

## Results

### Machine Learning Model:
    * Accuracy: The accuracy score indicates the proportion of correctly predicted instances out of the total instances in the test set.
    * Precision: Metric for how accurately the model predicts whether values for "0" and "1" are actually the value.
    * Recall: Metric used to measure the ability of the model to identify all relevant instances within a dataset. 

Accuracy Score: 0.9937061494015683

| Class |  Precision  |   Recall   |
|-------|-------------|------------|
| 0     | 1.00 (100%) | 0.99 (99%) |
| 1     | 0.84 (84%)  | 0.99 (99%) |

### Confusion Matrix
            Predicted 0     Predicted 1
Actual 0	18652	        113
Actual 1	9	            610

### Classification Report
              precision    recall  f1-score   support

           0       1.00      0.99      1.00     18765
           1       0.84      0.99      0.91       619
    accuracy                           0.99     19384
   macro avg       0.92      0.99      0.95     19384
weighted avg       0.99      0.99      0.99     19384

### Feature Importance
            Feature    Coefficient            Absolute Coefficient
3    debt_to_income     8.510279              8.510279
4   num_of_accounts    -0.873690              0.873690
6        total_debt    -0.675715              0.675715
2   borrower_income    -0.675715              0.675715
1     interest_rate    -0.662862              0.662862
0         loan_size    -0.533836              0.533836
5  derogatory_marks     0.152887              0.152887

## Summary
The sole focus of this analysis was the Logistic Regression Model. Overall, this model should suffice for evaluating a borrower's creditworthiness by predicting whether a loan will be healthy or high-risk, though there are only 9 of actual "1" predicted in the confusion matrix, which is a small subset. The logistic regression was used because this model predicts the categorical dependent variable, which can be used to inform a "yes or no", "true or false, "0 or 1" decision like whether to provide a loan to borrowers based on their loan status. Other classification models such as decision trees, random forests, and support vector machines (SVM) could also be explored; however, the overall accuracy score, precision, and recall indicate that this will aid in providing context. In a real world setting, for those classified as high-risk, I would recommend focusing on the individual and their situation, considering additional factors such as their credit history or income stability.

The model is a good predictor for healthy versus high-risk loans overall, though it is better at predicting healthy loans. The accuracy score is 99%, which means that the model correctly identifies 99% of healthy and high-risk loans. The precision for "0" (healthy loans) is 100%, meaning all predicted healthy loans are healthy and the precision for "1" (high-risk loans) is 84%, so only 84% of high-risk loans were actually high-risk.

The debt-to-income ratio is the most influential feature in the model, which indicates lenders should prioritize this metric when evaluating borrowers. The other features also contribute to the model's decisions, but their effects are comparatively smaller. This positive coefficient indicates that as the debt-to-income ratio increases, the likelihood of a loan being classified as high-risk (Class 1) also increases significantly. This suggests that higher debt relative to income is a strong indicator of potential loan default.

## Conclusion
The model demonstrated an impressive accuracy score of approximately 99%, with a high precision of 100% for healthy loans and 84% for high-risk loans. A Receiver Operating Characteristic (ROC) curve was also visualized with an area under curve of 99%, which means the model has excellent performance in distinguishing between positive and negative classes. All of these results indicate that the model is highly effective in identifying healthy borrowers while also providing valuable insights into potential high-risk cases. Utilizing machine learning in the lending industry, as in this analysis, can be a valuable tool for providing data-driven insights. Utilizing models such as these can make the process more efficient allowing lenders to focusing more in-depth analysis on those classified as "high-risk".