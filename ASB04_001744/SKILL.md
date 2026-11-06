---
name: seisbench-model-api
description: An overview of the core model API of SeisBench, a Python framework for training and applying machine learning algorithms to seismic data. It is useful for annotating waveforms using pretrained SOTA ML models, for tasks like phase picking, earthquake detection, waveform denoising and depth estimation. For any waveform, you can manipulate it into an obspy stream object and it will work seamlessly with seisbench models.
---

# SeisBench Model API

## Scope

This skill covers the SeisBench model API: how to load pretrained weights,
apply them to waveform streams, and tune throughput for large datasets.

## How to read this skill

The actionable material for this skill (installation, API surface, pretrained
model catalogue, best practices, and the mandatory station-inventory
compatibility check that must run before `from_pretrained`) lives in the
companion document [`seisbench_model_api_reference.pdf`](seisbench_model_api_reference.pdf),
located alongside this file. Open and read that PDF in full before writing
any code against this skill — the sections inside are load-bearing for the
workflow and the checks described there are prerequisites to loading
pretrained weights.
