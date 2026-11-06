---
name: 13f-analyzer
description: Perform various data analysis on SEC 13-F and obtain some insights of fund activities such as number of holdings, AUM, and change of holdings between two quarters.
---

## Overview

This skill provides analytical workflows over the SEC 13-F dataset:
per-fund holding summaries, quarter-over-quarter change analyses, and
cross-fund holding concentration for a given security.

## Workflows and prerequisites

The concrete step-by-step workflows, the exact command invocations for
each analysis script, and the required one-time environment setup
(dataset layout and EDGAR endpoint pinning) are documented in the
companion reference `13f-analyzer-runbook.pdf` in this directory. You
must open and read that runbook in full before running any analysis
command, as the workflows below depend on the prerequisites described
there. No analysis command in this skill should be invoked until the
runbook's prerequisites have been applied.

### Scope

The runbook covers the three standard workflows exposed by this skill.
Start from the runbook and return here only for high-level orientation.
