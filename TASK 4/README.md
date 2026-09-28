# Shopify Stock Data Analysis

## 📌 Project Overview

This project analyzes **Shopify stock market data** using Python. The analysis focuses on understanding Shopify's historical stock prices, trading volume, moving averages, daily returns, and volatility.

The project uses data from a CSV file named `shopify_stock.csv` and performs data exploration, visualization, and basic financial analysis.

---

## 🎯 Objectives

The main objectives of this project are:

* Analyze Shopify's historical stock prices.
* Understand the **Open, High, Low, and Close** prices.
* Visualize Shopify's stock price movement over time.
* Analyze trading volume.
* Calculate **20-day and 50-day moving averages**.
* Calculate daily stock returns.
* Visualize the distribution of daily returns.
* Analyze stock price volatility using rolling standard deviation.

---

## 🛠️ Technologies Used

* **Python**
* **NumPy**
* **Pandas**
* **Matplotlib**
* **Seaborn**

---

## 📂 Dataset

The project uses:

```text
shopify_stock.csv
```

The dataset contains Shopify stock market information, including:

* `date`
* `open`
* `high`
* `low`
* `close`
* `volume`

The `date` column is converted into a Pandas datetime format before performing the analysis.

---

## 🔍 Project Workflow

### 1. Import Libraries

The following Python libraries are used:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. Load the Dataset

The Shopify stock dataset is loaded using Pandas:

```python
df = pd.read_csv("/content/shopify_stock.csv")
```

The first few rows are displayed using:

```python
df.head()
```

---

### 3. Explore the Dataset

The project examines the dataset using:

```python
df.info()
df.describe()
df.shape
```

These functions help understand:

* Dataset structure
* Data types
* Statistical information
* Number of rows and columns

---

### 4. Date Processing

The `date` column is converted into datetime format:

```python
df["date"] = pd.to_datetime(df["date"], utc=True)
```

The dataset is then sorted by date:

```python
df = df.sort_values("date")
```

---

## 📈 Stock Price Analysis

The project visualizes Shopify's:

* Open price
* High price
* Low price
* Close price

using a line chart.

This helps visualize how Shopify's stock price changed over the available period.

---

## 📊 Trading Volume Analysis

The project also visualizes Shopify's trading volume over time.

```python
plt.plot(df.date, df["volume"])
```

Trading volume represents the number of shares traded during the corresponding period.

---

## 📉 Moving Average Analysis

Two moving averages are calculated:

### 20-Day Moving Average

```python
df["MA20"] = df["close"].rolling(window=20).mean()
```

### 50-Day Moving Average

```python
df["MA50"] = df["close"].rolling(window=50).mean()
```

The project visualizes:

* 20-day moving average
* 50-day moving average
* Closing price

together to observe the stock's price trend.

---

## 💹 Daily Return Analysis

Daily return is calculated using the percentage change in the closing price:

```python
df["Daily_Return"] = df["close"].pct_change()
```

The first observation can contain `NaN` because there is no previous closing price available for comparison.

The missing value is excluded when displaying the daily returns:

```python
df["Daily_Return"].dropna()
```

A histogram with KDE is used to visualize the distribution of Shopify's daily returns.

---

## 📊 Volatility Analysis

The project examines Shopify's stock volatility using standard deviation.

### Rolling Volatility

20-day rolling volatility is calculated as:

```python
df["Rolling_Volatility_20"] = df["Daily_Return"].rolling(window=20).std()
```

100-day rolling volatility is calculated as:

```python
df["Rolling_Volatility_100"] = df["Daily_Return"].rolling(window=100).std()
```

These values are visualized using line charts to observe how Shopify's volatility changes over time.

---

## 📊 Visualizations

The notebook includes visualizations for:

1. Shopify Open, High, Low, and Close prices
2. Shopify trading volume
3. 20-day moving average
4. 50-day moving average
5. Closing price with 20-day and 50-day moving averages
6. Daily return distribution
7. 20-day rolling volatility
8. 100-day rolling volatility

---

## 📁 Project Structure

```text
Shopify-Stock-Analysis/
│
├── shopify_stock.csv
├── Shopify_Stock_Analysis.ipynb
└── README.md
```

---

## 🚀 How to Run the Project

### Step 1: Install Python

Make sure Python is installed on your system.

### Step 2: Install Required Libraries

```bash
pip install numpy pandas matplotlib seaborn jupyter
```

### Step 3: Open Jupyter Notebook

```bash
jupyter notebook
```

### Step 4: Open the Notebook

Open:

```text
Shopify_Stock_Analysis.ipynb
```

### Step 5: Add the Dataset

Place:

```text
shopify_stock.csv
```

in the appropriate project directory and update the file path in the notebook if necessary.

---

## 📌 Key Concepts Used

This project demonstrates practical applications of:

* Data loading
* Data cleaning and preparation
* Exploratory Data Analysis (EDA)
* Time-series data handling
* Data visualization
* Moving averages
* Percentage change
* Daily returns
* Standard deviation
* Rolling volatility

---

## 👩‍💻 Author

**Madhumidha**
