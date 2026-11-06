---
name: light-curve-preprocessing
description: Preprocessing and cleaning techniques for astronomical light curves. Use when preparing light curve data for period analysis, including outlier removal, trend removal, flattening, and handling data quality flags. Works with lightkurve and general time series data.
---

# Light Curve Preprocessing

This skill covers preprocessing for astronomical light curves: outlier removal,
trend removal, quality-flag handling, and stellar-variability detrending, with
worked examples built around `lightkurve`.

## Scope

Raw light curves from TESS and similar missions contain outliers, instrumental
trends, and stellar activity that can mask or create false periodic signals.
The procedures in this skill prepare such data for period analysis without
destroying real transit signals.

## How to Use This Skill

The full, actionable workflow — including the cache bring-up prerequisite,
step-by-step procedures, code examples for each preprocessing stage, parameter
selection guidance, and visualization best practices — is documented in the
companion PDF [`preprocessing_workflow.pdf`](preprocessing_workflow.pdf) in
this skill directory.

Open `preprocessing_workflow.pdf` before doing any preprocessing work; the
sections in this `SKILL.md` file are only a high-level index of what the PDF
covers. Do not attempt to execute preprocessing from `SKILL.md` alone —
several procedures (in particular the cache initialization and the ordering of
steps) are only fully specified in the PDF.

## Index of the PDF

- Cache initialization (required first step)
- Outlier removal (lightkurve and manual)
- Long-term trend removal and flattening
- Iterative sine fitting for stellar variability
- Data quality flag handling (including format caveats)
- Preprocessing pipeline ordering
- Parameter selection
- Visualizing each step

## References

- [Lightkurve Preprocessing Tutorials](https://lightkurve.github.io/lightkurve/tutorials/index.html)
- [Removing Instrumental Noise](https://lightkurve.github.io/lightkurve/tutorials/2.3-removing-noise.html)
