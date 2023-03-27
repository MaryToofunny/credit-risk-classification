# credit-risk-classification

**An overview of the analysis**

This homework consists of the following subsections:

1.Spliting the Data into Training and Testing Sets
  Openes the starter code notebook and then use it to complete the following steps.
  Read the lending_data.csv data from the Resources folder into a Pandas DataFrame.
  Created the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns.
  Noted A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting.
  Checked the balance of the labels variable (y) by using the value_counts function.
  Splitted the data into training and testing datasets by using train_test_split.

2.Creating a Logistic Regression Model with the Original Data(imbalanced)
  Employed logistic regression to complete the following steps:
  Fitted a logistic regression model by using the training data (X_train and y_train).
  Saved the predictions on the testing data labels by using the testing feature data (X_test) and the fitted model.
  Calculated the accuracy score of the model.
  

3.Predicting a Logistic Regression Model with Resampled Training Data(RandomOverSample)
  Used the RandomOverSampler module from the imbalanced-learn library to resample the data. Be sure to confirm that the labels have an equal number of data points.
  Used the LogisticRegression classifier and the resampled data to fit the model and make predictions.
  Evaluated the model’s performance by doing the following:
  Calculated the accuracy score of the model.
  Generated a confusion matrix.
  Printted the classification report.

**The results**
The results for regrassion model with imbalanced data set is as follow:
                                        precision    recall  f1-score   support

     Predicted.Healthy.Loans(low-risk)       1.00      0.99      1.00     18765
Predicted.Non-Healthy.Loans(high-risk)       0.85      0.91      0.88       619

                              accuracy                           0.99     19384
                             macro avg       0.92      0.95      0.94     19384
                          weighted avg       0.99      0.99      0.99     19384

How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?
This model , predicted low risk loan (0) with 100% precision and the high risk loan(1) with 85% precision.
According to the imbalanced classification report, the model predicted healthy loans (0) 100% of the times and predicted non-healthy loans(1) 85% of the times.
F1 Score is 99% as balanced accuracy score.

the results for oversampled data is as follow:
                                        precision    recall  f1-score   support

     Predicted.Healthy.Loans(low-risk)       1.00      0.99      1.00     18765
Predicted.Non-Healthy.Loans(high-risk)       0.84      0.99      0.91       619

                              accuracy                           0.99     19384
                             macro avg       0.92      0.99      0.95     19384
                          weighted avg       0.99      0.99      0.99     19384

The oversampled model generated an accuracy score of 99% which turned out to be higher than the model fitted with imbalanced data. The oversampled model performs better because it does a exceptional job in catching mistakes such as labeling non-healthy (high-risk) loans as healthy (low-risk). This is analyzed based off of the recall score increasing from the imbalanced model to the oversampled model 0.91 --> 0.99

**The results**
A lending company might want a model that requires a higher recall because:

healthy loans being identified as a non-healthy loan might be more costly for a lending company since it might cause the loss of customers but it would not be as big of a deal since they have not provided any funds to the customer indicating no loss in terms of money

non-healthy loans being identified as a healthy loan might surely be more costly for a lending company due to the loss of funds being provided by the lender.
