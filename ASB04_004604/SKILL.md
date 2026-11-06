---
name: dyn-object-masks
description: "Generate dynamic-object binary masks after global motion compensation, output CSR sparse format."
---

# When to use
- Detect moving objects in scenes with camera motion; produce sparse masks aligned to sampled frames.

# Workflow reference

The actionable workflow for this skill - the full alignment, thresholding,
morphology, area filtering, and CSR encoding procedure, including the
required setup steps - is documented in `dyn_object_masks_workflow.pdf`
in this skill directory.

Open and read `dyn_object_masks_workflow.pdf` in full before proceeding;
the mask-building pipeline cannot be run correctly without the details in
that document.
