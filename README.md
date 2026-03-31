# 🧹 Automated Data Cleansing and ETL Pipeline

## 📌 Project Overview
Before engaging in complex predictive modeling or database architecture, an analyst must establish an absolute mastery of data organization and cleansing. Raw corporate data is rarely formatted appropriately for immediate analysis. 

This project demonstrates the ability to ingest a severely unformatted, inconsistent "Messy Employee Dataset" and subject it to a rigorous transformation pipeline. The execution validates proficiency in two distinct methodologies: **Traditional Formula-Based Manipulation** and **Automated Power Query (ETL) Workflows**.

## 🎯 Core Objectives
* Transform chaotic, string-concatenated inputs into actionable categorical dimensions.
* Handle missing values, typographical errors, and poisoned data (e.g., text mixed with numbers).
* Establish an automated, scalable Extract, Transform, and Load (ETL) pipeline for absolute reproducibility.

## 🛠️ Methodology 1: Formula-Based Data Cleansing
The initial phase validates manual data wrangling capabilities using advanced text parsing, conditional logic, and statistical imputation.

* **Whitespace Standardization:** Utilized nested `=PROPER(TRIM(CLEAN()))` functions to strip non-printable characters and ghost spaces often introduced by legacy ERP system exports.
* **Dynamic Substring Extraction:** Deconstructed concatenated identifiers (e.g., "Sales-East") using `FIND()`, `LEFT()`, and `RIGHT()` functions to isolate variables dynamically.
* **Data Type Conversion:** Cleansed poisoned financial data (e.g., `$ 65,000 ` or `N/A`) by nesting `SUBSTITUTE()` to remove currency symbols and commas, and wrapping it in a `VALUE()` function to force pure mathematical integers.
* **Statistical Imputation & Error Handling:** Proactively trapped analytical errors. Handled missing quantitative data by deploying `AVERAGEIF()` to replace blank or errored cells with the calculated mean of the respective column.
* **Categorical Logic:** Utilized complex Nested `IF()` statements to assign numerical bonus percentages based on categorical text strings (e.g., "Excellent", "Poor").

## ⚙️ Methodology 2: Power Query Automation (ETL)
To elevate this workflow for enterprise scale, the entire cleansing process was replicated using Power Query. This represents a paradigm shift from manual cell manipulation to automated data engineering.

**Applied Transformation Steps:**
1. **Extraction:** Imported raw .csv data directly into the Power Query Editor.
2. **Transformation:** * Applied bulk Trim/Clean/Capitalize transformations across textual arrays.
    * Split concatenated categorical columns by specific delimiters (`-`).
    * Cleansed financial columns using *Replace Values* to strip formatting, then reassigned Data Types to Decimal Numbers.
    * Generated a Custom Column utilizing **M-Code** conditional logic (`if/then/else`) to automatically calculate performance bonuses.
3. **Load:** Loaded the pristine, machine-readable dataset into a final production table.

**The Strategic Advantage:** Absolute reproducibility. When a new iteration of this messy dataset is generated, the connection simply needs to be refreshed. The Power Query engine automatically executes the entire sequence of transformation steps in seconds, establishing a highly scalable reporting workflow.

## 📂 Repository Contents
* `Automated_Cleansing_Pipeline.xlsx`: The complete workbook containing the Raw Data, Formula Cleansing sandbox, and the final Power Query output.
