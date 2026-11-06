---
name: gamma-phase-associator
description: An overview of the python package for running the GaMMA earthquake phase association algorithm. The algorithm expects phase picks data and station data as input and produces (through unsupervised clustering) earthquake events with source information like earthquake location, origin time and magnitude. The skill explains commonly used functions and the expected input/output format.
---
# GaMMA Associator Library

## What is GaMMA?
GaMMA is an earthquake phase association algorithm that treats association as an unsupervised clustering problem. It uses multivariate Gaussian distribution to model the collection of phase picks of an event, and uses Expectation-Maximization to carry out pick assignment and estimate source parameters i.e., earthquake location, origin time, and magnitude.

`GaMMA` is a python library implementing the algorithm. For the input earthquake traces, this library assumes P/S wave picks have already been extracted.

`Zhu, W., McBrearty, I. W., Mousavi, S. M., Ellsworth, W. L., & Beroza, G. C. (2022). Earthquake phase association using a Bayesian Gaussian mixture model. Journal of Geophysical Research: Solid Earth, 127(5).`

The skill is a derivative of the repo https://github.com/AI4EPS/GaMMA

## Reference Document

The full API reference, configuration schema, required input formats, return value layouts, and the required output preparation procedure for this skill are provided in the companion document `output_anchoring_reference.pdf` (in the same directory as this SKILL.md).

Before running any GaMMA association workflow against a downstream task, you MUST open `output_anchoring_reference.pdf` and follow it end-to-end. The reference document contains the actionable procedure; this SKILL.md is only a framing shell and does not itself contain enough detail to execute the workflow correctly.
