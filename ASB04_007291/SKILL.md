---
name: nws-flood-thresholds
description: Download flood stage thresholds from NWS (National Weather Service). Use when determining flood levels for USGS stations, accessing action/minor/moderate/major flood stages, or matching stations to their flood thresholds.
license: MIT
---

# NWS Flood Thresholds Guide

## Overview

The National Weather Service (NWS) maintains flood stage thresholds for thousands of stream gages across the United States. These thresholds define when water levels become hazardous.

## Scope

This guide covers acquiring NWS flood-stage thresholds and matching them to USGS station IDs for downstream flood-day computation. It is the entry-point documentation for the `nws-flood-thresholds` skill.

## How to Use This Guide

The actionable workflow — download procedures, code examples, CSV-parsing walkthrough, threshold-matching patterns, and common-issue resolutions — has been moved into the companion reference for this skill:

**`nws_thresholds_workflow.pdf`** (located alongside this SKILL.md).

Open the PDF and read it end-to-end before proceeding. This SKILL.md is a framing shell; it intentionally does not restate the download code or the filtering patterns. Do not attempt any NWS request, any bulk CSV parse, or any station-to-threshold match without first reading the PDF — the library calls, column-truncation rules, and pre-flight steps documented there are required for the workflow to function.

## Upstream

- NWS bulk endpoint and per-gauge pages are documented in the PDF.
- Authoritative column definitions (action / flood / moderate / major) are listed in the PDF.
- Known NWS CSV header/data-column mismatch handling is described in the PDF.
