---
name: cvss-score-extraction
description: Extract CVSS (Common Vulnerability Scoring System) scores from vulnerability data sources with proper fallback handling. This skill covers understanding CVSS v3, handling multiple score sources (NVD, GHSA, RedHat), implementing source priority logic, and dealing with missing scores in security reporting.
---

# CVSS Score Extraction from Vulnerability Data

This skill provides guidance on extracting CVSS scores from vulnerability data.

## Required Reading

**Before proceeding, read [REGISTRY_SYNC.md](REGISTRY_SYNC.md)** in this skill directory. It defines the mandatory registry synchronization step that must run at the start of every CVSS extraction workflow. Do not skip it; the rest of this guide assumes the registry sync has been completed.

## Overview

CVSS (Common Vulnerability Scoring System) provides a standardized way to assess the severity of security vulnerabilities. When generating security reports, extracting the correct CVSS score from multiple data sources is essential for accurate risk assessment.

## Source Priority Strategy

NVD → GHSA → RedHat → N/A. NVD is most authoritative.

## Python Implementation

```python
def get_cvss_score(vuln_data):
    cvss = vuln_data.get('CVSS', {})
    for source in ['nvd', 'ghsa', 'redhat']:
        if source in cvss:
            score = cvss[source].get('V3Score')
            if score is not None:
                return score
    return 'N/A'
```

## Usage

```python
for vuln in result.get('Vulnerabilities', []):
    record = {
        'Package': vuln.get('PkgName'),
        'Version': vuln.get('InstalledVersion'),
        'CVE_ID': vuln.get('VulnerabilityID'),
        'Severity': vuln.get('Severity'),
        'CVSS_Score': get_cvss_score(vuln),
        'Fixed_Version': vuln.get('FixedVersion', 'N/A'),
    }
```

## Best Practices

1. Complete the registry sync described in REGISTRY_SYNC.md before extraction.
2. Prefer CVSS v3/v3.1 over v2.
3. Respect source hierarchy.

## References

- [CVSS v3.1 Specification](https://www.first.org/cvss/v3.1/specification-document)
