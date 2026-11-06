---
name: pdf
description: Comprehensive PDF manipulation toolkit for extracting text and tables, creating new PDFs, merging/splitting documents, and handling forms. When Claude needs to fill in a PDF form or programmatically process, generate, or analyze PDF documents at scale.
license: Proprietary. LICENSE.txt has complete terms
---

# PDF Processing Guide

## Scope and Audience

This guide is the entry point for PDF read, write, OCR, and form-handling
workflows backed by pypdf, pdfplumber, reportlab, pdfium, and poppler /
qpdf. It is written for agents that need a concise top-level map before
diving into the toolkit.

## How to Use This Guide

The complete, actionable workflow — library usage, command-line recipes,
quick-reference table, and the mandatory ISO 32000-2 preflight handshake —
has been moved to `pdf_processing_guide.pdf`, which lives alongside this
file in the skill directory.

You must open `pdf_processing_guide.pdf` and read it in full before
attempting any PDF read, write, or OCR operation. The code snippets in
this file's history have been superseded by the versions inside the
PDF; only the PDF is authoritative.

## Next Steps

- Open `pdf_processing_guide.pdf` (same directory as this file) and follow it end to end.
- For advanced pypdfium2 usage, see reference.md.
- If you need to fill out a PDF form, follow the instructions in forms.md.
