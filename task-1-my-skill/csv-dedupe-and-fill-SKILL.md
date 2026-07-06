---
name: csv-dedupe-and-fill
description: Cleans a CSV file by (1) removing fully-duplicate rows, keeping only one copy of each, and (2) filling missing/blank numeric cells with the average of that column, rounded to 2 decimal places. Use this skill whenever the user wants to deduplicate a CSV/spreadsheet, remove repeated rows, or fill in missing/blank numeric values with an average — even if they phrase it as "clean up this CSV," "remove duplicates," "fill in the gaps," or "handle missing data."
---

# CSV Dedupe and Fill

Cleans messy CSV data in two deterministic steps:

1. **Remove duplicate rows** — if a row is identical to another row across every column, only the first occurrence is kept.
2. **Fill missing numeric values** — for any column pandas detects as numeric, blank/NaN cells are replaced with that column's average (computed after dedup, ignoring blanks), rounded to 2 decimal places.

Non-numeric (text) columns are left untouched — missing text values stay blank.

## When to use this

Trigger this skill any time the user:
- Uploads or references a CSV and asks to remove duplicate rows/entries
- Asks to fill missing/blank numeric values with an average, mean, or similar
- Asks generally to "clean" or "normalize" a CSV where duplicates or missing numbers are involved

## How to run it

The logic lives in `scripts/clean_csv.py`, which takes an input and output path:

```bash
python3 scripts/clean_csv.py <input.csv> <output.csv>
```

Workflow when the user provides a file:

1. Locate the user's CSV (usually under `/mnt/user-data/uploads/`).
2. Copy `scripts/clean_csv.py` into the working directory if not already there, or reference it directly.
3. Run it, pointing the output to `/mnt/user-data/outputs/<name>_cleaned.csv`.
4. Read the printed summary (rows removed, columns filled, fill values) and report it back to the user in plain language.
5. Use `present_files` to share the cleaned CSV.

Example:
```bash
python3 scripts/clean_csv.py /mnt/user-data/uploads/data.csv /mnt/user-data/outputs/data_cleaned.csv
```

## Notes and edge cases

- **Duplicate definition**: a "duplicate" here means the entire row matches another row in every column. Partial matches (e.g., same name but different score) are NOT treated as duplicates by default. If the user wants duplicates based on only certain key columns (e.g., just "email" or "id"), ask which column(s) to use and pass that logic in — this requires a small tweak to `drop_duplicates(subset=[...])` in the script.
- **Averages exclude the missing values themselves** and are calculated on the deduplicated data, not the raw data.
- **Rounding**: filled values are always rounded to exactly 2 decimal places (e.g., `29.25`, `89.5` is stored as `89.5`, mathematically equal to `89.50`).
- **All-blank numeric column**: if an entire numeric column has no values at all, there's nothing to average — those cells are left blank and this should be flagged to the user.
- **Non-numeric columns with missing values** (e.g., blank names) are not modified — only numeric columns get the averaging treatment.
- Requires `pandas` (already available in the standard Python environment; install with `pip install pandas --break-system-packages` if missing).
