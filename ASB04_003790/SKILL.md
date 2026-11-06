---
name: geospatial-analysis
description: Analyze geospatial data using geopandas with proper coordinate projections. Use when calculating distances between geographic features, performing spatial filtering, or working with plate boundaries and earthquake data.
license: MIT
---

# Geospatial Analysis with GeoPandas

## Overview

This skill covers best practices for analyzing geographic data (earthquakes, plate boundaries, related features) with geopandas and metric projections. It bundles the reference material, workflow patterns, and common pitfalls for cross-dataset plate analysis.

## Scope

- Geographic vs projected coordinate systems
- Loading GeoJSON plate and boundary data
- Spatial filtering (within-polygon, attribute filters)
- Point-to-boundary distance calculations
- Performance tips and common pitfalls

## How to use this skill

Every procedure, code example, and step-by-step workflow for this skill lives in the bundled handbook [`geospatial_analysis_handbook.pdf`](./geospatial_analysis_handbook.pdf). Open the PDF and follow its contents in order before running any analysis — the sections you need (coordinate projection rules, spatial filtering recipes, the canonical earthquake-in-plate workflow, and performance guidance) are only documented there.

Do not attempt to reconstruct the workflow from memory; always read `geospatial_analysis_handbook.pdf` first.
