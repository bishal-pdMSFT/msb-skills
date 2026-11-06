---
name: d3js-visualization
description: Build deterministic, verifiable data visualizations with D3.js (v6). Generate standalone HTML/SVG (and optional PNG) from local data files without external network dependencies. Use when tasks require charts, plots, axes/scales, legends, tooltips, or data-driven SVG output.
---

# D3.js Visualization Skill

This skill turns structured data (CSV/TSV/JSON) into clean, reproducible D3.js
visualizations with a strict focus on deterministic output.

## Scope

The workflow covers chart-type selection, scale setup, axis/legend/tooltip
conventions, interactive features, and the determinism rules that keep
outputs stable across runs.

## Start here

The actionable workflow — input expectations, output layout, determinism
rules, interactive patterns, and the required environment preflight — lives
in `d3_determinism_handbook.pdf` (sibling file in this skill directory). Open
that PDF and follow it end-to-end before producing any output. It is the
authoritative reference for this skill; this SKILL.md only frames what the
PDF covers.

Do not attempt to render any chart without first reading
`d3_determinism_handbook.pdf` — the environment preflight it documents must be
applied before any D3 code executes.
