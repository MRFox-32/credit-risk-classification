# credit-risk-classification
Train and evaluate a model based on loan risk that can identify the creditworthiness of borrowers.

## Instructions
This Challenge is divided into the following:
1. Split the Data into Training and Testing Sets
2. Create a Logistic Regression Model with the Original Data
3. Write a Credit Risk Analysis Report

## Split the Data into Training and Testing Sets
1. Read the lending_data data into a Pandas DataFrame.
2. Create the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns. Note: A value of 0 means that the loan is healthy and 1 means that the loan has a high risk of defaulting.
3. Split the data into training and testing datasets.

## Create a Logistic Regression Model with the Original Data
1. Fit a logistic regression model by using the training data (X_train and y_train).
2. Save the predictions for the testing data labels by using the testing feature data (X_test) and the fitted model.
3. Evaluate the model’s performance:
     * Generate a confusion matrix.
     * Print the classification report.
     * Answer the following question: How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

## Write a Credit Risk Analysis Report
Write a brief report that includes a summary and analysis of the performance of the machine learning models that you used. You should write this report as the README.md file included in your GitHub repository, ensuring that it contains the following:
1. An overview of the analysis: Explain the purpose of this analysis.
2. The results: Using a bulleted list, describe the accuracy score, the precision score, and recall score of the machine learning model.
3. A summary: Summarize the results from the machine learning model. Include your justification for recommending the model for use. If you don’t recommend the model, justify your reasoning.
