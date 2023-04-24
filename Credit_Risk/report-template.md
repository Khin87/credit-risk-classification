# Credit Risk Classification Analysis

## Overview of the Analysis

The purpose of this anaylsis is to construct a model to predict the creditworthness of borrowers from a peer-to-peer lending service company. The model should be able to distinguish between healthy and highly-risk loans so the company minimize the cost of approving highly-risky loans that default, and maximize the profit associated to approve healthy loans.

The data used in the model corresponds to historical loans and key financial variables associated to the borrower financial position and the loan characteristics. This data helps to determine whether a person will be able to pay back a loan or not. These variables are the loan size, the interest rate, the borrower income, the borrower debt to income ratio, the number of accounts of the borrower, his/her total debt, and whether he/she has any derogatory marks.

## The Machine Learning Process

1. Previously in this data analysis, the data was provided in a csv file. And read this file into a Pandas dataframe.
2. Split the data into training and testing data sets. The training data is used to fit the model, and the test data (25% of the set) is used to measure the quality of the predictions.
3. Create two Logistic Regression machine learning models from the Linear Model module of SKLearn. The first one, Machine Learning Model 1, directly uses the original loan data. The second one, Machine Learning Model 2, attempts to improve the model by applying a technique called oversampling to deal with the imbalance between the amount of high-risk and healthy loans in the original data.
4. Fit the training data to the model, which means to adjust the parameters for the best possible replication of the targets included in the data. The fit method of the Logistic Regression model is used for that purpose.
5. Predict the healthy or high-risk loan of the separated test sample data in both models. For this step, used the predict method of the LogisticRegression model.
6. Finally we compared the result by using three key metrics, which are the balance accuracy score, the precision score, and the recall score.

## Results

The results of the three key metrics described are shown in the below for each model.

* Machine Learning Model 1 metrics:

  * Balance Accuracy score: 95.8%
  * Precision score:
    * Healthy loans: 100%
    * High-risk loans: 85%
    * Average: 99%
  * Recall scores:
    * Healthy loans: 99%
    * High-risk loans: 91%
    * Average:99%

* Machine Learning Model 2 metrics:

  * Balance Accuracy score: 99.6%
  * Precision score:
    * Healthy loans: 100%
    * High-risk loans: 84%
    * Average: 99%
  * Recall scores:
    * Healthy loans: 99%
    * High-risk loans: 99%
    * Average: 99%

## Summary

By comparing the two Logistic Regression machine learning models were constructed and compared on predicting the quality of loans. Model 1 used the imbalanced original data, and Model 2 included a treatment for that imbalance. Both models have positive results. Both have a balance accuracy above 95%, and almost perfect metrics for healthy loans recognition. That said, model 2 have better performance in recognizing high-risk loans, with a recall of 99%, above the 91% of Model 1.

Therefore, we recommend to use of Model 2, because its excellent balanced performance. We acknoledge the draw back of falsely classifying healthy loans as risky 0.85 to 0.84 of the time. However that opportunity cost does not imply a risk for the business survival. The more important characteristics is to prevent defaults, and the performance of the model is statistically unbeatable in that respect.

