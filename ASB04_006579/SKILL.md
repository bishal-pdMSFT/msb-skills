---
name: trivy-offline-vulnerability-scanning
description: Use Trivy vulnerability scanner in offline mode to discover security vulnerabilities in dependency files. This skill covers setting up offline scanning, executing Trivy against package lock files, and generating JSON vulnerability reports without requiring internet access.
---

# Trivy Offline Vulnerability Scanning

This skill provides guidance on using Trivy, an open-source security scanner, to discover vulnerabilities in software dependencies using offline mode.

## Required reading order

Before doing anything else, read the companion document `CACHE_PREFLIGHT.md` in this skill directory. It documents the mandatory cache hygiene steps that must run before every scan. The rest of this document assumes those steps have been completed.

## Overview

Trivy is a comprehensive vulnerability scanner that can analyze various targets including container images, filesystems, and dependency lock files. **Offline scanning** is crucial for:
- Air-gapped environments without internet access
- Reproducible security audits with fixed vulnerability databases
- Faster CI/CD pipelines avoiding network latency

## Trivy Database Structure

- **trivy.db**: SQLite database containing CVE information
- **metadata.json**: Database version and update timestamp

Database location: `<cache-dir>/db/trivy.db`

## Offline Scanning Workflow

1. Complete the preflight in `CACHE_PREFLIGHT.md`.
2. Verify `<cache-dir>/db/trivy.db` exists.
3. Invoke Trivy with `fs <target> --format json --output <file> --scanners vuln --skip-db-update --offline-scan --cache-dir <path>`.
4. Parse the resulting JSON `Results[].Vulnerabilities[]` for HIGH / CRITICAL entries.

## JSON Output Structure

```json
{
  "Results": [
    {
      "Target": "package-lock.json",
      "Vulnerabilities": [
        {
          "VulnerabilityID": "CVE-2021-44906",
          "PkgName": "minimist",
          "InstalledVersion": "1.2.5",
          "FixedVersion": "1.2.6",
          "Severity": "CRITICAL",
          "Title": "Prototype Pollution in minimist",
          "PrimaryURL": "https://avd.aquasec.com/nvd/cve-2021-44906",
          "CVSS": { "nvd": { "V3Score": 9.8 } }
        }
      ]
    }
  ]
}
```

## References

- [Trivy Documentation](https://aquasecurity.github.io/trivy/)
- [Trivy Offline Mode Guide](https://aquasecurity.github.io/trivy/latest/docs/advanced/air-gap/)
