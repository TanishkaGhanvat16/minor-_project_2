# SpendDNA – Personal Transaction Analysis

SpendDNA is a Python-based personal finance analytics project that analyzes raw bank transaction data and converts it into structured spending insights. The project focuses on data cleaning, transaction parsing, merchant normalization, spending categorization, trend analysis, anomaly detection, and rule-based spending archetypes.

## 📌 Project Overview

The project works with six months of transaction data from January to June 2024. The raw dataset contains inconsistent date formats, multiple amount formats, different transaction-type representations, duplicate records, and varied merchant descriptions.

The analysis pipeline cleans and standardizes the data before extracting meaningful financial patterns.

### Dataset
- Raw transactions: **1,328**
- Duplicate transactions removed: **18**
- Clean transactions analyzed: **1,310**
- Period: **January–June 2024**
- Unique normalized merchant vendors: **33**

## 🔄 Project Workflow

The SpendDNA pipeline consists of:

1. **Transaction Parser**
   - Parses multiple date formats
   - Cleans and converts transaction amounts
   - Standardizes transaction types
   - Removes duplicate transactions
   - Creates useful time-based features

2. **Vendor Extractor**
   - Converts messy transaction descriptions into canonical merchant names
   - Handles vendor variations such as Swiggy/BUNDL, Amazon/Amazon Pay, etc.
   - Identifies special transactions such as P2P transfers and cash withdrawals

3. **Category Tagger**
   - Maps normalized vendors into spending categories:
     - Food Delivery
     - Quick Commerce
     - E-commerce
     - Transport
     - Cafe
     - Restaurants
     - Subscriptions
     - Utilities
     - Groceries
     - Investments
     - Fuel
     - Entertainment
     - Personal Transfer
     - Cash Withdrawal

4. **Spending Overview**
   - Calculates total credits and debits
   - Calculates net change and savings rate
   - Identifies top categories and vendors

5. **Monthly Trend Analysis**
   - Compares category spending across January–June
   - Calculates month-on-month percentage changes
   - Identifies the largest monthly increase and decrease

6. **Time-of-Day Analysis**
   - Analyzes spending by hour
   - Identifies peak Food Delivery and Cafe hours
   - Examines late-night Food Delivery activity

7. **Anomaly Detection**
   - Uses category-level z-scores
   - Flags transactions with `z > 2`
   - Identified **29 anomalies**

8. **Archetype Detection**
   - Uses rule-based logic to identify spending patterns
   - Detected:
     - The Foodie
     - The Quick Commerce Junkie
     - The Shopaholic
     - The Investor
     - The YOLO Spender

## 📊 Key Results

### Spending Overview

- **Total Credits:** ₹509,774
- **Total Debits:** ₹821,046
- **Net Change:** -₹311,272
- **Savings Rate:** -61.1%
- **Transactions:** 1,310

### Top Spending Categories

| Category | Spend | Share |
|---|---:|---:|
| E-commerce | ₹293,179 | 35.7% |
| Investments | ₹122,704 | 14.9% |
| Food Delivery | ₹76,399 | 9.3% |
| Fuel | ₹63,230 | 7.7% |
| Restaurants | ₹58,283 | 7.1% |

### Top Vendors

| Vendor | Spend | Transactions |
|---|---:|---:|
| Amazon | ₹150,425 | 39 |
| Flipkart | ₹107,803 | 26 |
| Zerodha | ₹105,000 | 7 |
| Restaurant | ₹58,283 | 35 |
| Swiggy | ₹46,889 | 107 |

## ⏰ Time-of-Day Insights

- Food Delivery peak: **20:00**
- Cafe peak: **10:00**
- Food Delivery transactions between 21:00–01:00: **18.31%**

## 📈 Trend Analysis

Food Delivery spending across the six months:

- January: ₹11,409
- February: ₹11,398
- March: ₹12,529
- April: ₹16,036
- May: ₹10,649
- June: ₹14,378

Largest month-on-month increase:
- **Fuel — March: +1158.49%**

Largest month-on-month decrease:
- **Entertainment — May: -100.00%**

## 🚨 Anomaly Detection

A total of **29 transactions** were flagged using a category-level z-score threshold of `z > 2`.

Top anomalies included:
- Amazon — ₹22,008
- Amazon — ₹21,986
- Restaurant — ₹8,383
- Restaurant — ₹7,935
- Restaurant — ₹7,931

## 🛠️ Technologies & Concepts

**Languages & Libraries**
- Python
- Pandas
- NumPy

**Concepts**
- Data cleaning and preprocessing
- Date and amount parsing
- String manipulation
- Dictionary-based merchant normalization
- Conditional classification
- GroupBy aggregation
- Pivot tables
- Percentage calculations
- Time-series analysis
- Statistical anomaly detection
- Rule-based classification

## 📁 Project Structure

```text
SpendDNA/
├── SpendDNA.ipynb
├── rahul_transactions.csv
└── README.md
