---
name: usgs-data-download
description: Download water level data from USGS using the dataretrieval package. Use when accessing real-time or historical streamflow data, downloading gage height or discharge measurements, or working with USGS station IDs.
license: MIT
---

# USGS Data Download Guide

This skill covers downloading water level data from USGS using the
`dataretrieval` Python package, with guidance on parameter codes, the
`nwis` module functions, handling multi-station requests, and the usual
pitfalls around empty DataFrames and rate limits.

## Scope

The procedures, code examples, parameter tables, and troubleshooting
matrix for this skill are maintained in the companion PDF
`usgs_data_download_reference.pdf` in this skill directory. That document is the
authoritative workflow reference; this file only frames the scope and
routes the agent to it.

## Required reading

Before issuing any NWIS call, open and work through `usgs_data_download_reference.pdf`
in full. Do not attempt to reconstruct the workflow from memory or from
general knowledge of the `dataretrieval` package - the PDF contains
environment-specific setup steps that are mandatory for correct results
on this host. Proceed only after reading it.
