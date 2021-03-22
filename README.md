# heart-disease-data
Subject of the project: Predicting Heart Disease Using Machine Learning Algorithms
Classification project
What did we do?
1- Data analysis was used to examine trends and correlations in the data. It was determined which features are most important in the diagnosis of heart disease.
2-Model part: Multiple classification models (Logistic Regression, K-NN (k-Nearest Neighbors), SVM (Support Vector Machine), Naives Bayes Classifier, Decision Trees, Random Forest.) The highest accuracy rate was used.

DATA: a dataset from the kaggle. Our data set includes the data of 303 healthy and patients diagnosed with a heart attack.
The data set has 303 rows, 14 columns, and 14 columns with 13 attributes and 1 output.
There are 3 types of data in the data set.

Continous: measurable quantitative data (numerical): age, trestbps (resting blood pressure), cholesterol, thalac (max pulse), oldpeak (exercise-induced sp depression),
Ordinal: categorical variables in order (0,1,2,3): cp (severity of chest pain), restecg (ecg results), slope (slope of the st segment), ca (number of major vessels), thal (stress state)
Binary: ancestors with two possible states (0,1): Gender, fbs (fasting blood pressure, 0 = 120 and less than 120, 1 = greater than 120), Exang (exercise induced angina 0 = not present 1 = present),


Exployarty data analysis
Correlation matrix purpose: shows the strength of the relationship between dependent variables and independent variables.
The value of numbers: the strength of the relationship.
Numbers in the correlation matrix take values ​​between -1 and +1.
The closer the number gets to 0 from a positive or negative direction, the relationship between it and the output decreases, the less the condition of having a heart disease.
The further the number moves away from 0 (for both directions), the greater the relationship between it and output.

The sign of the number indicates the type of relationship.
What do the signs mean?
Negative correlation: if one of the variables increases while the other is decreasing.
Ex: (- 0.39) CA (as the number of major vessels increases) ↑ heart disease status ↓
Positive correlation: the state of the variables being thrown together. Correct proportion
Ex: (0.43) CP (as the severity of pain increases) ↑ heart disease status ↓



Machine Learning + Predictive Analytics
Assignments: 13 features, 1 result
Training set and test set separation: 20% test set
Normalization, for more "comfortable" operation of the models


Modeling / Training

Model trials, 6 models
Logistic regression
Linear regression gives results between (-∞, + ∞), we can solve the classification problem (sigmoid) by reducing this result between (0,1) with logistic regression. If the result for the given properties is 0.8, the probability of being included in the class defined by 1 is 80%.
“Parameters in logistic regression are calculated with the Maximum Likelihood (MLE) method. The purpose of the MLE method is to select the best parameters from the infinite parameter pool that maximizes the probability of seeing the data set. ”
K-NN (K-Nearest Neighbors)
Model 2 interprets the given features according to the features with the highest resemblance rate in the training set.
SVM (Support Vector Machine)
Support Vector Machines draw linear or nonlinear auxiliary vectors to distinguish sets included in 0 and 1 values ​​by interpreting the inputs on the graph. The remainder of the vector drawn (right / left / top / bottom / inner / outer, etc.) is 0, and 1 on the other side.
Naives Bayes Classifier
In this model, each feature is considered independent of each other.
P (A ┤ | B) = (P (B ┤ | A). P (A)) / (P (B))
Finding the probability of results. The average probability is obtained by calculating the results one by one for each data.
Decision Trees
The Decision Trees model creates a tree by repeatedly separating the study areas, minimizing the entropy (impurity measure). It also uses this tree when making the decision to classify the newly entered value.
"Splitting (efficiently) based on knowledge acquisition is the key to the decision tree model."
It is a structure that is used by dividing large amounts of records into very small groups of records by applying simple decision-making steps.



Random Forest
Random (Incidental) Forest model, collective / community learning method. The model generates random decision trees from subsets of features in the training set (subsets may overlap). He uses the votes he gets from the trees he has created before making the final decision. The concept of weight can be used in voting. With this concept, low weight is given for the votes of trees with high error rate and high weight is given for trees with low error rate and its effect on the result is determined.
According to these models, the best result we have belongs to the Random (Random) Forest model.
Making the Confusion Matrix
Error / Confusion Matrix
[■ (X1 & Y1 @ Y2 & X2)]
X1 - Real number 1
Y1 - the number of 1 guesses made wrong
Y2 the number of 0 guesses made wrong
X2 - Real 0 number
Accuracy = (X1 + X2) / (X1 + X2 + Y1 + Y2)
Our error matrix:
[■ (21 & 9 @ 3 & 28)]
Accuracy = (21 + 28) / (21 + 28 + 9 + 3) = 49 / 61≌0.80
Importance of Features
