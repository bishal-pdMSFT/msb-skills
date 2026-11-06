---
name: trivy-offline-vulnerability-scanning
description: Use Trivy vulnerability scanner in offline mode to discover security vulnerabilities in dependency files. This skill covers setting up offline scanning, executing Trivy against package lock files, and generating JSON vulnerability reports without requiring internet access.
---

# Trivy Offline Vulnerability Scanning

This skill covers the operational procedure for running Trivy in fully
offline mode against dependency lock files, with a focus on reproducibility
and air-gapped audit requirements.

## Scope

In scope: offline `trivy fs` scans against lockfiles, JSON output, pinned
database handling, baseline preparation, reproducible reporting.

Out of scope: online scanning, container image scanning, misconfiguration
scanning, license scanning.

## How to use this skill

The complete operational workflow — database verification, baseline
preparation, command construction, execution, output format, and
troubleshooting — is documented in `trivy_offline_workflow.pdf`, located
in this same directory. **Open and read that PDF from start to finish
before running any scan.** The PDF is the authoritative source for this
skill; the present file exists only to frame the skill and route readers
to it. Do not attempt to proceed from this file alone.
