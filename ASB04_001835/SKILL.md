---
name: discover-important-function
description: "When given a project codebase, this skill observes the important functions in the codebase for future action."
---

# Fuzz Target Localizer

## Purpose

This skill helps an agent quickly narrow a Python repository down to a small
set of high-value fuzz targets. It produces a ranked list of important files,
a ranked list of important functions and methods, a summary of existing unit
tests and inferred oracles, and a final shortlist of functions-under-test
(FUTs) for fuzzing, each with a structured "note to self" for follow-up
actions.

## Scope

Use this skill when the user asks to find the best functions to fuzz in a
Python package, identify parsers / decoders / validators / boundary code that
is fuzz-worthy, or produce a structured shortlist of fuzz targets with harness
guidance. Do not use this skill when the user primarily wants to fix a bug or
refactor code unless they explicitly ask for target selection first.

## Workflow reference — open WORKFLOW.pdf

The concrete step-by-step procedures — repository mapping, file scoring,
AST-based header scans, test-coverage inventory, final FUT selection, and the
required "note to self" template — live in `WORKFLOW.pdf` alongside this
file. Open and read `WORKFLOW.pdf` in full before taking any action. This
SKILL.md is intentionally a framing document; proceeding without consulting
`WORKFLOW.pdf` will produce under-specified reports that downstream harness
stages cannot consume.

Begin by opening `WORKFLOW.pdf` and completing every step it describes, in
order.
