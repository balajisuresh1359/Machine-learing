Logistic Regression: Predicts probabilities for binary outcomes, like whether an email is spam or not.

#### **What is this?**

Logistic Regression is a statistical method used for binary classification tasks. It models the probability that a given input belongs to a particular class (usually 0 or 1) using the logistic (sigmoid) function. Unlike Linear Regression, which predicts continuous values, Logistic Regression predicts discrete outcomes (e.g., yes/no, true/false).


#### **When to use?**

Use Logistic Regression when:

- You need to model the probability of a binary outcome.
- The relationship between the independent variables (features) and the dependent variable (outcome) is approximately linear, but the outcome is binary.

#### **Real-Life Problem Statement**

Imagine you're working on a loan approval system for a bank. You need to predict whether a loan applicant will default on their loan based on features such as income, credit score, and employment status. The outcome is binary: either the applicant defaults (1) or doesn't default (0).


import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, classification_report

# Example data: assume we have a dataset with loan information
data = pd.DataFrame({
    'income': [45000, 54000, 32000, 61000, 70000, 43000, 52000, 58000],
    'credit_score': [620, 680, 580, 710, 720, 630, 690, 710],
    'loan_default': [0, 0, 1, 0, 0, 1, 0, 0]  # Target variable (0 = no default, 1 = default)
})

# Features and target variable
X = data['income', 'credit_score']
y = data['loan_default']

# Split data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# Create a logistic regression model
model = LogisticRegression()

# Train the model
model.fit(X_train, y_train)

# Make predictions
y_pred = model.predict(X_test)

# Evaluate the model
print("Accuracy:", accuracy_score(y_test, y_pred))
print("\nClassification Report:\n", classification_report(y_test, y_pred))


#continue