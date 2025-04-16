# 🧪 Sampling Techniques with Heart Disease Dataset

This project demonstrates key sampling techniques using a real-world heart disease dataset. Sampling helps us draw meaningful insights from data when it's not feasible to analyze the entire population.

---

## 📌 What is Sampling?

A **sampling technique** is a method used to select a representative subset (sample) from a larger population. It allows us to make statistical inferences while saving time, cost, and effort.

---

## 🌟 Why Use Sampling?

- ✅ **Cost-effective** – Less expensive than analyzing the full population.
- ⚡ **Efficient** – Faster data processing and insights.
- 🔧 **Practical** – Often impossible to access the entire population.

---

## 📊 Sampling Techniques Covered

### 1. 🔹 Simple Random Sampling

**Definition**: Every individual has an equal chance of being selected.

```python
sample_df = df.sample(n=200, random_state=100)
```

✔️ Randomly selects 200 patients from the dataset.

---

### 2. 🔹 Stratified Sampling

**Definition**: The population is divided into subgroups (strata), and samples are taken from each group.

**Example**: Sampling based on age group.

```python
bins = [0, 20, 30, 40, 50, 60, 70, 80]
labels = ['0-19', '20-29', '30-39', '40-49', '50-59', '60-69', '70+']
df['age_group'] = pd.cut(df['age'], bins=bins, labels=labels)

stratified_sample = df.groupby('age_group', group_keys=False).apply(
    lambda x: x.sample(min(len(x), 10))
)
```

✔️ Ensures balanced representation across age groups.

---

### 3. 🔹 Cluster Sampling

**Definition**: The population is split into clusters (e.g., hospitals), and entire clusters are randomly selected.

**Note**: This dataset lacks a cluster column (like hospital ID), so this is only described conceptually.

✔️ Useful when working with location-based or institutional data.

---

### 4. 🔹 Systematic Sampling

**Definition**: Selects every _k<sup>th</sup>_ individual from an ordered dataset.

```python
systematic_sample = df.iloc[::5]
```

✔️ Easy to apply, assuming random order.

---

## 🧾 Dataset Used

🔗 [Dataset Link](https://github.com/BI-with-Sabbir/Statistics-for-Data-Science-using-python/blob/main/Sampling%20Methods%20in%20Statistics/heart.csv)

The dataset includes clinical information:

- **Features**: Age, sex, cholesterol, chest pain, heart rate, etc.
- **Target**: Heart disease presence (`target`)

```python
df = pd.read_csv('heart.csv')
df.head()
```

---

## 📂 Project Structure

```
📁 Sampling-Techniques-Heart-Disease
├── heart.csv                   # Dataset
├── sampling_code.ipynb         # Jupyter Notebook with code examples
└── README.md                   # Documentation
```

---

## 🎯 Learning Outcomes

- Apply various sampling techniques
- Understand when to use each method
- Explore how sample size and method affect representativeness

---

## 🔍 Sample Output Preview

| age | sex | trestbps | chol | target | age_group |
|-----|-----|----------|------|--------|-----------|
| 52  | 1   | 125      | 212  | 0      | 50–59     |
| 58  | 0   | 100      | 248  | 1      | 50–59     |
| 71  | 0   | 112      | 149  | 1      | 70+       |
| 34  | 0   | 118      | 210  | 1      | 30–39     |

---

## 💡 Final Thoughts

> _“Sampling is the bridge between the real world and data-driven decisions.”_  
> — Your Data Guide

---

## 📬 Additional Resources

📌 [Python Code Notebook](https://github.com/BI-with-Sabbir/Statistics-for-Data-Science-using-python/blob/main/Sampling%20Methods%20in%20Statistics/Sampling%20Methods%20in%20Statistics.ipynb)

