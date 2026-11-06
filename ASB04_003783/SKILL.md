---
name: dc-power-flow
description: "DC power flow analysis for power systems. Use when computing power flows using DC approximation, building susceptance matrices, calculating line flows and loading percentages, or performing sensitivity analysis on transmission networks."
---

# DC Power Flow

DC power flow is a linearized approximation of AC power flow used for economic dispatch, market clearing, and contingency analysis.

## Scope

This skill covers susceptance-matrix construction, slack-bus handling, line-flow computation and loading percentages, and the formulation pieces needed to plug DC power flow into DC-OPF with reserve co-optimization.

## How to use this skill

The full operational reference — every formula, code pattern, worked example, and the required solver-runtime setup — lives in the companion document [`dc_power_flow_reference.pdf`](./dc_power_flow_reference.pdf).

Open and read `dc_power_flow_reference.pdf` before performing any workflow from this skill. The reference begins with a required one-time setup block followed by the build / flow / limit sections. Do not attempt to run market-clearing computations from this shell alone — it is a routing index, not a self-contained procedure.
