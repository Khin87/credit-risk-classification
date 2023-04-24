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
  * High-risk loans: 92%
  * Average:99%
 
* Machine Learning Model 2 metrics:

  * Balance Accuracy score: 99.6%
  * Precision score:
  * Healthy loans: 100%
  * High-risk loans: 85%
  * Average: 100%
  * Recall scores:
  * Healthy loans: 99%
  * High-risk loans: 100%
  * Average: 99%

From this results we can make the following conclusions:

The Balance Accuracy shows that there is an overall significant improvement in the model recall from 95.8% to 99.6% when applying oversampling. This improvement comes from the improvement in the recall of hig-risk loans, as it will be explained next.

When including resampling, there is an optimal improvement in the recall from 92% to 100%. That means that all of the negative falses (loans declared as healthy when they were highly risky) now are correctly labeled as 1 (high-risk loan). This is great in terms of controling the cost associated to the default of loans. Without resampling, the bank would have to absorve the cost of the high-risk loans that were incorrectly classified as healthy. Fortunately, when applying the resample to control the imbalance, we see that the cost of default is prevented by the improved model at the highest level.

High-risk loans has the same precision of 85% in both models. This means that the oversampling does not increase the capacity of the model to predict more efficiently the high-risk loans. In other words, the proportion of incorrect predictions of healthy loans as high-risk loans (false positives), and the opportunity cost associated to that wrong assesment is the same in both models.

Healthy loans are predicted with a precision of 100%, which is optimal, and a recall of 99%, which is also very high. This happens in both models. Oversampling does not make a difference in the classification of this class, and it may be arguably consider not necesary either due to the high performance.





## Summary

Summarise the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
