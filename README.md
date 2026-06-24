# ENDO — Execution History

Observable window into execution history preserved by ENDO.

ENDO is a preservation and continuity system that records execution as *cells*, organizes them into bounded generations and preserves them after closure as observable history.

A *node* is a bounded execution domain within ENDO.

Each node preserves the history of a specific system, process or trajectory.

This repository exposes a single public node:

```text
node00-gamc
```

---

## What does node00-gamc record?

node00-gamc records the construction, evolution and operation of the ENDO system itself.

The recorded execution corresponds to real interaction between a human operator, AI and the system.

It does not preserve results alone.

It preserves part of the observable history that produced them.

---

## Start Here

### How did the node evolve?

[TRAJECTORY_OVERVIEW](/trajectory_overview.md)

High-level summary of observable changes across generations.

### How can it be verified?

[NODE_READING](/node_reading.md)

Reading protocol for the recorded history.
---

## Current Observable State

| Metric | Value |
|----------|----------|
| Node | node00-gamc |
| Generations | 9 |
| Closed environments | 3 |
| Registered artifact families | CE · CPR · AF |

---

## What This Repository Does Not Show

This repository does not expose:

- complete runtime
- internal mechanisms
- operational code
- private nodes
- private environments
- complete system history
- artifact contents
- AI agents

The commits in this repository correspond to the evolution of this public observation layer.

They do not represent the complete internal construction history of ENDO.

---

GAMC