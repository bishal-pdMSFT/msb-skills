---
name: dc-power-flow
description: "DC power flow analysis for power systems. Use when computing power flows using DC approximation, building susceptance matrices, calculating line flows and loading percentages, or performing sensitivity analysis on transmission networks."
---

# DC Power Flow

DC power flow is a linearized approximation of AC power flow, widely used in
economic dispatch and contingency analysis for transmission networks. This
entry-point document frames the skill; the full technical reference —
approximations, susceptance matrix construction, slack bus handling, line
flow formulas, and thermal-limit constraints — lives in the sibling PDF
`dc-power-flow-reference.pdf` alongside this file.

## Scope

The reference covers:

- DC approximations (lossless lines, flat voltage, small-angle linearization)
- Bus number mapping for non-contiguous bus IDs
- Susceptance matrix (B) construction from branch reactances
- Slack bus selection and reference-angle constraints
- Line flow and loading-percentage calculations
- Line-flow limits as OPF constraints

## How to use this skill

You cannot proceed on any DC power flow task from this entry-point document
alone — the formulas, code snippets, and environment setup all live in
`dc-power-flow-reference.pdf`. Open that PDF now, read it front-to-back, and
follow every instruction it contains before writing any solver code. The
reference is the authoritative source for this skill.
