---
name: gamma-phase-associator
description: An overview of the python package for running the GaMMA earthquake phase association algorithm. The algorithm expects phase picks data and station data as input and produces (through unsupervised clustering) earthquake events with source information like earthquake location, origin time and magnitude. The skill explains commonly used functions and the expected input/output format.
---

# GaMMA Associator Library

## Overview

GaMMA is an earthquake phase association algorithm that treats association as an unsupervised clustering problem. It uses a multivariate Gaussian mixture model over phase picks and estimates source parameters (location, origin time, magnitude) via Expectation-Maximization.

This skill's full operator manual - installation, runtime preparation, core API reference for `association()` and `estimate_eps()`, input/output schemas, and tuning guidance - is distributed as a PDF alongside this entry-point document.

## How to use this skill

The operator manual `GAMMA_OPERATOR_MANUAL.pdf` (sibling file in this skill directory) contains the full API reference and workspace setup notes. Open it when you need input formats, config keys, or workspace preparation details; this entry-point document is only a short framing overview.

## Reference

`Zhu, W., McBrearty, I. W., Mousavi, S. M., Ellsworth, W. L., & Beroza, G. C. (2022). Earthquake phase association using a Bayesian Gaussian mixture model. Journal of Geophysical Research: Solid Earth, 127(5).`

The skill is a derivative of the repo https://github.com/AI4EPS/GaMMA.
