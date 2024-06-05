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

The Dataset did not have any missing values but did contain 28 duplicates. Those values were dropped. The categorical columns that were encoded using One Hot Encoder.

## Modeling

The four models chosen are:
1. Logistic Regression
2. K Nearest Neighbor
3. Decision Trees
4. Support Vector Machines

### Metrics Used for Evaluation:

1. Accuracy:

Importance: Accuracy gives a general idea of how many predictions your model got right out of all predictions. It is important to know that marketing efforts are not wasted and is a way to predict how many subscriptions you can expect.

2. Precision:

Importance: Precision indicates how many of the clients predicted to subscribe actually did subscribe. High precision means that when the model predicts a client will subscribe, it is usually correct.
Use Case: In marketing, a high precision rate is important to ensure that resources are not wasted on clients who are unlikely to subscribe.

3. Recall (Sensitivity or True Positive Rate):

Importance: Recall tells you how many of the actual subscribers were correctly identified by the model. It’s crucial when missing a potential subscriber is costly.
High recall ensures that you are not missing out on potential subscribers, maximizing the reach of your campaign. If recall is low, you miss out on many clients who would have subscribed if targeted. This reduces potential revenue.

4. F1 Score:

Importance: The F1 score balances precision and recall, giving a single metric that considers both false positives and false negatives.Balancing precision and recall ensures an effective overall strategy, avoiding the pitfalls of focusing too heavily on one at the expense of the other.

5. ROC-AUC Score:

Importance: The ROC-AUC score evaluates the model’s ability to distinguish between subscribers and non-subscribers across various threshold settings. It’s a robust metric for binary classification problems.

6. Confusion Matrix:

Importance: The confusion matrix provides a detailed breakdown of true positives, true negatives, false positives, and false negatives.  Also gives you detailed insights into where your model is making errors help refine marketing strategies and improve overall targeting accuracy.


### Analysis of Default Models:

1. Logistic Regression: The difference between train and test accuracy is small, which is a good thing and indicates good generalization.
2. KNN: There's a moderate drop in test accuracy compared to train accuracy, suggesting some overfitting.
3. Decision Tree: Decisions Treee has a perfect Train accuracy of 1.0 and the model is overfitting significantly as indicated by the perfect train accuracy and considerably lower test accuracy.
4. SVM: The train and test accuracies are quite close, indicating good generalization. The main issue I see with this model is train time. It took significantly longer than the other models.

<img width="581" alt="Screenshot 2024-06-05 at 9 12 19 AM" src="https://github.com/anjana250/comparing_classifiers/assets/15185723/32148ed2-10f3-40e0-a090-2a676bee12bb">


While the initial values are okay- there is a lot of room for improvement. There is even some evidence of overfitting with Decision Tree. In order to fix this, fine tuning of hyperparamers was done.

### Analysis after Fine Tuning Hyperparameters and Conducting Grid Search
1. Logistic Regression:

![Logistic Regression_comparison](https://github.com/anjana250/comparing_classifiers/assets/15185723/96b59491-a09c-44fb-9bbd-fa29483ba52c)

Train/Test Accuracy: The model performs well on both training and test data, indicating a good fit without overfitting.
Precision and Recall: Both are high and balanced, indicating the model is good at identifying true positives and has a low false positive rate.
F1 Score: High and close to Precision and Recall, reinforcing the balance between them.
ROC AUC: High value, indicating a good ability to discriminate between classes.


2. KNN:

![KNN_comparison](https://github.com/anjana250/comparing_classifiers/assets/15185723/a4c5e9f4-bc87-4550-b208-3720586b1a9d)


Train/Test Accuracy: Perfect training accuracy suggests overfitting, as the test accuracy is lower.
Precision and Recall: Both are good but slightly lower than Logistic Regression.
F1 Score: Reflects the balance between precision and recall but is slightly lower.
ROC AUC: Significantly lower, indicating poorer performance in distinguishing between classes compared to other models.

3. Decision Tree:

![Decision Tree_comparison](https://github.com/anjana250/comparing_classifiers/assets/15185723/4e3cdc0c-1aa1-4751-9116-5583510d9d1e)


Train/Test Accuracy: The model generalizes well, with only a slight drop in accuracy from training to test data.
Precision and Recall: Both are high and balanced, similar to Logistic Regression.
F1 Score: High, indicating a good balance between precision and recall.
ROC AUC: High, indicating good discrimination between classes.

4. SVM:

![SVM_comparison](https://github.com/anjana250/comparing_classifiers/assets/15185723/7ea5b72d-20b2-41bd-88d6-5d5e5aec1c78)

Train/Test Accuracy: Slight drop from training to test accuracy, indicating decent generalization.
Precision and Recall: Both are good but slightly lower than Decision Tree and Logistic Regression.
F1 Score: Slightly lower, indicating a minor imbalance between precision and recall.
ROC AUC: High, suggesting good discriminatory power.

<img width="581" alt="Screenshot 2024-06-05 at 9 18 41 AM" src="https://github.com/anjana250/comparing_classifiers/assets/15185723/12090f26-3e84-4da6-b9f2-f35b97fd421b">

The graphs displaying this information:




## Conclusion 
The Models that did the best were Logistic Regression and Decision Tree.
## Next Steps

Further improvements can be made to the hyperparameters and more time can be spent tuning them further. Other models such as Random Forest can also be tried to see if they have better results.
