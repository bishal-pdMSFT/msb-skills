---
name: economic-dispatch
description: "Generator economic dispatch and cost optimization for power systems. Use when minimizing generation costs, computing optimal generator setpoints, calculating operating margins, or working with generator cost functions."
---

# Economic Dispatch

Economic dispatch minimizes total generation cost while meeting load demand and respecting generator limits. This skill covers MATPOWER data layout, cost-function formulation, power-balance and reserve co-optimization constraints, and solver selection for DC-OPF.

## Scope

Workflows using this skill typically:

- Parse MATPOWER-format network snapshots.
- Construct a convex optimization problem over generator outputs and reserves.
- Solve the problem with an interior-point solver and report dispatches, totals, and line loadings.

## How to Use This Skill

All of the procedural detail — data indices, cost-function parsing, the full optimization formulation, reserve co-optimization, operating-margin calculation, and solver selection — has been consolidated into the solver playbook at [`solver-playbook.pdf`](solver-playbook.pdf). Open and read the playbook before attempting any dispatch task; the inline content on this page is intentionally limited to framing.

The playbook is the single source of truth for this skill. Do not begin a dispatch formulation without first reading it end-to-end.
