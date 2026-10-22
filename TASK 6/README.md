# Healthcare Data Visualization

## Project Overview
This project explores a preprocessed healthcare dataset using Python. It analyzes patient demographics, medical conditions, admission types, hospital billing amounts, insurance providers, monthly admissions, and relationships between selected numeric variables. The results are presented using charts and summary statistics.

---

## Dataset

The script loads a CSV file named healthcare_preprocessed (1).csv.

The code expects columns including:
- Age
- Gender
- Medical_Condition
- Admission_Type
- Billing_Amount
- Insurance_Provider
- Admission_Date
- Length_of_Stay
The script also inspects the dataset's row count, column count, column names, and data types.

Important: The script currently uses the Google Colab path /content/healthcare_preprocessed (1).csv. If running locally, update the path to the location of your CSV file, for example:
```df = pd.read_csv("healthcare_preprocessed (1).csv")```

---

## Technologies and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn

---

## Analysis and Visualizations

### 1. Dataset inspection

- Displays the first rows.
- Prints the number of rows and columns.
- Lists column names and shows data types and non-null counts.

### 2. Patient age analysis

- Histogram of patient ages with a KDE curve.
- Age distribution grouped by gender.

### 3. Gender and medical conditions

- Bar chart of patient counts by gender.
- Bar chart of patient counts by medical condition.
- Count plot showing gender distribution across medical conditions.

### 4. Admission analysis

- Bar chart of admission types.
- Stacked bar chart showing admission types across medical conditions.

### 5. Billing analysis

- Histogram of hospital billing amounts.
- Violin plot of billing amounts by medical condition.
- Bar chart of average billing amount by medical condition.
- Violin plot of billing amounts by insurance provider.
- Prints and plots average billing amount by insurance provider.

### 6. Monthly admissions

- Converts Admission_Date to a datetime value.
- Extracts the admission month.
- Counts and sorts admissions by month after handling invalid or missing values in the derived summary.

### 7. Correlation analysis

Calculates and prints a correlation matrix for:
- Age
- Length_of_Stay
- Billing_Amount

---

## Requirements
Install the required libraries:
```pip install pandas numpy matplotlib seaborn```

### How to Run

1. Place health_visual.py and healthcare_preprocessed (1).csv in your project folder, or ensure the CSV path in the script is correct.
2. Install the required Python libraries.
3. Run the script using Python or execute the cells in Google Colab.
4. Review the generated charts and printed summaries.

---

## Project Structure

```
Healthcare-Data-Visualization/
├── health_visual.py
├── healthcare_preprocessed (1).csv
└── README.md
```
---

## Notes and Limitations
- The dataset must contain the columns referenced in the script; otherwise, the relevant code will raise a column-related error.
- Admission_Date must contain values that can be converted to datetime.
- The script computes correlations only for Age, Length_of_Stay, and Billing_Amount.
- The code shown ends after printing the correlation matrix; it does not include a correlation heatmap or additional interpretation.
- Charts and numerical results depend on the supplied dataset.

---

## Author

**Madhumidha**
