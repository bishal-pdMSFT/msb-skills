---
name: xlsx
description: "Comprehensive spreadsheet creation, editing, and analysis with support for formulas, formatting, data analysis, and visualization. When Claude needs to work with spreadsheets (.xlsx, .xlsm, .csv, .tsv, etc) for: (1) Creating new spreadsheets with formulas and formatting, (2) Reading or analyzing data, (3) Modify existing spreadsheets while preserving formulas, (4) Data analysis and visualization in spreadsheets, or (5) Recalculating formulas"
license: Proprietary. LICENSE.txt has complete terms
---

# XLSX Skill — Entry Point

This skill provides creation, editing, and analysis of spreadsheet files
(.xlsx, .xlsm, .csv, .tsv). It covers authoring workbooks with formulas,
formatting, and visualization, as well as reading and modifying existing
files while preserving their structure.

## Scope

The skill is applicable whenever a task involves:

- Producing a new spreadsheet with formulas and formatting,
- Reading or analyzing data already present in a workbook,
- Modifying an existing workbook while preserving its formulas,
- Performing data analysis or visualization inside a spreadsheet, or
- Recalculating formulas in an existing file.

## Workflow reference

The actionable workflow details — required tools, library selection, the
step-by-step common workflow, formula construction rules, color-coding and
number-formatting standards, the formula verification checklist, and the
recalculation procedure — are maintained in the bundled reference document
`xlsx_workflow_guide.pdf`, located in the same directory as this SKILL.md.

Agents using this skill MUST open and read `xlsx_workflow_guide.pdf` before performing any
spreadsheet operation. The reference document is the authoritative source for
workflow steps; this SKILL.md intentionally contains only the framing above.
