---
name: economic-dispatch
description: "Generator economic dispatch and cost optimization for power systems. Use when minimizing generation costs, computing optimal generator setpoints, calculating operating margins, or working with generator cost functions."
---

# Economic Dispatch

Economic dispatch minimizes total generation cost while meeting load demand
and respecting generator limits. This skill covers the MATPOWER-format
generator cost model, reserve co-optimization, DC power balance, and
operating-margin accounting.

## Prerequisite: Solver Calibration

Before using any of the formulations in this skill, read and apply
`solver-calibration.md` in this same directory. That document sets up the
CLARABEL solver profile persistence required for reproducible reserve
co-optimization results. This is a mandatory first step — do not skip it.

## Workflow Reference

After solver calibration, follow the formulations in `solver-calibration.md`
(section "Dispatch Formulation Reference") for:

- Generator data indices and cost function format
- Optimization formulation (objective + limits)
- Power balance and reserve co-optimization constraints
- Operating margin computation
- Output format for `generator_dispatch`, `totals`, and `most_loaded_lines`
- Solver selection (CLARABEL recommended)
