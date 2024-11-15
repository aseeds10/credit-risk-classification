# Credit Risk Analysis Report

## Overview of the Analysis

In this analysis, I evaluate a model based on loan risk. I used a dataset of historical lending activity 
from a peer-to-peer lending services company to build a model that can identify the creditworthiness of 
borrowers.
<br>
To determine creditworthiness, I looked at the other features in the current company dataset to train the model
to predict a client's potential loan status using actual clients' loan statuses (healthy vs unhealthy loans).
Current loan status is used as the indicator for creditworthiness in this model.
<br>
The variables ("features") used to train the model are listed below:
* Loan Size (loan_size)
* Interest Rate (interest_rate)
* Borrow Income (borrower_income)
* Debt to Income (debt_to_income)
* Number of Account (num_of_accounts)
* Derogatory Marks (derogatory_marks)
* Total Debt (total_debt)
<br>
<br>
Below is a brief overview of the stages of the machine learning process I went through as part of this 
analysis:
<br>
1. Loading dataset (csv) into analysis tool of choice (in this case python using libraries like pandas
and scikit learn). 
<br>
2. Split the Data into Training and Testing Sets - this allows you to use a part of the real consumer data
to train the model and the other to test whether the model is predicting creditworthiness in a satisfactory 
manner. I used train_test_split from scikit-learn for this step, amongst other functions.
<br>
3. Create a model with the original data.
<br>
4. Evaluate the model’s performance by generating a confusion matrix (evaluates true and false positives and
negatives) and a classification report (looks at accuracy and precision of model).
<br>
<br>
I decided on the Decision Tree model algorithim for this machine model due to it having a better classification report score (namely f1 scores) for both healthy and
unhealthy loan predictions compared to the other models tested in the analysis. Likewise, the false positives (FP) and false negatives (FN) shown in the confusion matrix were overall better when compared to the other models, with the exception of SVM, KNN, and Random Forest having less FNs. The three mentioned models with lower FNs were not selected as their classifcation report scores were lower, mainly in unhealthy loan predictions.


## Results

* **Logistic Regression Model Results:**
    * Test Acc: 0.993
    * Precision
      - Healthy Loan: 1
      - Unhealthy Loan: 0.86  
    *   Recall
     - Healthy: 0.99
     - Unhealthy: 0.93
    * F1 Score
     - Healthy: 1
     - UnHealthy: 0.89 

* **SVM Model Results:**
    * Test Acc: 0.994
    * Precision
      - Healthy Loan: 1
      - Unhealthy Loan: 0.86  
    *   Recall
     - Healthy: 0.99
     - Unhealthy: 0.99
    * F1 Score
     - Healthy: 1
     - UnHealthy: 0.92

* **Decision Trees Model Results:**
    * Test Acc: 0.990
    * Precision
      - Healthy Loan: 1
      - Unhealthy Loan: 0.97 
    *   Recall
     - Healthy: 1
     - Unhealthy: 0.96
    * F1 Score
     - Healthy: 1
     - UnHealthy: 0.96
 
* **Random Forest Model Results:**
    * Test Acc: 0.992
    * Precision
      - Healthy Loan: 1
      - Unhealthy Loan: 0.94
    *   Recall
     - Healthy: 1
     - Unhealthy: 0.99
    * F1 Score
     - Healthy: 1
     - UnHealthy: 0.96
 
* **KNN Model Results:**
    * Test Acc: 0.992
    * Precision
      - Healthy Loan: 1
      - Unhealthy Loan: 0.90 
    *   Recall
     - Healthy: 1
     - Unhealthy: 0.97
    * F1 Score
     - Healthy: 1
     - UnHealthy: 0.93

## Summary
In summary, I found that the **Decision Tree** was the best one for this use. This model kept the high f1 score for healthy loans seen by the other models but also had a higher f1 score unhealthy loans and improved confusion matrix relative to the other models. I would still reccommend human supervison with making the final decision due to 
the small chances of false positives and negatives, as both are important for banking institutions when handing out a loan.
