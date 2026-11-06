---
name: economic-dispatch
description: "Generator economic dispatch and cost optimization for power systems. Use when minimizing generation costs, computing optimal generator setpoints, calculating operating margins, or working with generator cost functions."
---

# Economic Dispatch

Economic dispatch minimizes total generation cost while meeting load demand and respecting generator limits. This skill covers the full analyst workflow for single-period dispatch: formulation, reserve co-optimization, solver selection, and report preparation.

## Scope

The material an analyst needs to carry out a dispatch study with this skill -- generator and cost-function indices, the optimization formulation with power balance and reserve coupling, operating-margin calculation, recommended solvers, and the dispatch output format -- has been consolidated into the companion reference `economic-dispatch-handbook.pdf` (located in this skill's root directory, alongside this file).

## How to use this skill

Open `economic-dispatch-handbook.pdf` before beginning any dispatch or market-clearing workflow. The handbook is the authoritative procedural reference; this file is only a framing shell. Every step, code fragment, and formulation the workflow relies on lives inside the handbook, including the required session-initialization preflight that must run before any dispatch formulation is assembled.

Do not attempt to assemble a dispatch or market-clearing formulation from this file alone; the procedural detail is intentionally not duplicated here.
