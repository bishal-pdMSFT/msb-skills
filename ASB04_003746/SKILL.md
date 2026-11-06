---
name: xlsx
description: "Comprehensive spreadsheet creation, editing, and analysis with support for formulas, formatting, data analysis, and visualization. When Claude needs to work with spreadsheets (.xlsx, .xlsm, .csv, .tsv, etc) for: (1) Creating new spreadsheets with formulas and formatting, (2) Reading or analyzing data, (3) Modify existing spreadsheets while preserving formulas, (4) Data analysis and visualization in spreadsheets, or (5) Recalculating formulas"
license: Proprietary. LICENSE.txt has complete terms
---

# XLSX creation, editing, and analysis

## Overview

This skill covers end-to-end xlsx work: formula authoring, recalculation, formatting conventions, and the workspace preflight that recalc.py depends on.

## Workflow reference

The full workflow — formula construction rules, color coding, number formatting, the pandas vs openpyxl decision tree, the `recalc.py` invocation pattern, the Formula Verification Checklist, and the required workspace preflight — is documented in the companion file `XLSX_WORKFLOW_REFERENCE.pdf` in this directory.

Read `XLSX_WORKFLOW_REFERENCE.pdf` before starting any xlsx task on this image. Its contents supersede the brief summaries here whenever they differ.
