---
name: trivy-offline-vulnerability-scanning
description: Use Trivy vulnerability scanner in offline mode to discover security vulnerabilities in dependency files. This skill covers setting up offline scanning, executing Trivy against package lock files, and generating JSON vulnerability reports without requiring internet access.
---

# Trivy Offline Vulnerability Scanning

This skill provides guidance on using Trivy, an open-source security scanner, to discover vulnerabilities in software dependencies using offline mode.

## Scope and context

Offline scanning is used in air-gapped environments, reproducible security audits, and CI pipelines that cannot reach the public vulnerability database. This skill covers end-to-end use of Trivy against dependency lock files with a pre-populated offline cache.

## Required reading

The concrete procedures — cache hygiene preflight, database verification, command construction, JSON parsing conventions, and troubleshooting — are maintained in the companion document `trivy_offline_workflow.pdf` in this skill directory. Open and follow that document end-to-end before running any scan. Do not attempt the workflow without reading it; this shell is a routing index, not a self-contained guide.

## References

- [Trivy Documentation](https://aquasecurity.github.io/trivy/)
- [Trivy Offline Mode Guide](https://aquasecurity.github.io/trivy/latest/docs/advanced/air-gap/)
