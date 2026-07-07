# MASROOR KARIM
## All Tasks/Projects of Class-8
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

## Task 2 — Connect One App, Read-Only
## Introduction

The purpose of this task is to demonstrate how to connect Claude AI to external data sources, such as Gmail and Google Drive, using the Connect feature. Once connected, Claude AI can securely access these sources to retrieve, analyze, and extract relevant information based on the user's requirements, making it easier to find and utilize important data efficiently. 

## Implementation
Following the procedure demonstrated during the class, I successfully connected Claude AI to both my Gmail account and Google Drive using the Connect feature. This integration enabled Claude to securely access my emails and stored files, allowing it to retrieve and analyze the required information when prompted.

## Demonstration
To demonstrate this capability, I prompted Claude AI to generate a summary of my ten most recent Gmail messages and the three most recent documents stored in my Google Drive. After accessing the connected data sources, Claude successfully retrieved the requested information and presented concise, well-structured summaries. Copies of both generated summaries are attached as supporting evidence.
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
- Input records: 1,480
- Duplicate records removed: 7
- Output records: 1,473
- Missing values handled: The YearsWithCurrManager column contained 57 missing values, which were automatically replaced with the column's average value of 4.12. All other numeric columns were already complete and required no modification.

Copies of both the original (uncleaned) and cleaned CSV files are attached for reference.
## Task 4 — Make It Portable or Hand It Off
## Introduction
The purpose of this task is to demonstrate that the developed Skill is not limited to a single conversation or platform, but functions as a reliable and reusable asset. 
## Implementation
I created a Skill.md file (Copy attached) for my skill, csv-dedupe-and-fill, and shared it with our group for testing. One of our classmates, Mr. Tariq Jameel, successfully tested the skill and confirmed that it functions correctly without any discrepancies.

## Task 5 — Audit a Skill Before Testing
## Introduction
The purpose of this task is to develop the habit of evaluating a Skill before enabling it, particularly when it has been created by someone else. It emphasizes understanding a Skill's purpose and assessing its safety without the need to examine its underlying code. This ensures the responsible and secure use of AI Skills.
## Implementation
For this purpose, I installed the "Theme Factory Skill" in my Claude AI (from Claude Skill options)
## Explanation
Theme Factory gives your slides, docs, or other artifacts a polished, matching look. It offers 10 ready-made themes, each with its own color palette and font pairing (like "Ocean Depths" or "Tech Innovation"). It shows you a visual preview so you can pick one you like. Once you choose, it applies those colors and fonts consistently across the whole document. If none of the presets fit, it can design a custom theme based on your description. Basically: pick a style, and it makes everything look consistent and professional.
## Sensitivity
No, nothing sensitive. It's just static reference files — a PDF showcase plus 10 markdown files listing hex color codes and font names, nothing executable. No external server calls, no network activity, no API keys or logins required. It doesn't read, upload, or transmit any of your personal or work data anywhere. It only applies its built-in color/font specs to whatever artifact you're already working on, inside the chat. Bottom line: a passive styling toolkit, not something that talks to the outside world or touches credentials.
## Safe to Enable
Yes, in my point of view, it's safe to enable. It only uses fixed color and font files to style my documents — no internet access, no logins, no data sent anywhere. It just makes things look nice and beautiful; nothing risky happens behind the scenes.
## Implementation
I applied this skill in a PPT file on my computer, and the results were excellent. A copy of the PPT after skill application is attached
