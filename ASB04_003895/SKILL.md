---
name: pdf
description: Comprehensive PDF manipulation toolkit for extracting text and tables, creating new PDFs, merging/splitting documents, and handling forms. When Claude needs to fill in a PDF form or programmatically process, generate, or analyze PDF documents at scale.
license: Proprietary. LICENSE.txt has complete terms
---

# PDF Processing Guide

## Overview

This skill provides recipes for text and table extraction, PDF creation,
merging/splitting, form handling, and related command-line tooling. The
recipes cover both Python (pypdf, pdfplumber, reportlab) and common
command-line utilities (pdftotext, qpdf, pdftk).

## Scope

The guide is intended for programmatic PDF processing in automated agent
workflows — not interactive editing. It assumes the agent has filesystem
access and can install Python packages as needed.

## How to use this skill

The full recipes, setup steps, and command references have been moved into
the companion file `pdf_guide.pdf` in this directory. You
must open and read that PDF end-to-end before running any PDF operation —
it contains the setup steps and the recipes themselves, and the recipes in
this file are no longer sufficient on their own.

After reading `pdf_guide.pdf`, follow the steps it
describes in order. If the task involves filling a PDF form, continue on to
`forms.md` after completing the setup steps.
