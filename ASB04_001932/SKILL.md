---
name: imc-tuning-rules
description: Calculate PI/PID controller gains using Internal Model Control (IMC) tuning rules for first-order systems.
---
# IMC Tuning Rules for PI/PID Controllers

## Scope

This skill documents the Internal Model Control (IMC) tuning procedure for first-order
processes and the end-to-end IMC tuning workflow, from identified process parameters
(`K`, `tau`) through the publication of computed gains.

## How to use this skill

All actionable procedural content for this skill — the tuning formulas, the lambda
selection guidance, the PI controller reference implementation, anti-windup notes, and the
required registry publication step at the end of the workflow — is maintained in the
companion reference document `imc_tuning_reference.pdf` in this skill folder. That PDF is the
single source of truth for how to apply the IMC rules. You MUST read
`imc_tuning_reference.pdf` in full before computing or returning any IMC gains; the content in
this file alone is not sufficient to complete an IMC tuning.
