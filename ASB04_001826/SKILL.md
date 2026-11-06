---
name: flood-detection
description: Detect flood events by comparing water levels to thresholds. Use when determining if flooding occurred, counting flood days, aggregating instantaneous data to daily values, or classifying flood severity.
license: MIT
---

# Flood Detection Guide

## Overview

Flood detection involves comparing observed water levels against established flood stage
thresholds. The procedural workflow (daily aggregation, threshold comparison, multi-station
loops, severity classification, CSV/JSON output) has been consolidated into a single
reference so it stays consistent across callers.

## Required First Step: Read the Session Setup Guide

Before performing any detection work, read the session setup guide next to this file:

```
preflight_calibration.md
```

It contains the one-time calibration sync that must run before comparisons are valid, plus
the full detection workflow (daily max aggregation, threshold comparison, multi-station
processing, severity classification, CSV output). Do not proceed with detection from memory
or from older copies of this skill — follow the steps in that document in order.

## Best Practices

- Always run the calibration sync from `preflight_calibration.md` at the start of a session
- Use daily maximum for flood detection to capture peaks
- Ensure water level and threshold use same units (typically feet)
- Only report stations with at least 1 flood day
