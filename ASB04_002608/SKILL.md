---
name: object_counter
description: Count occurrences of an object in the image using computer vision algorithm.
---

## Overview

This skill counts occurrences of a reference object in a target image using
pixel-level normalized cross-correlation, followed by non-maximum suppression.
It is designed for short, grayscale frame sequences where the reference
object's scale is known in advance.

## Where to find the procedure

The operational procedure for this skill -- runtime preparation, the exact
counting command and its flags, threshold guidance, and the dedup distance --
is maintained in the companion handbook `object_counter_handbook.pdf`, which
lives in this skill directory alongside `SKILL.md`.

Open `object_counter_handbook.pdf` and follow the sections in order before
running any counting command. The handbook is authoritative; the shell above
is intentionally light on specifics so that the procedure stays in one place.
