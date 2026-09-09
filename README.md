
# Task 1 E-Commerce Dataset Cleaning

## Week 1 – Data Cleaning and Preprocessing

### Project Objective

The objective of this project is to clean and prepare an e-commerce transactional dataset for further analysis.

The project focuses on identifying and handling:

* Missing values
* Duplicate records
* Repeated Order IDs
* Invalid or inconsistent data
* Incorrect data types
* Inconsistent column names
* Invalid quantities and prices
* Date formatting issues
* Total amount inconsistencies

The cleaned dataset is prepared in a structured format suitable for data analysis and visualization.

---

## Dataset Description

The dataset contains **67 e-commerce transaction records** with information related to orders, customers, products, pricing, payments, delivery, and location.

### Main Columns

| Column          | Description                        | Data Type   |
| --------------- | ---------------------------------- | ----------- |
| Order_ID        | Unique order identifier            | Identifier  |
| Customer_ID     | Customer identifier                | Numeric     |
| Product_Name    | Name of the purchased product      | Categorical |
| Category        | Product category                   | Categorical |
| Quantity        | Number of products ordered         | Numeric     |
| Unit_Price      | Price of one product               | Numeric     |
| Total_Amount    | Total recorded transaction amount  | Numeric     |
| Order_Date      | Date on which the order was placed | Date        |
| Payment_Mode    | Payment method used                | Categorical |
| Delivery_Status | Current delivery status            | Categorical |
| City_or_Region  | Customer/order location            | Categorical |

---

## Tools and Libraries Used

### Programming Language

* Python

### Libraries

* **Pandas** – Data loading, cleaning, validation, and analysis
* **NumPy** – Numerical operations
* **OpenPyXL** – Reading and writing Excel files

### Software

* Jupyter Notebook / Google Colab / VS Code
* Microsoft Excel

---

## Key Steps Performed

### 1. Dataset Inspection

The dataset was loaded using Pandas and inspected to understand:

* Number of rows and columns
* Column names
* Data types
* Sample records
* Statistical information

### 2. Missing Value Analysis

Missing values were checked column by column.

The proportion of missing values was calculated to determine an appropriate treatment strategy.

Where required:

* Median was used for missing numeric values.
* `"Unknown"` was used for missing categorical values.
* Completely empty columns were removed.

### 3. Duplicate Analysis

The dataset was checked for fully duplicated rows.

Repeated Order IDs were also investigated separately.

Fully duplicated records were not found. Repeated Order IDs were retained because they represented different transaction details rather than identical records.

### 4. Column Name Standardization

Column names were standardized by:

* Removing unnecessary spaces
* Using consistent naming
* Replacing spaces with underscores

Example:

`Total Price` → `Total_Amount`

`Order Date` → `Order_Date`

### 5. Text Cleaning

Leading and trailing spaces were removed from text fields such as:

* Product Name
* Category
* Payment Mode
* Delivery Status
* City or Region

### 6. Data Validation

The following validation checks were performed:

* Quantity should not be negative.
* Unit Price should not be zero or negative.
* Order Date should contain valid dates.
* Category values were reviewed for consistency.
* Payment Mode values were reviewed.
* Delivery Status values were reviewed.
* City/Region values were reviewed.

### 7. Total Amount Validation

A calculated total was created using:

`Quantity × Unit_Price`

This value was compared with the recorded `Total_Amount`.

Any differences were flagged for review instead of automatically changing the original transaction value.

### 8. Cleaned Dataset Creation

After cleaning and validation, the processed dataset was saved as a separate Excel file.

The original/raw dataset was preserved so that the cleaning process remains traceable.

---

## Major Findings

The following findings were identified during the cleaning process:

* **67 records** were analyzed.
* **0 fully duplicated rows** were found.
* **2 Order IDs** appeared more than once.
* Repeated Order IDs were retained because their transaction details were different.
* One completely blank column was identified and removed.
* No negative quantities were found.
* No zero or negative unit prices were found.
* Order dates were successfully converted to a proper date format.
* Text fields were cleaned by removing unnecessary spaces.
* Total Amount values were compared with Quantity × Unit Price.
* Differences in Total Amount were flagged rather than overwritten because the source dataset did not provide enough information to determine whether taxes, discounts, shipping charges, or other adjustments were included.

---

## Folder Structure

```text
E-Commerce-Dataset-Cleaning/
│
├── README.md
│
├── data/
│   ├── E-Commerce Dataset Cleaning(3).xlsx
│   └── E-Commerce_Dataset_Cleaned.xlsx
│
├── code/
│   └── ecommerce_data_cleaning.py
│
└── reports/
    ├── Inspection_Summary
    ├── Missing_Value_Report
    ├── Duplicate_Analysis
    ├── Validation_Checks
    └── Cleaning_Decisions
```

---

## Execution Instructions

### Step 1: Install Required Libraries

Open the terminal or command prompt and run:

```bash
pip install pandas numpy openpyxl
```

### Step 2: Place the Dataset

Place the raw Excel dataset inside the `data` folder.

Example:

```text
data/E-Commerce Dataset Cleaning(3).xlsx
```

### Step 3: Run the Python Script

Navigate to the project directory:

```bash
cd E-Commerce-Dataset-Cleaning
```

Run:

```bash
python code/ecommerce_data_cleaning.py
```

### Step 4: Check the Output

After successful execution, the cleaned dataset will be generated as:

```text
E-Commerce_Dataset_Cleaned.xlsx
```

The cleaned file can then be opened using Microsoft Excel for further analysis.

---

## Cleaning Assumptions

The following assumptions were used:

1. The raw dataset should not be modified directly.
2. Completely empty columns do not provide useful analytical information and can be removed.
3. Repeated Order IDs are not automatically considered duplicates because one order may contain multiple transaction/product records.
4. Missing numeric values should be handled using an appropriate statistical method such as the median.
5. Missing categorical values can be represented using `"Unknown"`.
6. Original Total Amount values should not be changed without evidence about the business calculation.
7. Data validation issues should be documented before making irreversible changes.

---

## Deliverables

The project provides the following deliverables:

* Raw dataset inspection summary
* Missing value report
* Duplicate analysis
* Data validation checks
* Cleaned dataset
* Cleaning decisions and assumptions
* Python cleaning script
* README documentation

---

## Author Details

**Name:** Megha Rameshwar Bidwe
**Project:** E-Commerce Dataset Cleaning
**Week:** Week 1
**Task:** Task 1 – E-Commerce Dataset Cleaning

---

## Conclusion

The e-commerce dataset was systematically inspected, cleaned, and validated using Python and Pandas.

The cleaning process improves data quality while preserving the original business information. The resulting dataset is structured and ready for subsequent data analysis, visualization, and reporting.
