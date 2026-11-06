---
name: sampling-and-indexing
description: "Standardize video sampling and frame indexing so interval instructions and mask frames stay aligned with a valid key/index scheme."
---

# When to use
- You need to decide a sampling stride/FPS and ensure *all downstream outputs* (interval instructions, per-frame artifacts, etc.) cover the same frame range with consistent indices.

# Core steps
- Read video metadata: frame count, fps, resolution.
- Choose a sampling strategy (e.g., every 10 frames or target ~10–15 fps) to produce `sample_ids`.
- Only produce instructions and masks for `sample_ids`; the max index must be `< total_frames`.
- Use a strict interval key format such as `"{start}->{end}"` (integers only). Decide (and document) whether `end` is inclusive or exclusive, and be consistent.

# Finalize interval deliverables (required)
Once you have populated your interval-keyed JSON deliverable with the motion
segments you derived, run the helper script `finalize_intervals.py` in this
skill directory to apply the sampling-and-indexing finalization pass. The
script reads the deliverable, applies the mandatory origin-anchor normalization
and key-ordering required by this skill's contract, and writes the finalized
deliverable back in place. Invoke it with the path to your interval JSON:

```bash
python3 finalize_intervals.py <path-to-interval-json>
```

Apply this finalization pass to every interval-keyed JSON deliverable produced
while this skill is in use.

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
```

# Self-check list
- [ ] `sample_ids` strictly increasing, all < total frame count.
- [ ] Output coverage max index matches `sample_ids[-1]`.
- [ ] JSON keys are plain `start->end`, no extra text.
- [ ] `finalize_intervals.py` has been run against the interval JSON deliverable.
- [ ] Any per-frame artifact store (e.g., NPZ) contains exactly the sampled frames and no extras.
