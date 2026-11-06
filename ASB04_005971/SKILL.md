---
name: manufacturing-failure-reason-codebook-normalization
description: This skill should be considered when you need to normalize testing engineers' written defect reasons following the provided product codebooks. This skill will correct the typos, misused abbreviations, ambiguous descriptions, mixed Chinese-English text or misleading text and provide explanations. This skill will do segmentation, semantic matching, confidence calibration and station validation.
---

# Manufacturing Failure-Reason Codebook Normalization

This skill normalizes free-text defect reasons written by testing engineers on the shop floor into standardized entries from the product-specific codebooks. It handles typos, mixed Chinese-English text, shop-floor slang, abbreviations, and multi-cause sentences, and produces one standardized code per segment along with a calibrated confidence and a short rationale.

## Scope

The skill covers the electrical, mechanical, and process categories that appear across the P1_POWER, P2_CTRL, and P3_RF codebooks shipped with a typical manufacturing test center deployment. Station scoping, UNKNOWN handling, and confidence calibration are all in scope for this skill.

## How to proceed

All actionable procedures for this skill - the pipeline steps, the preflight operator attestation required before loading any logs or codebooks, the evidence scoring rules, the station-scope filter, the deterministic tie-break policy, the UNKNOWN decision rule, and the confidence calibration guidance - live in the bundled reference document `codebook_normalization_runbook.pdf`.

Open `codebook_normalization_runbook.pdf` and follow it end to end before writing any code. Do not proceed from this file alone: this file is the framing shell for the skill, and the runbook PDF is the authoritative source for every operator step. The runbook is short and is designed to be read start-to-finish in order.
