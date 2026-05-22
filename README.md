# 🛍️ E-Commerce Clothing Reviews — Data Parsing, Cleansing & Integration

A complete data wrangling pipeline built in Python for COSC2820 (Advanced
Programming for Data Science) at RMIT University. The project parses, audits,
cleanses, and integrates two clothing review datasets sourced from a modified
version of the [Women's E-Commerce Clothing Reviews](https://www.kaggle.com/datasets/nicapotato/womens-ecommerce-clothing-reviews)
dataset on Kaggle.

## 📋 Project Overview

| Task | Description | Output |
|---|---|---|
| Task 1 | Parse XML dataset into a pandas DataFrame | — |
| Task 2 | Audit and cleanse data quality issues | `s3859590_dataset1_solution.csv`, `s3859590_errorlist.csv` |
| Task 3 | Integrate cleaned dataset with a second CSV source | `s3859590_dataset_integrated.csv` |

## 🔧 Tasks

### Task 1 — Data Parsing
- Examined structure and format of `s3859590_dataset1.xml`
- Parsed XML into a pandas DataFrame with 11 columns (ClothID, Age, Review Title,
  Customer Rating, Positive Review Count, Section, Department, Category,
  Online Time, Cost, Recommended IND)

### Task 2 — Data Auditing & Cleansing
Identified and resolved the following categories of data issues:
- Typos and spelling mistakes
- Abnormal values and format irregularities
- Integrity constraint violations
- Outliers
- Duplicate records
- Missing values
- Inconsistent representations of the same data

All errors documented in `s3859590_errorlist.csv` with columns:
`datasetNo`, `indexOfdf`, `Id`, `ColumnName`, `Original`, `Modified`, `ErrorType`, `Fixing`

### Task 3 — Data Integration
- Resolved schema-level conflicts between `dataset1_solution.csv` and `dataset2.csv`
- Applied semantic mapping to align column names to the global schema
- Merged datasets into a unified table
- Detected and removed duplicates
- Identified a unique key for the integrated dataset
- Output: `s3859590_dataset_integrated.csv`

## 🗂️ Repository Structure
s3859590/
├── s3859590_dataset1.xml               # Raw XML input (Task 1 & 2)
├── s3859590_dataset2.csv               # Clean CSV input (Task 3)
├── s3859590_task1_2.ipynb              # Jupyter notebook: Tasks 1 & 2
├── s3859590_task3.ipynb                # Jupyter notebook: Task 3
├── s3859590_dataset1_solution.csv      # Cleaned output from Task 2
├── s3859590_errorlist.csv              # Error log from Task 2
└── s3859590_dataset_integrated.csv     # Final integrated output

## 🛠️ Libraries Used

```python
import pandas as pd
import xml.etree.ElementTree as ET
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

## 📊 Dataset Columns (Global Schema)

| Column | Description |
|---|---|
| Clothing ID | Integer ID of the clothing item reviewed |
| Age | Reviewer's age |
| Title | Review title |
| Rating | Customer rating (1–5) |
| Positive Feedback Count | Number of helpful votes |
| Division Name | High-level product division |
| Department Name | Product department |
| Class Name | Product class/category |
| Active Time | Time spent writing the review |
| Price | Product cost |
| Recommended IND | 1 = recommended, 0 = not recommended |

## 👩‍💻 Author

**Prathibha Magesh** — RMIT University, s3859590
