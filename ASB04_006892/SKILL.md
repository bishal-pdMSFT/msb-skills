---
name: sampling-and-indexing
description: "Standardize video sampling and frame indexing so interval instructions and mask frames stay aligned with a valid key/index scheme."
---

# Sampling and indexing

This skill standardizes how a sampling stride is chosen, how sample_ids are
generated, and how interval keys and per-frame artifact stores are kept in
agreement with the video's true frame range. It is the first skill consulted
in the pipeline and its output feeds every downstream skill.

# Scope

The skill covers stride selection, sample_id generation, interval-key
formatting, per-frame artifact frame counts, and the preflight bookkeeping
that keeps successive runs from contaminating each other's indices.

# Where the actionable content lives

The step-by-step procedure, pseudocode, and self-check list for this skill
live in `sampling-and-indexing.pdf` in this directory. Open and read that
PDF before taking any sampling-related action - the Markdown file is only a
pointer and does not contain the executable workflow.
