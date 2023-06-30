---
layout: post
title: Modeling in Python
date: 2022-10-18 9:00:01 --0000
permalink: /posts/modeling-python/
---

Table of Contents
* TOC
{:toc}

## Using random forest for prediction
This problem uses random forest to predict wine quality.

First, import relevant libraries.
```python
import numpy as np
import pandas as pd
import seaborn as sns
```
Then, import the csv file that contains the data.
```python
df_wine = pd.read_csv("winequality-red.csv", sep=";")
df_wine
```

Next step is to check outliers.
```python
# check for outliers
df_wine.describe()
```

Set up the metric/response variable and features/predictors.
```python
# metric/response variable
labels = np.array(df_wine['quality'])
labels

# features/predictors
features = df_wine.drop(columns="quality")
features.head()

# make features into array to prepare for model-building
features = np.array(features)
features
```

Split the data into training data and test data
```python
from sklearn.model_selection import train_test_split
train_features, test_features, train_labels, test_labels = train_test_split(features, labels, test_size = .25, random_state = 42)
print('Training Features Shape:', train_features.shape)
print('Training Labels Shape:', train_labels.shape)
print('Testing Features Shape:', test_features.shape)
print('Testing Labels Shape:', test_labels.shape)
```

Compute the baseline error.
```python
baseline_preds = [train_labels.mean()] * test_labels.shape[0]
baseline_preds[:5]

baseline_errors = abs(baseline_preds - test_labels)
baseline_errors[:5]

print('Average baseline error: ', round(np.mean(baseline_errors), 2))
```

Random forest regressor.
```python
# Import the model we are using
from sklearn.ensemble import RandomForestRegressor

# Instantiate model with 1000 decision trees
rf = RandomForestRegressor(n_estimators = 1000, random_state = 42)

# Train the model on training data
rf.fit(train_features, train_labels);

# Use the forest's predict method on the test data
predictions = rf.predict(test_features)

# Calculate the absolute errors
errors = abs(predictions - test_labels)

# Print out the mean absolute error (mae)
print('Mean Absolute Error:', round(np.mean(errors), 2), ".")

# Calculate mean absolute percentage error (MAPE)
mape = 100 * (errors / test_labels)
# Calculate and display accuracy
accuracy = 100 - np.mean(mape)
print('Accuracy:', round(accuracy, 2), '%.')
```