
# 🧹 Data Cleaning Project in MySQL Workbench

## 📌 Project Overview

This project demonstrates a **complete data cleaning workflow** using SQL in **MySQL Workbench**. The dataset contains information about layoffs across various companies, including details like company name, location, industry, stage, and layoff counts.

The objective is to transform the raw, messy data into a **clean, standardized, and analysis-ready table** by handling duplicates, nulls, formatting inconsistencies, and irrelevant columns.

---

## 🛠️ Tools Used

- **MySQL Workbench**
- SQL (Window Functions, CTEs, Joins, Aggregations)
- Dataset: Layoffs (sample company data)

---

## 🔍 Data Cleaning Steps

### 1️⃣ Remove Duplicates
- Created a staging table to isolate the cleaning operations.
- Used `ROW_NUMBER()` with `PARTITION BY` to detect duplicates.
- Removed duplicate rows safely using `DELETE`.

### 2️⃣ Standardize the Data
- Trimmed whitespace from `company` names.
- Unified similar values (e.g., changed `'crypto '` to `'Crypto'` in `industry`).
- Cleaned up trailing punctuation in country names.
- Converted `date` from `VARCHAR` to proper `DATE` format using `STR_TO_DATE()`.

### 3️⃣ Handle Null or Blank Values
- Identified records with missing `industry`, `total_laid_off`, or `percentage_laid_off`.
- Used self-joins to populate missing `industry` values based on matching company names.
- Deleted rows that had insufficient data for imputation (both layoff fields null).

### 4️⃣ Remove Unnecessary Columns
- Dropped the helper column `row_num` after deduplication.

---

## 📂 Project Files
-  mysql-data-cleaning-project/
├── data/
│ └── layoffs.csv
├── sql/
│ └── data_cleaning.sql
├── screenshots/
│ └── cleaned_preview.png
└── README.md


---

## 🧠 Key Concepts Used

- CTEs (Common Table Expressions)
- `ROW_NUMBER()` window function
- String manipulation (`TRIM`, `LIKE`, `UPDATE`)
- Date formatting with `STR_TO_DATE`
- Self joins for intelligent imputation
- Schema alteration (`ALTER TABLE`)

---

## ✅ Final Output

The final cleaned table `layoffs_staging2` is:
- Free of duplicates
- Nulls and blanks are handled
- String formats are consistent
- Suitable for further analysis or dashboarding

---

## 📈 Possible Extensions

- Export cleaned data to CSV
- Load into Power BI or Tableau for visualization
- Perform analysis: trends over time, layoffs by industry, etc.

---

## 🙌 Author

**[Aysha Faidha Muneer]**  
SQL & Data Analyst 
📧 Email: [afaidhamuneer97@gmail.com]

---



