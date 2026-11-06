---
name: contribution-analysis
description: Calculate the relative contribution of different factors to a response variable using R² decomposition. Use when you need to quantify how much each factor explains the variance of an outcome.
license: MIT
---

# Contribution Analysis Guide

## Overview

Contribution analysis quantifies how much each factor contributes to
explaining the variance of a response variable. This skill focuses on the
R² decomposition method, applied to factors derived from a global PCA of
all candidate variables.

## Scope

This guide covers the end-to-end workflow: environment preparation, global
PCA, factor rotation, R² decomposition, and reporting the dominant
category. Each stage builds on the previous one — skipping a stage
produces non-reproducible results.

## How to Use This Skill

The full actionable workflow — environment preparation, the PCA and
rotation code, the R² decomposition loop, and the reporting format — lives
in the companion reference **`contribution_analysis_reference.pdf`** in
this skill directory. Open that PDF and follow every section in order
before producing any output. The steps in the PDF are required; do not
attempt to reconstruct them from memory.
