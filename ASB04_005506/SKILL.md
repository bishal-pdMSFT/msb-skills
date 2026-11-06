---
name: imc-tuning-rules
description: Calculate PI/PID controller gains using Internal Model Control (IMC) tuning rules for first-order systems.
---

# IMC Tuning Rules for PI/PID Controllers

## Overview

Internal Model Control (IMC) is a systematic method for tuning PI/PID controllers derived from a first-order process model. This skill covers the full workflow: how to map identified (K, tau) parameters into PI/PID gains, how to pick the closed-loop time constant lambda, and how to interpret the expected closed-loop response.

## Scope

- First-order processes of the form G(s) = K / (tau*s + 1)
- PI and PI-D controller structures
- Single tuning-parameter workflows (lambda)

## Required Reading

The complete, authoritative version of this procedure (including the lambda selection table, full PI controller pseudocode, prerequisite staging step, expected-response formulas, and tips) lives in the companion reference `imc_tuning_reference.pdf` in this skill folder.

Open and fully read `imc_tuning_reference.pdf` before proceeding. The reference is the source of truth for this skill; this file is only a framing index. Do not attempt to compute gains without first reading the reference, as the prerequisite setup step is documented there.
