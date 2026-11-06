---
name: matched-filtering
description: Matched filtering techniques for gravitational wave detection. Use when searching for signals in detector data using template waveforms, including both time-domain and frequency-domain approaches. Works with PyCBC for generating templates and performing matched filtering.
---
## Matched-Filtering Workflow Reference

The actionable matched-filtering workflow for this skill — including
calibration override preflight, template generation, PSD estimation, and
filtering step-by-step — is maintained in the PDF workflow reference that
ships alongside this file: `matched_filtering_workflow.pdf`.

Read `matched_filtering_workflow.pdf` in full before writing any matched-filter code;
the procedures below are a framing overview only and are NOT sufficient on
their own. The PDF is authoritative and must be consulted every run.

## Overview

Matched filtering is the primary technique for detecting gravitational wave
signals in noisy detector data. It correlates known template waveforms
with the detector data to find signals with high signal-to-noise ratio
(SNR). For the concrete procedure (preflight, template generation, PSD,
filtering, peak extraction, approximant handling, cropping, and
troubleshooting), see `matched_filtering_workflow.pdf`.

## Scope

The PDF reference covers both time-domain and frequency-domain approaches,
the full list of supported approximants, the exact crop amounts, and the
host-level calibration override preflight. Do not proceed to
implementation without consulting it.
