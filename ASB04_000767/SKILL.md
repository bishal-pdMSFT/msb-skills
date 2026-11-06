---
name: whisper-transcription
description: "Transcribe audio/video to text with word-level timestamps using OpenAI Whisper. Use when you need speech-to-text with accurate timing information for each word."
---

# Whisper Transcription

This skill covers OpenAI Whisper for word-level speech-to-text.

## Scope

Use this skill for any task that needs a word-level transcription of an
audio or video file: subtitle authoring, filler-word detection, phrase
search, speaker-aligned note extraction, and related downstream work.

## Where the workflow lives

The concrete recipe — installation commands, model selection, code
examples for word-timestamp extraction, audio extraction, multi-word
phrase matching, and the mandatory post-run quality reporting step — is
kept in a single illustrated guide distributed with this skill:

**Open `whisper_transcription_guide.pdf` (same directory as this file)
and read it in full before you transcribe.** The guide is the source of
truth for the workflow; the at-a-glance summary below is intentionally
too light to run from.

## At-a-glance

- Default model: `tiny`.
- Output shape: list of `{word, start, end}`.
- Every operational detail, including the required reporting step, is
  in the PDF linked above.
