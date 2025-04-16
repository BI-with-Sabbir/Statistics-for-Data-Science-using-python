# 📊 Amazon Sales Data Analysis - Descriptive Statistics

This project performs a comprehensive **descriptive statistical analysis** on Amazon sales data. It explores measures of **central tendency**, **dispersion**, and **shape characteristics** to understand patterns and variability in sales figures such as order amounts and quantities. The project also includes visualizations and statistical techniques to examine the distribution and behavior of key numerical features.

---

## 🔍 Objectives

- Understand the distribution and central location of numeric sales data
- Analyze the skewness and kurtosis to detect asymmetry and tail behavior
- Identify outliers that could affect business insights or model performance
- Visualize the spread and shape of the "Amount" and "Qty" variables
- Practice statistical transformations to normalize skewed data

---

## 📁 Dataset Overview

- Dataset: [Amazon Sale Report.csv](https://www.kaggle.com/code/youssefelbadry10/e-commerce-sales-eda/input)

> The dataset reflects transaction-level records from Amazon including product-wise sales, quantities, and geographic spread.

---

## 🧰 Libraries Used

```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from scipy import stats
import statsmodels.api as sm
```

---

## 📈 Exploratory Data Analysis (EDA)

### 1. Central Tendency Measures
- **Mean, Median, Mode** of `Amount` and `Qty` calculated
- Helped understand typical order behavior

### 2. Dispersion Measures
- **Range, Standard Deviation, Variance**
- Boxplot and IQR used to detect spread and potential outliers

### 3. Shape Measures
- **Skewness & Kurtosis** measured using `scipy.stats`
- Histogram and density plots created for visual confirmation

### 4. Outlier Detection
- Used **boxplots** and Z-score method
- Identified extreme values impacting average metrics

---

## 🧪 Data Transformation

To correct for right-skewed distributions:
- Applied **log transformation** on the `Amount` column
- Improved symmetry and normality of the distribution
- Compared original vs transformed distributions side-by-side

---

## 📊 Visualizations

Key plots used:
- Histograms with KDE for distribution analysis

![image](https://github.com/user-attachments/assets/35071a07-3da2-461e-9027-698fb15f9d18)

- Boxplots to detect outliers

![image](https://github.com/user-attachments/assets/f8fdd6ef-c6ab-4a70-938e-9d4cf59dbb8b)

- Q-Q Plots to check normality

- Pairplots to examine inter-variable relationships

> Visualizations provided crucial insight into the asymmetry and variability of the sales figures.

---

## 💡 Key Findings

- The **Amount** variable is positively skewed with some extreme order values
- **Log transformation** made the data more symmetric, ideal for further analysis or modeling
- There are a few high-value outliers, possibly large bulk orders or pricing anomalies
- Most transactions fall under low to mid-range values, showing a long-tail distribution

---

## 📌 Business Insights

- Skewed sales data suggest pricing or quantity bundling strategies might be reviewed
- Outliers, while rare, might indicate valuable customers or errors
- Normalizing skewed variables improves accuracy in forecasting models and trend detection
- Understanding the distribution helps in segmenting customer behavior and managing stock

---

## 🚀 Future Enhancements

- Extend to **time series analysis** of sales over months
- Analyze **category-wise** contribution to revenue
- Integrate **customer segmentation** based on purchase behavior
- Use **correlation analysis** to identify dependencies between sales features

---

## 📂 Project Structure

```
📁 amazon-sales-analysis/
│
├── 📄 Amazon_Descriptive_Statistics.ipynb     # Jupyter Notebook for analysis
├── 📄 README.md                               # Project overview and documentation
├── 📁 data/
│   └── amazon_sales_data.csv                 # Raw dataset
├── 📁 images/ (optional)
│   └── histogram_amount.png                  # Visuals used in README
```

---

## 📬 Need Python code: [click here]()
