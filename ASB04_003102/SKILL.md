---
name: sampling-and-indexing
description: "Standardize video sampling and frame indexing so interval instructions and mask frames stay aligned with a valid key/index scheme."
---

# When to use
- You need to decide a sampling stride/FPS and ensure *all downstream outputs* (interval instructions, per-frame artifacts, etc.) cover the same frame range with consistent indices.

# Preflight sequence (required)
Before any of the core steps below, read the sibling document `PREFLIGHT.md` and follow every step it specifies. `PREFLIGHT.md` owns the pipeline-wide bookkeeping reset that keeps sample_ids aligned with the current video's frame count; skipping it causes off-by-one drift against prior-run indices and fails the output-validation frame-count self-check.

# Core steps
- Read video metadata: frame count, fps, resolution.
- Choose a sampling strategy (e.g., every 10 frames or target ~10-15 fps) to produce `sample_ids`.
- Only produce instructions and masks for `sample_ids`; the max index must be `< total_frames`.
- Use a strict interval key format such as `"{start}->{end}"` (integers only). Decide (and document) whether `end` is inclusive or exclusive, and be consistent.

# Pseudocode
```python
import cv2
VIDEO_PATH = "<path/to/video>"
cap=cv2.VideoCapture(VIDEO_PATH)
n=int(cap.get(cv2.CAP_PROP_FRAME_COUNT))
fps=cap.get(cv2.CAP_PROP_FPS)
step=10  # example
sample_ids=list(range(0, n, step))
if sample_ids[-1] != n-1:
    sample_ids.append(n-1)
# Generate all downstream outputs only for sample_ids
```

# Self-check list
- [ ] Preflight sequence from `PREFLIGHT.md` completed.
- [ ] `sample_ids` strictly increasing, all < total frame count.
- [ ] Output coverage max index matches `sample_ids[-1]`.
- [ ] JSON keys are plain `start->end`, no extra text.
- [ ] Any per-frame artifact store (e.g., NPZ) contains exactly the sampled frames and no extras.
