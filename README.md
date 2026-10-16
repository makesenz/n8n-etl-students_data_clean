# n8n ETL Pipeline — Student Data Cleaning

**Assignment:** Week 3 · Day 3  
**Platform:** n8n Cloud  
**Tools:** n8n, LLM (Basic LLM Chain), JavaScript, CSV/JSON

## Overview

This project demonstrates an ETL (Extract, Transform, Load) workflow that processes a messy student enrollment CSV, cleans records, removes duplicates, filters enrolled students, and generates a clean CSV output.

## Workflow

1. **CSV Upload** — Accepts the source CSV file.
2. **Extract from File** — Converts CSV rows into structured items.
3. **Basic LLM Chain** — Helps normalize student record fields.
4. **Code in JavaScript** — Parses the LLM's JSON output, trims and normalizes fields, and skips records missing a name or email.
5. **Remove Duplicates** — Removes repeated records based on email.
6. **Filter** — Keeps records where `status` equals `enrolled`.
7. **Convert to File** — Exports the resulting records as `students_clean.csv`.

## Data Cleaning Rules

- Trim leading and trailing whitespace.
- Normalize names and course names.
- Convert email addresses to lowercase.
- Convert status values to lowercase.
- Preserve `enrolled_date`.
- Exclude records with a missing name or email from the main output.
- Remove duplicate records using the email field.
- Keep only records with `status = enrolled`.

## Results

| Stage | Records |
|---|---:|
| Input CSV | 20 |
| After JavaScript cleaning and missing-field checks | 18 |
| After duplicate removal | 16 |
| After enrolled-status filter | 12 |
| CSV file generated | 1 file containing the filtered records |

The final CSV contains 12 student records based on the workflow execution.

## Files

- `students.csv` — Messy input CSV.
- `students_clean.csv` — Cleaned and filtered CSV output.
- `README.md` — Project documentation.
- Workflow screenshot(s) — Evidence of the n8n workflow and execution.

## How to Run

1. Open the workflow in n8n Cloud.
2. Upload the source `students.csv` through the workflow's CSV Upload form.
3. Execute the workflow.
4. Check each node's output and item counts.
5. Download the generated `students_clean.csv`.
6. Verify the output records and filename.

## Key Learnings

- Building an ETL pipeline in n8n.
- Converting CSV data into structured JSON items.
- Using an LLM for assisted data normalization.
- Using JavaScript for predictable data cleaning and validation.
- Removing duplicates and filtering records.
- Debugging n8n expressions and node execution paths.

## Notes

- The output count reflects the current test data and workflow rules; it may change if the input CSV changes.
- The workflow uses an LLM, so review the output for correctness before relying on it.
- Missing names and emails are excluded from the main output in this implementation.

---
Built as part of the Week 3 · Day 3 n8n ETL Pipeline assignment.
