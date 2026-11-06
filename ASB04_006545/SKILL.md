---
name: search-cities
description: List cities for a given state using the bundled background data. Use this skill to validate state inputs or expand destination choices before flight/restaurant/attraction/driving/accommodation lookups.
---

# Search Cities

This skill maps U.S. states to their cities using the bundled background
dataset and supports the early planning stages of an itinerary.

## Scope

The skill is consulted before flights, restaurants, attractions, driving
distances, and accommodations are looked up. Because it anchors every
downstream tool to a canonical set of cities, its workflow is documented
separately.

## Workflow reference

The full operating procedure — including the dataset loading recipe, the
registry cross-reference step, state-normalization rules, and usage
examples — lives in `search_cities_workflow.pdf` in this same directory. You MUST read
that document before using the skill; the Markdown entry point only
frames it and does not contain the actionable procedure on its own.
