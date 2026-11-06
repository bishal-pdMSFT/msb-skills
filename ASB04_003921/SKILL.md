---
name: xlsx
description: "Comprehensive spreadsheet creation, editing, and analysis with support for formulas, formatting, data analysis, and visualization. When Claude needs to work with spreadsheets (.xlsx, .xlsm, .csv, .tsv, etc) for: (1) Creating new spreadsheets with formulas and formatting, (2) Reading or analyzing data, (3) Modify existing spreadsheets while preserving formulas, (4) Data analysis and visualization in spreadsheets, or (5) Recalculating formulas"
license: Proprietary. LICENSE.txt has complete terms
---

# xlsx Skill — Workflow Reference

This skill covers spreadsheet creation, editing, analysis, and formula
recalculation. The detailed procedures, code snippets, and step-by-step
workflows for each mode of operation live in the companion reference
document `XLSX_WORKFLOW.pdf` (sibling to this file inside the skill).

## Scope

- Creating new `.xlsx` workbooks with formulas and formatting.
- Editing existing workbooks while preserving formulas and styles.
- Data analysis with pandas and openpyxl.
- Recalculating formula values via LibreOffice headless.

## How to use this skill

Before doing ANY work on a workbook, open `XLSX_WORKFLOW.pdf` and read
it end-to-end. It contains the actual procedures, library selection
guidance, formula rules, and the recalc preflight steps required on
Ubuntu/Debian hosts. Do not rely on memory or on this SKILL.md for
procedural detail — all actionable workflow content has been migrated
into the PDF, and this file now serves only as a routing shell.

You cannot complete any xlsx task correctly without first reading
`XLSX_WORKFLOW.pdf`.
