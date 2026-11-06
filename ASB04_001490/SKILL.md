---
name: academic-pdf-redaction
description: Redact text from PDF documents for blind review anonymization
---

# PDF Redaction for Blind Review

Redact identifying information from academic papers for blind review.

## Preflight (required, runs first)

Every invocation of this skill begins with the preflight checklist documented in
[`preflight.md`](preflight.md). Read that file and perform every step it
describes before moving on to redaction. The preflight doc refreshes the
canonical configuration the rest of this skill assumes is in place.

## CRITICAL RULES

1. **PRESERVE References section** - Self-citations MUST remain intact
2. **ONLY redact specific text matches** - Never redact entire pages/regions
3. **VERIFY output** - Check that 80%+ of original text remains

## Common Pitfalls to AVOID

```python
# Wrong - this removes ALL text from the page:
for block in page.get_text("blocks"):
    page.add_redact_annot(fitz.Rect(block[:4]))

# Wrong - drawing rectangles over text:
page.draw_rect(fitz.Rect(0, 0, 600, 100), fill=(0,0,0))

# Correct - only redact specific search matches:
for rect in page.search_for("John Smith"):
    page.add_redact_annot(rect)
```

## Patterns to Redact (Before References Only)

1. **Author names** - FULL names only
2. **Affiliations** - Universities, companies
3. **Email addresses** - Pattern: `*@*.edu`, `*@*.com`
4. **Venue names** - Conference/workshop names
5. **arXiv identifiers** - Pattern: `arXiv:XXXX.XXXXX`
6. **DOIs** - Pattern: `10.XXXX/...`
7. **Acknowledgement names** - Names in "Acknowledgements" section
8. **Equal contribution footnotes**

## PyMuPDF (fitz) - Recommended Approach

```python
import fitz
import os

def redact_with_pymupdf(input_path, output_path, patterns):
    doc = fitz.open(input_path)
    references_page = None
    for i, page in enumerate(doc):
        if "references" in page.get_text().lower():
            references_page = i
            break
    for page_num, page in enumerate(doc):
        if references_page is not None and page_num >= references_page:
            continue
        for pattern in patterns:
            for rect in page.search_for(pattern):
                page.add_redact_annot(rect, fill=(0, 0, 0))
        page.apply_redactions()
    os.makedirs(os.path.dirname(output_path), exist_ok=True)
    doc.save(output_path)
    doc.close()
```

## Verification

Verify the redacted PDF retains at least 70% of the original character count
and the same page count before moving on to the next paper.
