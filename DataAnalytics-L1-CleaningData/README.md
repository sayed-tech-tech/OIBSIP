    Task 3 – Data Cleaning: Retail Transactions Dataset

     Overview
This project cleans a retail transactions dataset (12,575 rows, 11 columns) 
sourced from Kaggle. The raw data contained missing values across several 
columns and one column with an incorrect data type. This notebook diagnoses 
each issue and applies a targeted fix, explained below.

    Dataset
- Source: Kaggle (retail transactions dataset)
- Raw file: `raw_data.csv` — 12,575 rows, 11 columns
- Cleaned file: `cleaned_data.csv` — 11,971 rows, 11 columns

    Issues Found
| Column            | Missing Values | Issue                          |
|-------------------|-----------------|----------------------------------|
| Item              | 1,213           | Missing item label                |
| Price Per Unit    | 609             | Missing price                     |
| Quantity          | 604             | Missing quantity                  |
| Total Spent       | 604             | Missing total                     |
| Discount Applied  | 4,199           | Missing + wrong dtype (object)    |
| Transaction Date  | 0               | Stored as text, not a date type   |

No duplicate rows were found.

Cleaning Steps & Reasoning

1. Recovered missing `Price Per Unit`
    using the relationship 
    `Price = Total Spent / Quantity`, since all 609 rows with missing 
    Price had both Quantity and Total Spent present.

2. Dropped 604 rows
    where both `Quantity` and `Total Spent` were 
    missing simultaneously, since there was no way to mathematically 
    recover either value. This is a 4.8% data loss, which was judged 
    acceptable given no reliable reconstruction was possible.

3. Filled missing `Item` values with `"Unknown"` rather than 
   dropping the rows, since the rest of each row (price, quantity, 
   category) was still valid and usable data.

4. Filled missing `Discount Applied` values with `False`, under 
   the assumption that an unrecorded discount means no discount was 
   applied. This is a judgment call made explicit here for transparency.

5. Converted `Transaction Date`
    from text to a proper datetime 
    type using `pd.to_datetime()`, enabling date-based analysis.

6. Converted `Discount Applied`
    to a proper boolean type.

7. Reset the index
    after dropping rows, and exported the result 
    to `cleaned_data.csv`.

Result
- Rows: 12,575 → 11,971
- Missing values: fully resolved (0 nulls in every column)
- All data types corrected

Tools Used
Python, pandas, Jupyter Notebook

Author
Syed Touheed Shah — Data Analytics Intern, Oasis Infobyte (OIBSIP)