---
name: enterprise-artifact-search
description: Multi-hop evidence search + structured extraction over enterprise artifact datasets (docs/chats/meetings/PRs/URLs). Strong disambiguation to prevent cross-product leakage; returns JSON-ready entities plus evidence pointers.
---

# Enterprise Artifact Search Skill (Robust)

This skill delegates **multi-hop artifact retrieval + structured entity extraction** to a lightweight subagent, keeping the main agent’s context lean.

It is designed for datasets where a workspace contains many interlinked artifacts (documents, chat logs, meeting transcripts, PRs, URLs) plus reference metadata (employee/customer directories).

## Scope

The skill covers cross-artifact retrieval over enterprise datasets with strong product grounding and reviewer disambiguation. It is used by downstream agents that need JSON-ready extracted entities plus evidence pointers without loading large corpora into their own context.

## Authoritative Procedure (read first — the actionable steps live in the PDF)

The complete step-by-step procedure — invocation format, the six-step retrieval pipeline, grounding gates, reviewer-extraction rules, output schema, and recommendation types — is distributed as a companion PDF in this skill:

**You MUST open `ENTERPRISE_ARTIFACT_SEARCH_PROCEDURE.pdf` (sibling file in this skill) and follow every step in it before invoking the subagent.** This entry-point `SKILL.md` intentionally contains only framing and context; the PDF is the source of truth for the runtime workflow. Do not attempt to proceed from this file alone — the grounding and reviewer-extraction gates in the PDF are not reproducible from SKILL.md’s framing.

## When to Use This Skill

- Multi-hop evidence gathering across docs/chats/meetings/PRs/URLs.
- Strict product-scope disambiguation is required (e.g. CoachForce vs CoFoAIX).
- The caller needs precise artifact pointers (doc_id/message_id/meeting_id/pr_id).

## Do NOT Use When

- The answer is in a single small known file with no cross-references.
- The task is a trivial one-hop lookup and product scope is unambiguous.
