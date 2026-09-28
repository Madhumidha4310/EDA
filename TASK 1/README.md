# 🛒 E-commerce Order Data Analysis & Data Cleaning

## 📌 Project Overview

This project focuses on **data cleaning and feature engineering of an E-commerce Order dataset using Python and Pandas**.

The notebook loads an e-commerce order dataset, examines its structure, identifies missing values, handles missing information, checks for duplicate records, and creates new calculated columns related to pricing and discounts.

The project demonstrates basic data preprocessing techniques that can be used before performing further data analysis or building machine learning models.

## 🎯 Objectives

The main objectives of this project are:

* Load the e-commerce order dataset.
* Inspect the dataset structure.
* Understand the dataset dimensions and columns.
* Generate descriptive statistics.
* Identify missing values.
* Handle missing values in important columns.
* Check duplicate records.
* Remove duplicate records.
* Create calculated price-related features.
* Calculate discount amounts.
* Calculate final order amounts.

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Jupyter Notebook**

## 📂 Dataset

The notebook uses the following dataset:

```text
Ecommerce_Order_Test_Dataset.csv
```

The dataset contains e-commerce order information, including customer details, location, ratings, payment mode, quantity, unit price, and discount information.

## 🔍 Project Workflow

The notebook follows these main steps:

```text
Load Dataset
     ↓
Inspect Dataset
     ↓
Check Missing Values
     ↓
Handle Missing Values
     ↓
Check Duplicate Records
     ↓
Remove Duplicates
     ↓
Create New Features
     ↓
Calculate Final Amount
```

## 1. 📥 Importing Libraries

The notebook imports NumPy and Pandas:

```python
import numpy as np
import pandas as pd
```

## 2. 📊 Loading the Dataset

The dataset is loaded using Pandas:

```python
df = pd.read_csv("/content/Ecommerce_Order_Test_Dataset.csv")
```

The first few records are viewed using:

```python
df.head()
```

## 3. 📐 Dataset Inspection

The notebook examines the dataset using:

```python
df.shape
df.columns
df.info()
df.describe()
```

These operations are used to understand:

* Number of rows and columns
* Column names
* Data types
* Statistical summary of numerical columns

## 4. 🧹 Missing Value Analysis

Missing values are checked using:

```python
df.isnull().sum()
```

The notebook handles missing values in several columns.

### City

Missing city values are replaced with:

```text
Unknown
```

```python
df["City"] = df["City"].fillna("Unknown")
```

### Customer Name

Missing customer names are replaced with:

```text
Unknown
```

```python
df["Customer_Name"] = df["Customer_Name"].fillna("Unknown")
```

### Rating

Missing ratings are replaced using the **mean rating**:

```python
mean = df["Rating"].mean()
df["Rating"] = df["Rating"].fillna(mean)
```

This uses the average rating to fill missing rating values.

### Payment Mode

Missing payment-mode values are replaced with:

```text
Unknown
```

```python
df["Payment_Mode"] = df["Payment_Mode"].fillna("Unknown")
```

## 5. 🔁 Duplicate Record Checking

The notebook checks for duplicate records using:

```python
df.duplicated()
```

Duplicate records are then removed using:

```python
df.drop_duplicates()
```

This helps reduce repeated records in the dataset.

## 6. 🧮 Feature Engineering

The notebook creates additional columns to calculate order-level pricing.

### Total Price

The `Total_Price` column is calculated using:

```python
df["Total_Price"] = df["Quality"] * df["Unit_Price"]
```

The calculation is:

```text
Total Price = Quantity × Unit Price
```

### Discount Amount

The `Discount_Amount` column is calculated as:

```python
df["Discount_Amount"] = df["Total_Price"] * df["Discount"]
```

The calculation is:

```text
Discount Amount = Total Price × Discount
```

### Final Amount

The final amount after applying the discount is calculated using:

```python
df["Final_Amount"] = df["Total_Price"] - df["Discount_Amount"]
```

The calculation is:

```text
Final Amount = Total Price − Discount Amount
```

## 📊 Features Created

The notebook creates the following calculated columns:

| Feature           | Calculation                     |
| ----------------- | ------------------------------- |
| `Total_Price`     | `Quality × Unit_Price`          |
| `Discount_Amount` | `Total_Price × Discount`        |
| `Final_Amount`    | `Total_Price − Discount_Amount` |

## 📌 Data Cleaning Techniques Used

The project demonstrates the following data-cleaning techniques:

* Missing-value detection
* Missing-value replacement
* Mean-based imputation
* Categorical value replacement
* Duplicate detection
* Duplicate removal
* Dataset inspection
* Data transformation

## 💡 Key Analysis Areas

The notebook focuses on:

* E-commerce order data
* Customer information
* City information
* Customer ratings
* Payment modes
* Quantity
* Unit price
* Discounts
* Total price
* Discount amount
* Final amount

## 📁 Project Structure

```text
Ecommerce-Order-Data-Cleaning/
│
├── EDA 1.ipynb
├── Ecommerce_Order_Test_Dataset.csv
└── README.md
```

## 🚀 How to Run the Project

### Step 1: Install Required Libraries

```bash
pip install pandas numpy jupyter
```

### Step 2: Open Jupyter Notebook

```bash
jupyter notebook
```

### Step 3: Add the Dataset

Place the following dataset in the project directory:

```text
Ecommerce_Order_Test_Dataset.csv
```

Update the file path in the notebook if necessary:

```python
df = pd.read_csv("Ecommerce_Order_Test_Dataset.csv")
```

### Step 4: Run the Notebook

Run the cells sequentially to perform:

1. Dataset loading
2. Data inspection
3. Missing-value analysis
4. Missing-value handling
5. Duplicate checking
6. Duplicate removal
7. Feature engineering
8. Price and discount calculations

## 🎓 Skills Demonstrated

This project demonstrates practical knowledge of:

* Python
* Pandas
* NumPy
* Data Cleaning
* Data Preprocessing
* Missing Value Handling
* Mean Imputation
* Duplicate Detection
* Duplicate Removal
* Feature Engineering
* Basic E-commerce Data Analysis

## 👩‍💻 Author

**Madhumidha**
