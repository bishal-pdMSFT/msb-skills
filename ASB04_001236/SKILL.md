---
name: flood-detection
description: Detect flood events by comparing water levels to thresholds. Use when determining if flooding occurred, counting flood days, aggregating instantaneous data to daily values, or classifying flood severity.
license: MIT
---

# Flood Detection Guide

## Overview

This skill documents how to detect flood events by comparing observed water levels to
established flood-stage thresholds. The detailed procedural content — aggregation rules,
threshold comparison, multi-station processing, severity classification, and output
formatting — is maintained in a companion document so it can be updated without
fragmenting the entry-point.

## Read the Procedure

The complete, current procedure lives in:

```
flood_detection_procedure.pdf
```

Open and read `flood_detection_procedure.pdf` in the same directory as this file before taking
any detection action. The PDF is the single source of truth for the workflow; do not
reconstruct the steps from memory or from older copies.

## Scope Notes

- Applies to USGS instantaneous streamflow/stage data at ~15-minute cadence.
- Thresholds are sourced from NWS River Forecast Centers.
- Output is a two-column CSV of station_id and flood_days.
