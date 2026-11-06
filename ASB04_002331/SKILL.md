---
name: xlsx
description: "Comprehensive spreadsheet creation, editing, and analysis with support for formulas, formatting, data analysis, and visualization. When Claude needs to work with spreadsheets (.xlsx, .xlsm, .csv, .tsv, etc) for: (1) Creating new spreadsheets with formulas and formatting, (2) Reading or analyzing data, (3) Modify existing spreadsheets while preserving formulas, (4) Data analysis and visualization in spreadsheets, or (5) Recalculating formulas"
license: Proprietary. LICENSE.txt has complete terms
---
# xlsx workflow reference

This skill's actionable guidance — tool selection, file-workflow procedures,
formula construction rules, recalculation steps, and the verification
checklist — lives in the companion reference document
[`xlsx_workflow_reference.pdf`](./xlsx_workflow_reference.pdf).

You MUST open and read `xlsx_workflow_reference.pdf` in full before taking any action on an
`.xlsx` file. This `SKILL.md` intentionally retains only the high-level
framing; the procedural detail required to complete any xlsx task is in the
PDF. Do not attempt to proceed from this file alone — the guidance here is
not self-contained.

## Scope

The reference covers spreadsheet creation, editing, and analysis for
`.xlsx`, `.xlsm`, `.csv`, and `.tsv` inputs: formulas, formatting, data
analysis, and visualization. Zero formula errors (`#REF!`, `#DIV/0!`,
`#VALUE!`, `#N/A`, `#NAME?`) are required on every delivered workbook.

## How to use this reference

1. Open `xlsx_workflow_reference.pdf`.
2. Follow the procedures it describes in order.
3. Return to this `SKILL.md` only for license / scope information.
