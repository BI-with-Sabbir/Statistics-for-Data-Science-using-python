# 📈 Regression & Correlation Analysis on California Housing Data

This project is part of a **Data Science and Statistics (DSA)** learning module, designed to help students understand key statistical concepts such as **correlation**, **regression**, **causality**, and **probability distributions**. It uses the **California Housing Dataset** and walks through exploratory analysis, correlation matrix, and multiple linear regression.

---

## 🎯 Objectives

- Understand **causality** and the difference between **correlation** and **regression**
- Use **descriptive statistics** to interpret dataset features
- Build a **Multiple Linear Regression** model to analyze relationships
- Explore and visualize **correlation** and interpret statistical output
- Understand which predictors are **statistically significant**

---

## 🧰 Libraries Used

```python
import pandas as pd
import numpy as np
import statsmodels.api as sm
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.datasets import fetch_california_housing
```

---

## 🏡 Dataset: California Housing

The dataset contains information on:
- Median income
- Average number of rooms and bedrooms
- Population
- House age
- Location (latitude and longitude)

```python
housing = fetch_california_housing()
df = pd.DataFrame(housing.data, columns=housing.feature_names)
df['MEDV'] = housing.target
```

---

## 📊 Causality, Correlation, and Regression

### 🔗 Causality
Causality implies a direct cause-and-effect relationship between two variables. Not all correlations indicate causation—external factors may drive both variables.

### 📉 Correlation vs. Regression
- **Correlation**: Measures strength and direction of a relationship (-1 to +1)
- **Regression**: Models relationships and makes predictions

Regression gives more context about the **impact** and **predictive power** of variables.

---

## 🔍 Exploratory Data Analysis

```python
df.info()
df.describe()
```

Sample preview:
```
   MedInc  HouseAge  AveRooms  AveBedrms  Population  AveOccup  Latitude  Longitude  MEDV
0  8.3252      41.0   6.984127   1.023810       322.0   2.555556     37.88   -122.23  4.526
1  8.3014      21.0   6.238137   0.971880      2401.0   2.109842     37.86   -122.22  3.585
```

---

## 📈 Multiple Linear Regression

We’ll model how independent variables influence median house value.

```python
X = df[['MedInc', 'Population', 'HouseAge', 'AveBedrms']]
y = df['MEDV']
X = sm.add_constant(X)
model = sm.OLS(y, X).fit()
print(model.summary())
```

### 🔍 Key Results:
- **R-squared**: 0.510 — 51% of variance in house prices explained
- **MedInc** has a strong, significant positive relationship (p < 0.05)
- **HouseAge** and **Population** also positively contribute

---

## 📋 Interpretation of Regression Output

- **R-squared**: Explains model's effectiveness (closer to 1 is better)
- **F-statistic**: Tests overall model significance (low p = good)
- **Coefficients**: Shows how one unit change in predictor affects MEDV
- **P>|t|**: Indicates statistical significance (< 0.05 is significant)

---

## 🧠 Important Notes

- **Causality ≠ Correlation**: A strong correlation doesn’t confirm causation
- **Multicollinearity**: Large condition number may indicate overlapping predictors
- **Assumptions**: Check linearity, normality, and independence of residuals
- **Outliers**: Can distort model accuracy

---

## 📉 Correlation Analysis

```python
correlation_matrix = df.corr()
print(correlation_matrix['MEDV'])
```

### Key Insights:
- **MedInc** has the highest positive correlation with **MEDV** (0.69)
- Weak correlations from **Population**, **AveOccup**, and **Latitude**

```python
plt.figure(figsize=(12, 10))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', fmt=".2f")
plt.title('Correlation Matrix Heatmap')
plt.show()
```

---

## 📚 Educational Value

This notebook helps learners understand:
- How to run and interpret regression models
- How correlation differs from regression
- Real-world application of linear modeling in housing price prediction
- The importance of statistical assumptions and significance testing

---

## ✅ Conclusion

By completing this project, students gain hands-on experience in:
- Regression modeling with real-world data
- Analyzing feature importance and significance
- Visualizing and interpreting correlation matrices
- Understanding statistical summaries for practical decision-making

This foundational knowledge prepares students for more advanced predictive analytics and data modeling tasks.

---

> 🚀 *Use this project as a starter to build deeper projects around price prediction, real estate analytics, and causal inference modeling.*
