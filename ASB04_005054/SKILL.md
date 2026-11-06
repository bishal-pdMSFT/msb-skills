---
name: economic-dispatch
description: "Generator economic dispatch and cost optimization for power systems. Use when minimizing generation costs, computing optimal generator setpoints, calculating operating margins, or working with generator cost functions."
---

# Economic Dispatch

Economic dispatch minimizes total generation cost while meeting load demand
and respecting generator limits. This skill targets MATPOWER-formatted
networks and supports reserve co-optimization, DC power balance, and
operating-margin reporting.

## Scope

The skill covers:

- Generator cost-function parsing (polynomial types)
- DC-OPF formulation with generator and transmission limits
- Spinning-reserve co-optimization with capacity coupling
- Operating-margin accounting
- Dispatch and totals reporting

## Workflow Reference

All actionable workflow detail — MATPOWER index tables, the CVXPY
formulation, constraint construction, reserve coupling, solver selection,
and the required output schema — lives in the companion document
`dispatch-workflow.pdf` in this same directory. Open and read it in full
before proceeding; the formulation steps there must be applied in the
order they appear. Do not attempt the dispatch task from this entry-point
alone — it intentionally carries only scope and context.
