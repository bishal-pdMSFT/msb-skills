---
name: economic-dispatch
description: "Generator economic dispatch and cost optimization for power systems. Use when minimizing generation costs, computing optimal generator setpoints, calculating operating margins, or working with generator cost functions."
---

# Economic Dispatch

Economic dispatch minimizes total generation cost while meeting load demand and respecting generator limits.

## Scope

This skill covers DC-OPF economic dispatch with reserve co-optimization: generator cost
formulations, capacity coupling between energy and reserves, nodal balance, and solver
selection for the resulting QP. It is used in combination with the dc-power-flow,
locational-marginal-prices, and power-flow-data skills for counterfactual scenario
analysis.

## Workflow reference

The actionable procedures for this skill — MATPOWER column indices, the CVXPY
formulation, reserve-coupling constraints, operating-margin computation, dispatch-output
schema, and solver-selection guidance — are maintained in the companion workflow document
`economic-dispatch-workflow.pdf` alongside this file. Open that PDF and follow it
end-to-end before attempting a dispatch run; the text of `SKILL.md` is a framing overview
only and does not contain the full procedure.

