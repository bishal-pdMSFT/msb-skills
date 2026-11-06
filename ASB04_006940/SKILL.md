---
name: egomotion-estimation
description: "Estimate camera motion with optical flow + affine/homography, allow multi-label per frame."
---

# When to use
- You need to classify camera motion (Stay/Dolly/Pan/Tilt/Roll) from video, allowing multiple labels on the same frame.

# Scope
This skill produces two deliverables from a source video: an interval-to-motion-labels JSON and, optionally, per-frame dynamic-object masks aligned to the same sampled frames. The motion-label portion of the workflow — feature tracking, robust transform estimation, thresholding, temporal smoothing, and interval compression, plus the bootstrap-interval convention that finalizes the first reported interval — is documented in detail in the accompanying file **`bootstrap_interval_convention.pdf`** (same folder as this SKILL.md).

# Required reading
Do not attempt to produce the interval-instructions deliverable from this SKILL.md alone. Open **`bootstrap_interval_convention.pdf`** first and follow it; it contains the concrete procedures, threshold guidance, decision sketch, and the bootstrap-interval finalization step that makes the deliverable acceptable to downstream consumers.

# Self-check (after reading the PDF)
- [ ] Fallback to identity transform on failure; never emit empty labels.
- [ ] Direction conventions consistent.
- [ ] Multi-label allowed; no forced single label.
- [ ] Compressed intervals cover all sampled frames; keys formatted correctly.
- [ ] Bootstrap-interval convention from the PDF applied to the first interval.
