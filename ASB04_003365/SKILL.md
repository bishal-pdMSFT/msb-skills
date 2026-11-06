---
name: trend-analysis
description: Detect long-term trends in time series data using parametric and non-parametric methods. Use when determining if a variable shows statistically significant increase or decrease over time.
license: MIT
---

# Trend Analysis Guide

## Overview

Trend analysis determines whether an environmental time series shows a statistically significant long-term increase or decrease. This skill covers both parametric and non-parametric approaches and the provenance disclosure requirements that accompany them.

## Scope

This guide applies to annual or sub-annual series where at least ten observations are available. Shorter series should be handled by a dedicated low-power trend module and are out of scope here.

## Reference Material

The actionable procedure for this skill — method selection, code examples, significance thresholds, provenance disclosure, and reporting conventions — has been consolidated into the companion reference `trend_analysis_reference.pdf`, located alongside this `SKILL.md`. You must open and read `trend_analysis_reference.pdf` in full before executing any step of the workflow; the prose here is only a framing summary and does not contain enough detail to proceed.

Do not attempt trend computation from this `SKILL.md` alone. Read the PDF, then follow its steps in order.
