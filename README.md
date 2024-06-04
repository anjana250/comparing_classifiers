#  Comparing Performance of Classifiers K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines

[Link to Jupyter Notebook](https://github.com/anjana250/comparing_classifiers/blob/main/module_17_starter/prompt_III.ipynb)


## Business Objective


The goal is to optimize the direct marketing campaigns of a Portuguese banking institution by leveraging historical data to predict whether a client will subscribe to a bank term deposit. The marketing campaigns are conducted via phone calls, often requiring multiple contacts with the same client. By accurately predicting the likelihood of subscription, the bank aims to improve the efficiency of its marketing efforts, reduce operational costs, and enhance customer engagement.

To achieve this, we will analyze the following types of data:

Client Demographics: Age, job type, marital status, education level, default status, housing loan status, and personal loan status.
Last Contact Information: Communication type, last contact month, last contact day of the week, and duration of the last contact.
Campaign Data: Number of contacts during the current campaign, days since the last contact from a previous campaign, number of previous contacts, and the outcome of the previous campaign.
Economic Indicators: Employment variation rate, consumer price index, consumer confidence index, Euribor 3-month rate, and the number of employees.
The target variable is whether the client subscribed to the term deposit ('yes' or 'no'). By developing a predictive model, the bank can better identify potential clients who are more likely to subscribe, thereby maximizing the return on investment for marketing campaigns and improving overall customer satisfaction.

## Data Preparation

The Dataset did not have any missing values but did contain 28 duplicates. Those values were dropped. The categorical columns that were 

## Modeling
The four models chosen are:
1. Logistic Regression
2. K Nearest Neighbor
3. Decision Trees
4. Support Vector Machines

Initially these models were fitted using only their default parameters. And while the metrics were decent- there was a lot of room for improvement!
<img width="400" alt="Screenshot 2024-06-04 at 11 54 59 AM" src="https://github.com/anjana250/comparing_classifiers/assets/15185723/2ecdafea-18e5-4a2b-ba21-bd68df03fcef">

### Analysis of Default Models:

1. Logistic Regression: The difference between train and test accuracy is small, which is a good thing and indicates good generalization.
2. KNN: There's a moderate drop in test accuracy compared to train accuracy, suggesting some overfitting.
3. Decision Tree: Decisions Treee has a perfect Train accuracy of 1.0 and the model is overfitting significantly as indicated by the perfect train accuracy and considerably lower test accuracy.
4. SVM: The train and test accuracies are quite close, indicating good generalization. The main issue I see with this model is train time. It took significantly longer than the other models.



## Model Evaluation

## Conclusion 

## Next Steps
