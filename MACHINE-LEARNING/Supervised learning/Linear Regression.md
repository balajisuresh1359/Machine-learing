Linear Regression: Predicts a continuous value like price, temperature, etc.

#### **What is this?**

Linear Regression is a statistical method used for predicting continuous outcomes based on one or more input features (independent variables). It assumes a linear relationship between the input features and the target variable.

#### **When to use?**

Use Linear Regression when:

- You need to model the relationship between a continuous dependent variable and one or more independent variables.
- The relationship between the variables is approximately linear.

#### **Real-Life Problem Statement**

Suppose you're working for a real estate company and need to predict the price of houses based on features such as the size of the house, number of bedrooms, and location. The outcome (house price) is continuous.


import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score

# Example data: assume we have a dataset with house information
data = pd.DataFrame({
    'size': [1500, 1600, 1700, 1800, 1900, 2000, 2100, 2200],
    'bedrooms': [3, 3, 3, 4, 4, 4, 5, 5],
    'price': [300000, 320000, 340000, 360000, 380000, 400000, 420000, 440000]  # Target variable
})

# Features and target variable
X = data['size', 'bedrooms']
y = data['price']

# Split data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# Create a linear regression model
model = LinearRegression()

# Train the model
model.fit(X_train, y_train)

# Make predictions
y_pred = model.predict(X_test)

# Evaluate the model
print("Mean Squared Error:", mean_squared_error(y_test, y_pred))
print("R^2 Score:", r2_score(y_test, y_pred))



Y = MX + C  
  
M - SLOPE (WHEN X INCREASE ONE UNIT, THEN Y INCREASE M TIMES OF X.  
C - Y INTERCEPT, LINE CROSSING Y AXIS. IN SIMPLE, VALUE OF Y, WHEN X = 0.  
  
BETWEEN TWO DEPENDANT VARIABLES.  
  
Y - Outcome variable (The variable we are predicting).  
X - Predictor Variable (The variable we are basing our predictions).