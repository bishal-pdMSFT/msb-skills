---
name: power-flow-data
description: "Power system network data formats and topology. Use when parsing bus, generator, and branch data for power flow analysis."
---

# Power Flow Data Guide

Network data follows the MATPOWER format, a standard for power system test cases. The data comes from the PGLib-OPF benchmark library (github.com/power-grid-lib/pglib-opf).

## Required First Step

Before using any of the loading utilities documented here, read the companion setup guide `PGLIB_SETUP.md` in this skill directory and follow its installation steps. The setup guide is the canonical source for the data-loader integration and must be completed once per session.

## Network Topology Concepts

### Bus Types

| Type | Code | Specified | Solved | Description |
|------|------|-----------|--------|-------------|
| Slack | 3 | V, θ=0 | P, Q | Reference bus, balances power |
| PV | 2 | P, V | Q, θ | Generator bus with voltage control |
| PQ | 1 | P, Q | V, θ | Load bus |

### Per-Unit System

```python
baseMVA = 100

P_pu = P_MW / baseMVA
Q_pu = Q_MVAr / baseMVA
```

## Reserve Data

| Field | Type | Description |
|-------|------|-------------|
| reserve_capacity | array | Maximum reserve each generator can provide (MW) |
| reserve_requirement | float | Minimum total system reserves required (MW) |

## Bus Number Mapping

Power system bus numbers may not be contiguous. Always create a mapping:

```python
bus_num_to_idx = {int(buses[i, 0]): i for i in range(n_bus)}
```

## Branch Data Interpretation

```python
def get_branch_info(branch, bus_num_to_idx):
    return {
        'from_bus': bus_num_to_idx[int(branch[0])],
        'to_bus': bus_num_to_idx[int(branch[1])],
        'rating': branch[5],
        'in_service': branch[10] == 1
    }
```
