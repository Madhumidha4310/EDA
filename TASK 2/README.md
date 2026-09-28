# Superstore Sales & Profit Analysis

## 📌 Project Overview

This project performs **sales and profit analysis** on a Superstore dataset using Python. The notebook explores sales performance across different categories, analyzes profit distribution, studies the relationship between discount and profit, and examines correlations between numerical variables.

The project focuses mainly on **Exploratory Data Analysis (EDA)** and data visualization.

---

## 🎯 Objectives

* Load and explore the Superstore dataset.
* Understand the structure and statistical summary of the data.
* Analyze total sales by category.
* Study the distribution of profit.
* Examine the relationship between discount and profit.
* Calculate correlations between numerical variables.
* Visualize the correlation matrix using a heatmap.
* Find the maximum profit for each category.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Jupyter Notebook**

---

## 📂 Dataset

The project uses the following dataset:

```text
superstore_raw.csv
```

The dataset is loaded using Pandas:

```python
df = pd.read_csv('/content/superstore_raw.csv')
```

The analysis uses columns such as:

* `Category`
* `Sales`
* `Profit`
* `Discount`

and other numerical columns available in the dataset.

---

## 🔍 Project Workflow

### 1. Import Libraries

The following libraries are imported:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. Load the Dataset

The Superstore dataset is loaded into a Pandas DataFrame.

```python
df = pd.read_csv('/content/superstore_raw.csv')
```

### 3. Dataset Exploration

The notebook explores the dataset using:

```python
df.head()
df.info()
df.describe()
df.shape
```

These commands help understand the dataset structure, data types, statistical summary, and number of rows and columns.

---

## 📊 Analysis Performed

### 1. Total Sales by Category

The project calculates total sales for each product category and visualizes the results using a bar chart.

```python
df.groupby("Category")["Sales"].sum().plot(kind="bar")
```

**Visualization:**

* X-axis → Category
* Y-axis → Total Sales

This helps compare sales performance across different categories.

---

### 2. Profit Distribution

A box plot is used to understand the distribution of profit values.

```python
plt.boxplot(df["Profit"])
```

The visualization helps observe the spread of profit and identify possible extreme values.

---

### 3. Discount vs Profit

A scatter plot is created to study the relationship between discount and profit.

```python
plt.scatter(df["Discount"], df["Profit"])
```

**Visualization:**

* X-axis → Discount
* Y-axis → Profit

This helps examine how profit values vary at different discount levels.

---

### 4. Correlation Analysis

The project calculates correlations between numerical columns.

```python
df.select_dtypes(include="number").corr()
```

Correlation analysis helps identify relationships between numerical variables in the dataset.

---

### 5. Correlation Heatmap

A Seaborn heatmap is used to visualize the correlation matrix.

```python
sns.heatmap(
    df.select_dtypes(include="number").corr(),
    annot=True,
    cmap="coolwarm"
)
```

The heatmap provides a visual representation of the relationships between numerical variables.

---

### 6. Maximum Profit by Category

The maximum profit for each category is calculated using:

```python
df.groupby("Category")["Profit"].max()
```

This provides the highest recorded profit value for each product category.

---

## 📈 Visualizations

The notebook includes the following visualizations:

1. **Total Sales by Category** — Bar Chart
2. **Profit Distribution** — Box Plot
3. **Discount vs Profit** — Scatter Plot
4. **Numerical Correlation Matrix** — Heatmap

---

## 📁 Project Structure

```text
Superstore-Sales-Profit-Analysis/
│
├── superstore_raw.csv
├── Superstore_Sales_Profit_Analysis.ipynb
└── README.md
```

> Rename the notebook file according to the actual filename you use in your GitHub repository.

---

## 🚀 How to Run the Project

### Step 1: Clone the Repository

```bash
git clone <your-repository-url>
```

### Step 2: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Step 3: Open the Notebook

```bash
jupyter notebook
```

### Step 4: Add the Dataset

Make sure `superstore_raw.csv` is available in the expected location.

### Step 5: Run the Notebook

Run the cells sequentially to perform the complete analysis.

---

## 🧠 Skills Demonstrated

* Python Programming
* Pandas Data Analysis
* NumPy
* Exploratory Data Analysis (EDA)
* Data Grouping and Aggregation
* Statistical Summary
* Correlation Analysis
* Data Visualization
* Matplotlib
* Seaborn
* Business Data Analysis

---

## 👩‍💻 Author

**Madhumidha**

BCA Student | Aspiring Data Analyst | Full Stack & Machine Learning Enthusiast
