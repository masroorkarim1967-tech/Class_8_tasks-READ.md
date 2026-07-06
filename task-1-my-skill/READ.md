# Task 1: My Skill
## Introduction
When working with data, it is common to encounter issues such as duplicate records and missing numeric values. Cleaning these errors manually every time can be repetitive and time-consuming. To automate this process, I created a skill in Claude that removes duplicate entries from datasets (including CSV files) and fills missing numeric values in each column using the column's average value. This significantly improves data quality while reducing manual effort.  
## Initial Prompt
Create a skill that deletes one of the duplicate entries from a CSV file and inserts the average numeric value (upto 02 decilmal places) in the missing values of the columns of the file  
## Name of the Skill by Claude
- csv-dedupe-and-fill
## Improved Prompt
Cleans a CSV file by (1) removing fully-duplicate rows, keeping only one copy of each, and (2) filling missing/blank numeric cells with the average of that column, rounded to 2 decimal places. Use this skill whenever the user wants to deduplicate a CSV/spreadsheet, remove repeated rows, or fill in missing/blank numeric values with an average — even if they phrase it as "clean up this CSV," "remove duplicates," "fill in the gaps," or "handle missing data."
## Applying the Skill
To demonstrate the skill, a sample CSV file named error.csv was created and processed. After applying the skill, a cleaned output file named errors.csv.cleaned was generated. Copies of both CSV files are attached to this task for reference and comparison.
