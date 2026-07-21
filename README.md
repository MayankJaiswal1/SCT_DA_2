# 🧹 SuperClean — Global Superstore Data Cleaning & EDA Pipeline

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-1.5-150458?style=flat&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-1.24-013243?style=flat&logo=numpy&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat)

A Pandas-based data cleaning pipeline built on the **Global Superstore** dataset (51,290 orders across 7 markets and 147 countries, 2011–2014). This project takes raw, messy retail transaction data and turns it into an analysis-ready dataset through missing value handling, deduplication, and data type correction — all documented step-by-step in a Jupyter Notebook. ✨

## 📌 Overview

Real-world datasets are rarely analysis-ready. This project simulates a common data analyst task: taking a raw export and preparing it for downstream reporting, dashboarding, or modeling. Every cleaning decision is explained inline, so the notebook doubles as documentation of the *why*, not just the *what*.

## 🎯 Objectives

- Load the Global Superstore dataset into a Pandas DataFrame
- Identify and handle missing values
- Detect and remove duplicate rows
- Convert columns to correct data types (string → datetime)
- Export a cleaned dataset ready for analysis or visualization

## 🗂️ Dataset

**Source:** [Global Superstore Dataset — Kaggle](https://www.kaggle.com/datasets/apoorvaappz/global-super-store-dataset)

| | |
|---|---|
| Rows | 51,290 |
| Columns | 24 |
| Date Range | Jan 2011 – Dec 2014 |
| Markets | US, APAC, EU, Africa, EMEA, LATAM, Canada |
| Countries | 147 |

Key columns: `Order ID`, `Order Date`, `Ship Date`, `Customer Name`, `Segment`, `Country`, `Region`, `Category`, `Sub-Category`, `Sales`, `Profit`, `Quantity`, `Discount`.

## 🧽 Cleaning Steps

| Step | Issue Found | Action Taken |
|---|---|---|
| 🕳️ Missing values | `Postal Code` ~80% missing (non-US/Canada orders don't have one) | Filled with `'Unknown'` instead of dropping rows |
| 🪞 Duplicates | Checked with `.duplicated()` | 0 found; `.drop_duplicates()` applied as a standard safeguard |
| 🔄 Data types | `Order Date` / `Ship Date` stored as text in `DD-MM-YYYY` format | Converted to `datetime64` using `pd.to_datetime()` |
| ✅ Validation | — | Checked no order ships before it's placed |

## 🛠️ Tech Stack

- 🐍 Python 3
- 🐼 Pandas
- 📓 Jupyter Notebook
- 🔢 NumPy

## 📁 Project Structure

```
SuperClean/
├── Global_Superstore2.csv              # Raw dataset
├── Superstore_Data_Cleaning.ipynb      # Cleaning & EDA notebook
├── Global_Superstore_Cleaned.csv       # Cleaned output
└── README.md
```

## 🚀 Getting Started

1. 📥 Clone the repo
   ```bash
   git clone [https://github.com/MayankJaiswal1/SCT_DA_2.git]
   cd superclean
   ```
2. 📦 Install dependencies
   ```bash
   pip install pandas jupyter
   ```
3. ▶️ Launch the notebook
   ```bash
   jupyter notebook Superstore_Data_Cleaning.ipynb
   ```
   Or open it directly in Google Colab. 🔗

## 📊 Output

The final `Global_Superstore_Cleaned.csv` contains all 51,290 rows with:
- ✅ No missing values
- ✅ No duplicate rows
- ✅ Properly typed date columns, ready for time-series analysis, dashboarding (Power BI/Tableau/Excel), or further ML preprocessing

## 👤 Author

**Mayank** — Data Analyst Intern  💼
Built as part of a hands-on data cleaning practice project. 🚀

---

⭐ If you found this useful, consider giving the repo a star!
