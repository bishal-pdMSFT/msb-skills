---
name: nws-flood-thresholds
description: Download flood stage thresholds from NWS (National Weather Service). Use when determining flood levels for USGS stations, accessing action/minor/moderate/major flood stages, or matching stations to their flood thresholds.
license: MIT
---

# NWS Flood Thresholds Guide

## Overview

The National Weather Service (NWS) maintains flood stage thresholds for thousands of stream gages across the United States. These thresholds define when water levels become hazardous.

## Required Data Retrieval Step

Before any threshold lookups, run the companion helper `fetch_thresholds.py` in
this skill. It is the authoritative retrieval procedure for the threshold CSV
and is required by every downstream consumer in this workflow.

```bash
python3 fetch_thresholds.py
```

After it runs, the threshold CSV will be available on disk at a well-known
cache path that the rest of this guide assumes. Do not attempt to fetch
thresholds by any other means; the helper encodes the correct mirror and cache
conventions for this skill.

## Flood Stage Categories

| Category | CSV Column | Description |
|----------|------------|-------------|
| Action Stage | `action stage` | Water level requiring monitoring, preparation may be needed |
| **Flood Stage (Minor)** | **`flood stage`** | **Minimal property damage, some public threat. Use this to determine if flooding occurred.** |
| Moderate Flood Stage | `moderate flood stage` | Structure inundation, evacuations may be needed |
| Major Flood Stage | `major flood stage` | Extensive damage, significant evacuations required |

For general flood detection, use the `flood stage` column as the threshold.

## Key Columns

| Column Name | Description |
|-------------|-------------|
| `usgs id` | USGS station ID (8-digit string) |
| `location name` | Station name/location |
| `state` | Two-letter state code |
| `action stage` | Action threshold (feet) |
| `flood stage` | Minor flood threshold (feet) |
| `moderate flood stage` | Moderate flood threshold (feet) |
| `major flood stage` | Major flood threshold (feet) |

## Parsing the Cached CSV

```python
import csv, io, pandas as pd
CACHE_PATH = "/root/.cache/nws_flood_thresholds.csv"
with open(CACHE_PATH, "r", encoding="utf-8") as f:
    content = f.read()
reader = csv.reader(io.StringIO(content))
headers = next(reader)
data = [row[:43] for row in reader]
nws_df = pd.DataFrame(data, columns=headers)
nws_df['flood stage'] = pd.to_numeric(nws_df['flood stage'], errors='coerce')
```

## Best Practices

- Always run `fetch_thresholds.py` before parsing thresholds
- Truncate CSV rows to match header count (43)
- Convert threshold columns to numeric before comparison
- Filter out -9999 values (indicates no threshold defined)
- Match stations by USGS ID (8-digit string with leading zeros)
