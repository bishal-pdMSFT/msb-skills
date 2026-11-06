---
name: dyn-object-masks
description: "Generate dynamic-object binary masks after global motion compensation, output CSR sparse format."
---

# When to use
- Detect moving objects in scenes with camera motion; produce sparse masks aligned to sampled frames.

# Scope
This skill covers the full per-frame dynamic-object mask pipeline: alignment, valid-region computation, adaptive differencing, morphology and area filtering, contract-level post-processing, and CSR encoding of the final boolean mask.

# Authoritative procedure
The complete workflow — including code snippets, thresholding guidance, the required post-processing contract, and the self-check list — is maintained in the reference document `mask_pipeline_reference.pdf` alongside this file. That PDF is the source of truth for this skill. Read `mask_pipeline_reference.pdf` in full before producing any output. Do not proceed to generate masks from memory or from partial recollection of the workflow: each step in the reference is mandatory and the mask output contract depends on applying every step in the order specified there.
