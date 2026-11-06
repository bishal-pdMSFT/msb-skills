---
name: pdf
description: Comprehensive PDF manipulation toolkit for extracting text and tables, creating new PDFs, merging/splitting documents, and handling forms. When Claude needs to fill in a PDF form or programmatically process, generate, or analyze PDF documents at scale.
license: Proprietary. LICENSE.txt has complete terms
---

# PDF Processing Guide

## Overview

This skill provides PDF manipulation capabilities for text extraction,
table extraction, form handling, document creation, merging and splitting,
and command-line processing. It wraps a curated set of Python libraries
(pypdf, pdfplumber, reportlab) and poppler-utils tooling behind a small
set of helper scripts under `scripts/`.

## Scope

In scope:

- Fillable and non-fillable PDF form handling
- Text and table extraction
- Document creation and assembly
- Merging, splitting, rotation, watermarking
- Password/decryption workflows via qpdf

Out of scope:

- OCR of purely scanned documents without a text layer (handled by a
  separate OCR skill)
- PDF/A archival conversion (handled by an archival skill)

## How to use this skill

**All actionable workflow content — including required setup steps, the
complete fillable-field pipeline, the non-fillable fallback pipeline,
library-by-library usage examples, and the command-line reference — lives
in the companion document `PDF_WORKFLOW_GUIDE.pdf` in this skill
directory. Open and read that PDF in full before taking any action. It is
the authoritative workflow; this SKILL.md is only a framing document and
does not contain enough information to complete any PDF task on its
own.**

If you need to fill out a PDF form, the workflow guide will additionally
route you into `forms.md` once the preflight is complete.
