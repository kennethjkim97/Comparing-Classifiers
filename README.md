# Comparing Classifiers

## Overview
The goal of this project is to compare the performance of the classifiers (k-nearest neighbors, logistic regression, decision trees, and support vector machines). A dataset is used related to the marketing of bank products over the telephone.

## Understanding the data, features, and tasks
The dataset comes from the UCI Machine Learning repository (https://archive.ics.uci.edu/ml/datasets/bank+marketing).  The data is from a Portugese banking institution and is a collection of the results of multiple marketing campaigns. After gaining a better understanding of the dataset, we can conclude the data represents a total of 17 marketing campaigns.

After examining the data, there are no strictly missing values such as the data field being completely empty (NaN). Every column contains 41188 non-null data. However, it seems that in place of missing values, the value of "unknown" is assigned, effectiely acting as NaN since these values give no use in interpreting/processing the data.
These rows may need to be removed to utilize full data responsibility. Additionally, we may consider removing the "duration" category as according to the descriptions of the dataset, the "duration" is not known before a call is performed and can be removed to ensure a more realistic predictive model.

### BUSINESS OBJECTIVE
After examining the description and data, the business objective is to use Machine Learning to predict if a client will subscribe to a term deposit for a Portuguese banking institution via direct marketing campaigns (phone calls). By analyzing and interpreting the results of this predictive model, the bank can optimize and tailor its marketing campaign strategies to those who are most likely to subscribe to a term deposit. This can greatly contribute to increased success in gaining subscriptions, and an overall rise in time and cost efficiency.

## Technical Processes

### Engineering Features + Train/Test Split
Now that we understand your business objective, we will build a basic model to get started.  Before we can do this, we must work to encode the data.  Using just the bank information features, we prepare the features and target column for modeling with appropriate encoding and transformations.
Next, we split the preprocessed data into a training and test dataset respectively.

### Scoring a Baseline Model and a Simple Model
Before we build the first model, we establish a baseline performance that our classifier should aim to beat. Utilizing a Dummy Classifier to use a simple baseline to compare with other classifiers, we can come up with a score of accuracy on the test set. In this case, the baseline score is around **89%** (majority of the results are 'no').
Additionally, a basic model built via Logistic Regression also gives an accuracy score of around **89%**.

### Model Comparisons
Now, we aim to compare the performance of the Logistic Regression model to our KNN algorithm, Decision Tree, and SVM models.  Using the default settings for each of the models, we fit and score each.  Also, we compare the fit time of each of the models:
<img width="406" height="128" alt="image" src="https://github.com/user-attachments/assets/e838780f-8a72-4fe7-90b0-792abf9192c7" />

### Improving the Model
Now that we have some basic models on the board, we want to try to improve these.  Below, are a few things to explore in this pursuit:
- Hyperparameter tuning and grid search.  All of our models have additional hyperparameters to tune and explore.  For example the number of neighbors in KNN or the maximum depth of a Decision Tree.  
- Adjust the performance metric
<img width="530" height="133" alt="image" src="https://github.com/user-attachments/assets/50296a73-6357-4743-b5e7-8b56757202ec" />

Keep in mind LinearSVC is utilized for SVM, normal SVC() times out during execution.

## Results

### Decision Trees
Analyzing the results, it seems that **Decision Tree** is the best model to use. With the highest F1 scoreof round 0.38, it would be the best model to find likely subscribers to the term deposit. However, training time is the second worst out of the 4 coming in at around 21 seconds. Additionally, due to the nature of decision trees, it can be unstable with data changes and interpretability is at the mercy of the simplicity of rules.

### Logistic Regression
