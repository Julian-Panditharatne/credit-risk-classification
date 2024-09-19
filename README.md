# Credit Risk Classification Challenge

## Overview of the Analysis

* The purpose of the analysis is to build, train, and evaluate a model that can identify the creditworthiness of borrowers.
* A csv file, named `lending_data.csv`, contained the dataset of historical lending activity from a peer-to-peer lending services company that was used to train and evaluate the model.
* The dataset had the following variables:
  * **loan_size**.
  * **interest_rate**.
  * **borrower_income**.
  * **debt_to_income**.
  * **num_of_accounts**.
  * **derogatory_marks**.
  * **total_debt**.
  * **loan_status**.
* The variable that the model is designed to predict is **loan_status**.
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any other algorithms).
* The model was built, trained, and evaluated in the following manner:
  * The data was split into Training and Testing Sets using the following steps:
    * **Step 1**: Read the `lending_data.csv` data from the `Resources` folder into a Pandas DataFrame.
    * **Step 2**: Create the labels set (`y`)  from the “loan_status” column, and then create the features (`X`) DataFrame from the remaining columns.
    * **Step 3**: Split the data into training and testing datasets by using `train_test_split`.
  * The Logistic Regression Model was built, trained, and evaluated using the following steps:
    * **Step 1**: Fit a logistic regression model by using the training data (`X_train` and `y_train`).
    * **Step 2**: Save the predictions on the testing data labels by using the testing feature data (`X_test`) and the fitted model.
    * **Step 3**: Evaluate the model’s performance by doing the following:
      * Generating a confusion matrix.
      * Printing the classification report.

---

## Results

* Logistic Regression Learning Model:
  * Accuracy score: 0.99
  * Precision scores:
    * `0` **(healthy loan):** 1.00
    * `1` **(high-risk loan):** 0.87
  * Recall scores:
    * `0` **(healthy loan):** 1.00
    * `1` **(high-risk loan):** 0.95
  
---

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:

* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

* The logistic regression model was better at predicting `0` (healthy loans) than `1` (high-risk loans).
* Even though precision score for `1` (high-risk loans) is the weakest score out of all of them, it is still a fairly strong.
  * This indicates that the model seems to have a fairly low false positive rate.
  * Which means that it seems fairly unlikely for the model to misidentify a healthy loan as a high-risk loan.
* The recall score for `1` (high-risk loans) is significantly strong.
  * This indicates that the model seems to have a significantly low false negative rate.
  * Which means that it seems significantly unlikely for the model to misidentify a high-risk loan as a healthy loan.
* Therefore, I would recommend performing further training and testing on the model to try to improve its precision and recall scores for high-risk loans; and given that the overall accuracy, precision, and recall scores are quite high already, I would recommend using the model.
