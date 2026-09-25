# SWYNEX Data Cleaning Project

## Project Overview

This project was completed as part of my data analytics internship at SWYNEX.

The objective was to perform data quality checks and clean a public dataset by identifying:

* Missing values
* Duplicate records
* Incorrect data types
* Inconsistent values
* Invalid numerical values

The **Sample Superstore** dataset was selected for this project and analyzed using Python and Pandas.

---

## Dataset

The dataset contains sales transaction records from a retail business.

It includes information related to:

* Shipping mode
* Customer segment
* Country
* City
* State
* Postal code
* Region
* Product category
* Product sub-category
* Sales
* Quantity
* Discount
* Profit

### Dataset Size

| Metric        | Value |
| ------------- | ----: |
| Original rows | 9,994 |
| Columns       |    13 |
| Final rows    | 9,977 |

---

## Tools Used

* Python
* Pandas
* NumPy
* Google Colab
* GitHub

---

## Data Cleaning Process

### 1. Missing Value Analysis

All columns were checked for missing values.

**Result:** No missing values were found.

```text
Missing values = 0
```

Therefore, no missing-value imputation or row removal was required.

---

### 2. Duplicate Record Analysis

The dataset was checked for exact duplicate records using Pandas.

**Result:**

```text
Duplicate records identified = 17
```

The duplicate records were removed using:

```python
df_cleaned = df.drop_duplicates().copy()
```

After cleaning:

```text
Remaining duplicate records = 0
```

---

### 3. Data Type Validation

The data types of all 13 columns were inspected.

The following fields were confirmed as numeric:

* Postal Code
* Sales
* Quantity
* Discount
* Profit

Categorical fields such as Ship Mode, Segment, City, State, Region, Category, and Sub-Category were stored as text.

No incorrect data types requiring correction were identified.

---

### 4. Inconsistent Value Analysis

Categorical columns were examined for:

* Different capitalization
* Spelling inconsistencies
* Unexpected category values
* Leading or trailing whitespace

No obvious inconsistent categorical values were identified.

A whitespace check also confirmed that no categorical values contained unwanted leading or trailing spaces.

---

### 5. Numerical Data Validation

Numerical columns were checked for invalid values.

| Check        | Result |
| ------------ | -----: |
| Quantity ≤ 0 |      0 |
| Sales < 0    |      0 |
| Discount < 0 |      0 |
| Discount > 1 |      0 |

Negative profit values were retained because they represent legitimate business losses rather than invalid data.

---

## Before vs After Cleaning

| Metric            | Before Cleaning | After Cleaning |
| ----------------- | --------------: | -------------: |
| Rows              |           9,994 |          9,977 |
| Columns           |              13 |             13 |
| Missing Values    |               0 |              0 |
| Duplicate Records |              17 |              0 |

---

## Final Result

The final dataset contains **9,977 records and 13 columns**.

The cleaning process successfully removed 17 exact duplicate records while preserving valid business data.

No missing values, incorrect data types, obvious categorical inconsistencies, or invalid numerical values requiring correction were identified.

The cleaned dataset is available in:

```text
data/cleaned_superstore.csv
```

The complete analysis is available in:

```text
notebooks/data_cleaning.ipynb
```

---

## Repository Structure

```text
SWYNEX-Data-Cleaning/
│
├── data/
│   ├── SampleSuperstore.csv
│   └── cleaned_superstore.csv
│
├── notebooks/
│   └── data_cleaning.ipynb
│
├── README.md
│
└── requirements.txt
```

---

## How to Reproduce the Analysis

1. Clone or download this repository.
2. Install the required Python libraries:

```bash
pip install -r requirements.txt
```

3. Open `notebooks/data_cleaning.ipynb`.
4. Place the raw dataset in the `data` directory if required.
5. Run the notebook cells sequentially.
6. The cleaned dataset will be generated as `cleaned_superstore.csv`.

---

## Project Status

**Completed**

This project demonstrates practical data-cleaning and data-quality validation using Python and Pandas.



# Task 2 — Exploratory Data Analysis

## Objective

Perform exploratory data analysis on the cleaned dataset to identify important statistics, trends, patterns, and anomalies.

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Google Colab

## Dataset

The analysis uses the cleaned Sample Superstore dataset produced during Task 1.

## Key Statistics

| Metric | Value |
|---|---:|
| Total Sales | $2,296,194.59 |
| Total Profit | $286,238.45 |
| Average Sales | $230.15 |
| Median Sales | $54.82 |
| Average Profit | $28.69 |
| Median Profit | $8.67 |
| Total Quantity Sold | 37,820 |
| Overall Profit Margin | 12.47% |

## Exploratory Analysis

The following areas were analyzed:

1. Product category performance
2. Regional performance
3. Customer segment performance
4. Sub-category profitability
5. Discount and profit relationship
6. High-value and large-loss transactions

## Key Insights

### 1. Technology leads category performance

Technology generated the highest sales of $836,154.03 and the highest profit of $145,451.98 among the three categories.

### 2. West region leads sales and profit

The West region generated $725,255.64 in sales and $108,328.84 in profit.

### 3. Consumer is the largest customer segment

The Consumer segment generated approximately $1.16 million in sales and $134,004.47 in profit.

### 4. Some high-sales products are not profitable

The Tables sub-category generated $206,964.53 in sales but recorded a loss of $17,725.48.

### 5. Higher discounts are associated with lower profitability

The correlation between Discount and Profit was -0.22, indicating a weak negative linear relationship.

Discount levels from 30% to 80% recorded negative total profit in this dataset.

### 6. High-value transactions can still generate losses

The highest-sales transaction generated $22,638.48 in sales but recorded a loss of $1,811.08.

The largest individual loss was $6,599.98.

## Visualizations

The analysis includes charts for:

- Sales by Category
- Profit by Category
- Sales by Region
- Profit by Region
- Sales by Customer Segment
- Profit by Customer Segment
- Profit by Sub-Category
- Discount vs Profit
- Largest Loss-Making Transactions

## Conclusion

The exploratory analysis shows that sales volume alone does not determine profitability. Differences in product category, sub-category, region, customer segment, and discount levels contribute to different financial outcomes.

The analysis also highlights loss-making sub-categories and unusually large transactions that may require further investigation.

## Project Files

- `cleaned_superstore.csv` — cleaned dataset
- `data_cleaning.ipynb` — Task 1 data cleaning
- `SWYNEX_Task2_Exploratory_Analysis.ipynb` — Task 2 exploratory analysis

