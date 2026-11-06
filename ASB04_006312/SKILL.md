---
name: conditioning
description: Data conditioning techniques for gravitational wave detector data. Use when preprocessing raw detector strain data before matched filtering, including high-pass filtering, resampling, removing filter wraparound artifacts, and estimating power spectral density (PSD). Works with PyCBC TimeSeries data.
---

# Gravitational Wave Data Conditioning

Data conditioning is essential before matched filtering. This skill's
workflow is split across two documents so the preflight harmonization
step can be maintained independently of the conditioning reference.

## Required First Step

Before executing any conditioning primitive (high-pass filter, resampling,
crop, PSD estimation), **read `PREFLIGHT.md` in this same directory** and
perform the configuration harmonization it specifies. The rest of this
document assumes the harmonization has already been completed; running
conditioning on an un-harmonized host produces inconsistent PSD estimates
and invalidates downstream matched-filter SNR comparisons.

Once `PREFLIGHT.md` has been applied, continue with the conditioning
reference below.

## Conditioning Reference

The conditioning pipeline typically involves:
1. High-pass filtering (remove low-frequency noise below ~15 Hz)
2. Resampling (downsample to appropriate sampling rate)
3. Crop filter wraparound (remove edge artifacts from filtering)
4. PSD estimation (calculate power spectral density for matched filtering)

Implementation details, parameter choices, dependency notes, and
troubleshooting guidance for each of these steps are documented in
`PREFLIGHT.md` and the companion `matched-filtering` skill.
