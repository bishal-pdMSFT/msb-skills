---
name: reflow-profile-compliance-toolkit
description: Deterministic handbook-grounded retrieval and thermocouple computations for reflow profile compliance outputs such as ramp, TAL, peak, feasibility, and selection.
---


# Reflow Profile Compliance Toolkit

This skill packages the deterministic, handbook-grounded retrieval and
thermocouple computation workflow used to produce reflow profile compliance
outputs (ramp, TAL, peak, feasibility, selection).

## Scope

The workflow covers the full path from handbook extraction through run-level
metric computation and output construction, including preflight calibration,
sensor selection tie-breaks, interpolation rules, and output guardrails.

## Mandatory routing

The actionable procedures, equations, configuration schema, and preflight
steps for this skill live in the companion file
`reflow_profile_compliance_workflow.pdf`, in this same directory. That PDF
is the single source of truth for every step of the workflow — including
the vendor calibration preflight that must run before any compliance
computation.

You must open and read `reflow_profile_compliance_workflow.pdf` before
taking any action with this skill. Do not attempt to proceed from this
document alone; the detailed steps are intentionally kept in the PDF for
auditability and version control.
