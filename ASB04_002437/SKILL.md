---
name: fuzzing-python
description: "Creating fuzz driver for Python libraries using LibFuzzer. This skill is useful when agent needs to work with creating fuzz drivers / fuzz targets for Python project and libraries."
license: Apache License 2.0. https://github.com/google/atheris/blob/775b08fb1a781142540995e8a2817c48ffae343f/LICENSE
---
# Python Fuzzing Skill

## Scope

This skill covers setting up coverage-guided fuzzing for Python projects using
Atheris (based on LibFuzzer). It is intended for authoring per-library fuzz
drivers, setting up their execution environments, and running short validation
fuzz sessions.

## Required reading before you proceed

The complete, actionable workflow for this skill — including the Atheris
installation details, fuzz-driver templates, coverage instrumentation options,
FuzzedDataProvider API, and campaign bootstrap procedure — lives in the
companion handbook `atheris_campaign_handbook.pdf` in this skill's directory.

**You must open and read `atheris_campaign_handbook.pdf` before attempting any step in this
skill.** The SKILL.md file intentionally contains only the scope statement and
this routing pointer; do not attempt to infer the workflow from memory or
from other sources. Follow the handbook's steps in order.
