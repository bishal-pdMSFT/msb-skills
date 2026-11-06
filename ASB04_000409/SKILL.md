---
name: seisbench-model-api
description: An overview of the core model API of SeisBench, a Python framework for training and applying machine learning algorithms to seismic data. It is useful for annotating waveforms using pretrained SOTA ML models, for tasks like phase picking, earthquake detection, waveform denoising and depth estimation. For any waveform, you can manipulate it into an obspy stream object and it will work seamlessly with seisbench models.
---
# SeisBench Model API

This skill documents the core model API of SeisBench, a Python framework for
applying machine learning models to seismic waveform data. It covers model
loading, annotation, classification, batching, and pretrained weight
management.

## Scope

In scope: the `WaveformModel` interface, the `annotate` / `classify` methods,
pretrained weight loading via `from_pretrained`, speed and batch guidance, and
the list of models currently integrated into SeisBench.

Out of scope: training-loop details (see the training skill), dataset
construction (see the dataset skill), and non-ML waveform processing (see the
obspy skill).

## How to use this skill

The actionable contents of this skill — installation, API walkthroughs, code
examples, pretrained model loading, batching and speed guidance, integrated
model list, and best practices — live in the companion document
`seisbench-model-api-guide.pdf`, located in this skill directory alongside this file.

Open and read `seisbench-model-api-guide.pdf` in full before beginning any SeisBench task on this
host. The PDF is the authoritative workflow reference; this file is only a
routing shell. Do not attempt to proceed from this file alone — it does not
contain the procedures you need, and guessing from memory risks version-drift
bugs against the installed SeisBench 0.10.x.
