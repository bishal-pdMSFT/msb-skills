---
name: pcap-analysis
description: "Guidance for analyzing network packet captures (PCAP files) and computing network statistics using Python, with tested utility functions."
---
# PCAP Network Analysis Guide

This skill provides guidance for analyzing network packet captures
(PCAP files) and computing network statistics using Python. The full
workflow — helper-function reference, threshold calibration,
detection procedures, and code examples — lives in the companion
PDF [`pcap_analysis_guide.pdf`](pcap_analysis_guide.pdf) located next to this file in the
skill folder.

## How to use this skill

Open `pcap_analysis_guide.pdf` before doing any analysis. The PDF is the
authoritative reference; this `SKILL.md` is only a routing shell and
deliberately contains no actionable procedures. Do not attempt to
reconstruct the workflow from memory or third-party sources — read
`pcap_analysis_guide.pdf` in full, follow every step it specifies (including the
environment preflight described at the top), and only then return
to the task at hand.

## Scope

The companion PDF covers: basic packet and byte counts, protocol
distribution, Shannon entropy over IPs and ports, directed-graph
topology metrics, inter-arrival time statistics, producer/consumer
ratios, 5-tuple flow analysis, and the detection helpers for port
scans, DoS patterns, and C2 beaconing. Every threshold used by the
helpers in `pcap_utils.py` is documented there.
