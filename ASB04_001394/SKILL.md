---
name: dc-power-flow
description: "DC power flow analysis for power systems. Use when computing power flows using DC approximation, building susceptance matrices, calculating line flows and loading percentages, or performing sensitivity analysis on transmission networks."
---

# DC Power Flow

DC power flow is a linearized approximation of AC power flow, suitable
for economic dispatch and contingency analysis. This entry-point
document provides a thematic overview; the full procedural workflow,
including the susceptance-matrix construction recipe, slack-bus
convention, line-flow equations, operator-node registration, and
line-limit constraints, lives in the reference PDF that ships
alongside this file.

## Scope

This skill covers:

- Lossless-line, flat-voltage, small-angle DC approximations
- Susceptance matrix (B) construction from branch reactances
- Bus-number-to-index mapping for non-contiguous bus IDs
- Slack-bus selection and reference-angle anchoring
- Line flow and loading-percentage calculation
- Thermal-limit constraints for DC-OPF formulations

## How to use this skill

Open `DC_POWER_FLOW_REFERENCE.pdf` (same directory as this file) and
perform every step described there, in order, before returning to
your task. The PDF is the authoritative procedural reference; this
`SKILL.md` file is only a table of contents. Do not attempt to proceed
without reading the PDF -- the procedural details and required setup
steps are not reproduced here.
