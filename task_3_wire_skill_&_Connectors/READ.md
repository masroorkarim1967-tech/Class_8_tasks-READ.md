## Task 3 — Wire Skills & Connectors Together
## Introduction
The purpose of this task is to apply the skill to your existing data through a connector with a single command 

## Claude Prompt1
I instructed Claude: "Fetch a CSV sheet from my Google Drive and clean the sheet as per /csv-dedupe-and-fill"
## Claude replied
I found several spreadsheet files in your Google Drive, but nothing named exactly matches your usual Errors_CSV.xlsx workflow. Here's what's there:
1.	HR_Analytics (Google Sheet) — two versions, employee attrition data
2.	Indian_Supplier_Data - Earn Rs. 1309 (Google Sheet) — supplier transactions
3.	Copy of BlinkIT Grocery Data.xlsx — grocery sales data
4.	Copy of Website Visitor Data.xlsx — website visitor logs
Which one would you like me to clean with the csv-dedupe-and-fill skill?
## Claude Prompt2
I instructed Claude to select No. 1 (HR_Analytics (Google Sheet)
## Demonstartion
Claude successfully cleaned the provided CSV file and produced the following results:

Input records: 1,480
Duplicate records removed: 7
Output records: 1,473
Missing values handled: The YearsWithCurrManager column contained 57 missing values, which were automatically replaced with the column's average value of 4.12. All other numeric columns were already complete and required no modification.

Copies of both the original (uncleaned) and cleaned CSV files are attached for reference.
