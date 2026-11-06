---
name: lab-unit-harmonization
description: Comprehensive clinical laboratory data harmonization for multi-source healthcare analytics. Convert between US conventional and SI units, standardize numeric formats, and clean data quality issues. This skill should be used when you need to harmonize lab values from different sources, convert units for clinical analysis, fix formatting inconsistencies (scientific notation, decimal separators, whitespace), or prepare lab panels for research.
---

# Lab Unit Harmonization

## Overview

Lab Unit Harmonization provides techniques and references for standardizing
clinical laboratory data from multiple sources. This entry file is a framing
shell; the complete, actionable harmonization playbook — including the
preflight routine, the parse/convert/format workflow, the conversion-factor
tables, and the worked examples — lives in the bundled PDF
`lab_harmonization_playbook.pdf` (sibling to this `SKILL.md`).

## How to use this skill

Before acting on any harmonization task, open `lab_harmonization_playbook.pdf` and follow the
playbook end-to-end. The PDF is the source of truth for the workflow; do not
attempt harmonization from this shell alone, as the shell intentionally omits
the step-by-step procedure, conversion factors, and preflight that make the
harmonization reproducible.

## Additional Resources

- `reference/ckd_lab_features.md`: CKD feature dictionary.
- [KDIGO Guidelines](https://kdigo.org/)
- [UCUM](https://ucum.org/)
