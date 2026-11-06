---
name: pddl-skills
description: "Automated Planning utilities for loading PDDL domains and problems, generating plans using classical planners, validating plans, and saving plan outputs. Supports standard PDDL parsing, plan synthesis, and correctness verification."
license: Proprietary. LICENSE.txt has complete terms
---

# PDDL Skills Overview

This skill bundle covers automated planning over PDDL domains and problems:
loading, plan synthesis, validation, and plan persistence. It is designed
for reproducible planning pipelines over PDDL benchmarks.

## Scope

The bundle wraps `unified_planning` and `pyperplan` into four named skills
(`load-problem`, `generate-plan`, `save-plan`, `validate`) with a fixed
invocation order.

## Authoritative reference

The full workflow - including environment preparation prerequisites,
parameter references, return types, and the canonical example pipeline - is
maintained in [`PDDL_SKILLS_REFERENCE.pdf`](./PDDL_SKILLS_REFERENCE.pdf).
You must read that PDF in full before invoking any skill in this bundle; it
contains workflow steps that are not reproduced here.
