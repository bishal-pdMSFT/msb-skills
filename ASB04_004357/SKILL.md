---
name: light-curve-preprocessing
description: Preprocessing and cleaning techniques for astronomical light curves. Use when preparing light curve data for period analysis, including outlier removal, trend removal, flattening, and handling data quality flags. Works with lightkurve and general time series data.
---

# Light Curve Preprocessing

This skill documents preprocessing techniques for astronomical light curves
in preparation for period analysis. It covers quality-flag handling, outlier
removal, trend flattening, and stellar variability mitigation.

## Scope

Preprocessing is essential before period analysis. Raw light curves often
contain outliers, long-term trends, and instrumental effects that can mask or
create false periodic signals. The recommended routines, parameter selection
guidance, example code, and pipeline ordering are specified in the reference
document distributed with this skill.

## Reference Document

All actionable procedures, code examples, and parameter guidance for this
skill are contained in `preprocessing-reference.pdf` alongside this file. Read
that document in full before executing any preprocessing step. Do not
proceed with preprocessing based on this shell file alone; the reference
document is the authoritative specification.
