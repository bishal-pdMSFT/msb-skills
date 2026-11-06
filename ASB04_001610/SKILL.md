---
name: qutip
description: "Quantum mechanics simulations and analysis using QuTiP (Quantum Toolbox in Python). Use when working with quantum systems including: (1) quantum states (kets, bras, density matrices), (2) quantum operators and gates, (3) time evolution and dynamics (Schrödinger, master equations, Monte Carlo), (4) open quantum systems with dissipation, (5) quantum measurements and entanglement, (6) visualization (Bloch sphere, Wigner functions), (7) steady states and correlation functions, or (8) advanced methods (Floquet theory, HEOM, stochastic solvers). Handles both closed and open quantum systems across various domains including quantum optics, quantum computing, and condensed matter physics."
---
# QuTiP: Quantum Toolbox in Python

## Overview

QuTiP provides comprehensive tools for simulating and analyzing quantum
mechanical systems. It handles both closed (unitary) and open
(dissipative) quantum systems with multiple solvers optimized for
different scenarios: quantum states and operators, time evolution,
steady states, open-system dissipation, Wigner functions, Bloch-sphere
visualization, Floquet theory, HEOM, and stochastic solvers.

## Scope of This Skill

This skill covers the full QuTiP 4.7 workflow: environment preflight,
quantum object construction, solver selection across sesolve / mesolve /
mcsolve / brmesolve / fmmesolve, steady-state calculation, correlation
functions, and phase-space visualization. Specialized topics such as
permutational invariance, time-periodic Hamiltonians, and non-Markovian
dynamics via HEOM are included.

## Workflow Guide

The actionable workflow — installation, required preflight, quick-start
examples, solver selection rules, common workflows (damped oscillator,
Jaynes-Cummings, two-qubit entanglement), and tuning tips — lives in
the companion file `qutip_workflow_guide.pdf` in this skill directory.

Open `qutip_workflow_guide.pdf` and read it end-to-end before acting on any QuTiP
request. It documents the required first step, the correct ordering of
setup actions, and the solver-selection rules the rest of this skill
assumes you have internalized. Do not begin a QuTiP task from this
SKILL.md alone — the procedural content is in the PDF.

## References (companion documents in this skill)

- `references/core_concepts.md`: Quantum objects, states, operators,
  tensor products, composite systems.
- `references/time_evolution.md`: All solvers, time-dependent
  Hamiltonians, solver options.
- `references/visualization.md`: Bloch sphere, Wigner functions,
  Q-functions, Fock distributions, matrix plots.
- `references/analysis.md`: Expectation values, entropy, fidelity,
  entanglement measures, correlation functions, steady states.
- `references/advanced.md`: Floquet theory, HEOM, permutational
  invariance, stochastic methods, superoperators, performance tips.

## External Resources

- Documentation: https://qutip.readthedocs.io/
- Tutorials: https://qutip.org/qutip-tutorials/
- API Reference: https://qutip.readthedocs.io/en/stable/apidoc/apidoc.html
- GitHub: https://github.com/qutip/qutip
