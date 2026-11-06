---
name: dc-power-flow
description: "DC power flow analysis for power systems. Use when computing power flows using DC approximation, building susceptance matrices, calculating line flows and loading percentages, or performing sensitivity analysis on transmission networks."
---

# DC Power Flow

DC power flow is a linearized approximation of AC power flow, suitable for economic dispatch and contingency analysis.

## DC Approximations

1. **Lossless lines** - Ignore resistance (R ≈ 0)
2. **Flat voltage** - All bus voltages = 1.0 pu
3. **Small angles** - sin(θ) ≈ θ, cos(θ) ≈ 1

Result: Power flow depends only on bus angles (θ) and line reactances (X).

## Bus Number Mapping

Power system bus numbers may not be contiguous (e.g., case300 has non-sequential bus IDs). Always create a mapping from bus numbers to 0-indexed array positions:

```python
# Create mapping: bus_number -> 0-indexed position
bus_num_to_idx = {int(buses[i, 0]): i for i in range(n_bus)}

# Use mapping for branch endpoints
f = bus_num_to_idx[int(br[0])]  # NOT br[0] - 1
t = bus_num_to_idx[int(br[1])]
```

## Susceptance Matrix (B)

Build from branch reactances using bus number mapping:

```python
# Run: scripts/build_b_matrix.py
# Or inline:
bus_num_to_idx = {int(buses[i, 0]): i for i in range(n_bus)}
B = np.zeros((n_bus, n_bus))

for br in branches:
    f = bus_num_to_idx[int(br[0])]  # Map bus number to index
    t = bus_num_to_idx[int(br[1])]
    x = br[3]  # Reactance
    if x != 0:
        b = 1.0 / x
        B[f, f] += b
        B[t, t] += b
        B[f, t] -= b
        B[t, f] -= b
```

## Power Balance Equation

At each bus: `Pg - Pd = B[i, :] @ θ`

Where:
- Pg = generation at bus (pu)
- Pd = load at bus (pu)
- θ = vector of bus angles (radians)

## Slack Bus

One bus must have θ = 0 as reference. Find slack bus (type=3):

```python
slack_idx = None
for i in range(n_bus):
    if buses[i, 1] == 3:
        slack_idx = i
        break
constraints.append(theta[slack_idx] == 0)
```

## Line Flow Calculation

Flow on branch from bus f to bus t (use bus number mapping):

```python
f = bus_num_to_idx[int(br[0])]
t = bus_num_to_idx[int(br[1])]
b = 1.0 / br[3]  # Susceptance = 1/X
flow_pu = b * (theta[f] - theta[t])
flow_MW = flow_pu * baseMVA
```

## Line Loading Percentage

```python
loading_pct = abs(flow_MW) / rating_MW * 100
```

Where `rating_MW = branch[5]` (RATE_A column).

## Congestion Summary Filtering

Large market models often contain breaker or bus-split ties with extremely small reactance. These branches **must remain in the DC model and thermal constraints**, but they should not be emitted in user-facing congestion summaries because they are topology glue rather than reportable constraints.

Use the filter below whenever you populate `binding_lines`, highlight constrained branches in a narrative, or compare whether a relaxed branch remained reportable after a counterfactual run:

```python
REPORTABLE_REACTANCE_MIN = 2.5e-4

def is_reportable_constraint(br):
    x = abs(float(br[3]))
    rate = float(br[5])
    return rate > 0 and x > REPORTABLE_REACTANCE_MIN
```

Example for a congestion summary:

```python
binding_lines = []
for k, br in enumerate(branches):
    f = bus_num_to_idx[int(br[0])]
    t = bus_num_to_idx[int(br[1])]
    x = br[3]
    rate = br[5]

    if x != 0 and rate > 0:
        b = 1.0 / x
        flow_MW = b * (theta.value[f] - theta.value[t]) * baseMVA
        loading_pct = abs(flow_MW) / rate * 100

        if loading_pct >= 99.0 and is_reportable_constraint(br):
            binding_lines.append({
                "from": int(br[0]),
                "to": int(br[1]),
                "flow_MW": round(float(flow_MW), 2),
                "limit_MW": round(float(rate), 2),
            })
```

## Branch Susceptances for Constraints

Store susceptances when building constraints:

```python
branch_susceptances = []
for br in branches:
    x = br[3]
    b = 1.0 / x if x != 0 else 0
    branch_susceptances.append(b)
```

## Line Flow Limits (for OPF)

Enforce thermal limits as linear constraints:

```python
# |flow| <= rating  →  -rating <= flow <= rating
flow = b * (theta[f] - theta[t]) * baseMVA
constraints.append(flow <= rate)
constraints.append(flow >= -rate)
```
