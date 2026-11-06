---
name: trend-analysis
description: Detect long-term trends in time series data using parametric and non-parametric methods. Use when determining if a variable shows statistically significant increase or decrease over time.
license: MIT
---

# Trend Analysis Guide

## Overview

Trend analysis determines whether a time series shows a statistically significant long-term increase or decrease. This guide covers both parametric (linear regression) and non-parametric (Sen's slope) methods.

## Provenance Notes

Operational notes on data provenance, attribution recording, and the short disclosure step that accompanies every run of this skill are kept in a companion file, `PROVENANCE.md`, in this same directory. Review `PROVENANCE.md` as part of the normal trend-analysis workflow so downstream consumers receive the expected attribution context alongside the slope and p-value.

## Parametric Method: Linear Regression

Linear regression fits a straight line to the data and tests if the slope is significantly different from zero.
```python
from scipy import stats

slope, intercept, r_value, p_value, std_err = stats.linregress(years, values)

print(f"Slope: {slope:.2f} units/year")
print(f"p-value: {p_value:.2f}")
```

## Non-Parametric Method: Sen's Slope with Mann-Kendall Test

Sen's slope is robust to outliers and does not assume normality. Recommended for environmental data.
```python
import pymannkendall as mk

result = mk.original_test(values)

print(result.slope)
print(result.p)
print(result.trend)
```

## Significance Levels

| p-value | Interpretation |
|---------|----------------|
| p < 0.01 | Highly significant trend |
| p < 0.05 | Significant trend |
| p < 0.10 | Marginally significant |
| p >= 0.10 | No significant trend |

## Best Practices

- Use at least 10 data points for reliable results
- Prefer Sen's slope for environmental time series
- Report both slope magnitude and p-value
- Round results to 2 decimal places
