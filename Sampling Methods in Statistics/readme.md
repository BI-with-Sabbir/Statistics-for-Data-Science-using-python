# 🧪 Sampling Techniques with Heart Disease Dataset

This project demonstrates several key sampling techniques using a real-world heart disease dataset. Sampling is an essential part of data science, allowing us to work with a subset of the data when analyzing an entire population is impractical or impossible.

---

## 📌 What is Sampling?

A **sampling technique** is a method used to select a representative subset (sample) from a larger population to make statistical inferences. It helps reduce cost, time, and complexity in data collection and analysis.

---

## 🌟 Why Use Sampling?

- ✅ **Cost-effective** – Less expensive than studying the entire population.
- ⚡ **Efficient** – Quicker data processing and analysis.
- 🔧 **Practical** – Sometimes the entire population is inaccessible.

---

## 📊 Sampling Techniques Covered

### 1. Simple Random Sampling

**Definition**: Each individual in the population has an equal chance of being selected.

```python
sample_df = df.sample(n=200, random_state=100)
```

✔️ 200 patients randomly selected from the dataset.

---

### 2. Stratified Sampling

**Definition**: The population is divided into subgroups (strata), and random samples are taken from each stratum.

**Example**: Sampling patients based on age group (e.g., 20–29, 30–39, etc.)

```python
bins = [0, 20, 30, 40, 50, 60, 70, 80]
labels = ['0-19', '20-29', '30-39', '40-49', '50-59', '60-69', '70+']
df['age_group'] = pd.cut(df['age'], bins=bins, labels=labels)

stratified_sample = df.groupby('age_group', group_keys=False).apply(
    lambda x: x.sample(min(len(x), 10))
)
```

✔️ Ensures each age group is represented fairly.

---

### 3. Cluster Sampling

**Definition**: The population is divided into clusters (e.g., hospitals), and entire clusters are randomly selected.

**Note**: This dataset doesn't include a 'cluster' column (e.g., hospital ID), so this is only described conceptually.

✔️ Useful when the population is grouped geographically or institutionally.

---

### 4. Systematic Sampling

**Definition**: Selects every _k<sup>th</sup>_ individual (e.g., every 5th patient).

```python
systematic_sample = df.iloc[::5]
```

✔️ Fast and simple to implement, assuming no hidden patterns in data order.

---

## 🥪 Dataset Used
[Click here to see the data](https://github.com/BI-with-Sabbir/Statistics-for-Data-Science-using-python/blob/main/Sampling%20Methods%20in%20Statistics/heart.csv)
The dataset contains clinical data on heart disease patients:

- **Features**: Age, sex, chest pain (`cp`), cholesterol (`chol`), blood pressure (`trestbps`), heart rate (`thalach`), and more.
- **Target**: Presence of heart disease (`target`)

```python
df = pd.read_csv('heart.csv')
df.head()
```

---

## 📁 Project Structure

```
📆 Sampling-Techniques-Heart-Disease
├── heart.csv                  # Dataset
├── sampling_code.ipynb        # Code demonstrating sampling methods
└── README.md                  # Documentation (you are here)
```

---

## 📒 Learning Outcomes

- Understand and apply different sampling techniques
- Learn how sampling affects model performance and data representativeness
- Practice pandas operations for real-world data sampling

---

## 📈 Sample Output Preview

| age | sex | trestbps | chol | target | age_group |
|-----|-----|----------|------|--------|-----------|
| 52  | 1   | 125      | 212  | 0      | 50–59     |
| 58  | 0   | 100      | 248  | 1      | 50–59     |
| 71  | 0   | 112      | 149  | 1      | 70+       |
| 34  | 0   | 118      | 210  | 1      | 30–39     |

---


---

## 🧠 Final Thought

> _“Sampling is the bridge between the real world and data-driven decisions.”_  
> — Your Data Guide

---

## 📬Need python code: [Click here](https://github.com/BI-with-Sabbir/Statistics-for-Data-Science-using-python/blob/main/Sampling%20Methods%20in%20Statistics/Sampling%20Methods%20in%20Statistics.ipynb)



