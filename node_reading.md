# ENDO — NODE READING

Minimal protocol for reading node execution history.

All observable traces were derived and exported when each generation closed.

---

## Exposed Node

```text
node00-gamc
```

---

## Concepts

### Node

Bounded preservation domain.

Preserves the history of a specific system, process or trajectory.

```text
node00-gamc
```

---

### Cell

Minimal recorded execution unit.

Preserved inside generation snapshots.

---

### Generation

Bounded execution container.

Groups recorded cells and closes under explicit conditions.

```text
gen_0001
gen_0002
gen_0003
```

---

### EFO

Bounded production environment.

Constrains production activity and preserves observable production records.

```text
EFO-01
EFO-02
EFO-03
```

---

## Reading Order

### 1. Did a generation close?

→ [execution_traces](history/node00-gamc/execution_traces/)

Read:

```text
closure.closed
→ closure status

closure.closed_reason
→ condition that triggered closure
(TIME, THRESHOLD, MANUAL, ...)

closure.closed_at
→ closure timestamp

resolution
→ Resolution Cell that closed the generation

integrity
→ integrity verification of the execution trace
```

Answers:

- Did it close?
- Why did it close?
- When did it close?
- Which Resolution Cell closed it?
- Was closure integrity preserved?

---

### 2. What was recorded?

→ [snapshots](history/node00-gamc/snapshots/)

Read:

```text
cells
→ recorded execution units

references
→ relationships between recorded cells

resolution
→ Resolution Cell preserved inside the generation

reentry
→ continuity link with previous generations

index
→ recorded size of the generation

  total_cells
  → number of preserved cells

  seq_global
  → total recorded sequence length
```

Answers:

- Which cells were preserved?
- How many cells were recorded?
- Which references were recorded?
- Which Resolution Cell closed the generation?
- Was continuity carried from previous generations?
- What was the recorded size of the generation?

---

### 3. How did execution evolve?

→ [trajectory](history/node00-gamc/trajectory/)

Trajectory does not show individual events.

It shows aggregate behavior derived from recorded history.

Read:

```text
intra
→  how execution behaved inside a generation

  reference_usage
  → how strongly execution depends on references

  chain_linearity
  → whether recorded history remains linear

inter
→ whether execution expanded or contracted compared to the previous generation

  generation_delta
  → expanding, contracting or stable execution volume

structure
→ whether participation and continuity remained stable over time

  regime_behavior
  → expanding, contracting or stable structural activity

  origin_persistence
  → participation continuity across generations

lineage
→ how far references connect across historical generations

  lineage_max_length
  → longest recorded reference chain

  lineage_max_depth
  → deepest recorded historical continuity

global
→ accumulated node history

  total_generations
  total_cells
```

Answers:

- How did generations evolve?
- What changed between generations?
- What persisted between generations?
- How dependent is execution on references?
- How linear is recorded history?
- How deep is recorded lineage?
- How large is accumulated node history?

---

### 4. What is the latest observable state?

→ [latest](history/node00-gamc/latest/)

Read:

```text
generation
→ latest observable generation

status
→ current closure state

index
→ current generation totals

runtime
→ runtime version that produced the export
```

Answers:

- What is the latest published generation?
- Is it open or closed?
- How many cells exist in the latest generation?
- Which runtime produced the current state?

---

### 5. Was closure reviewed after execution?

Audit exists only when a Resolution Cell requires external continuity review.

→ [audit](history/node00-gamc/audit/)

Read:

```text
status
→ audit result

continuity
→ continuity decision

audit_count
→ total recorded audits

closed_at
→ audit closure timestamp
```

Answers:

- Was an audit performed?
- Was continuity authorized?
- How many audits were recorded?
- What was the final audit status?

---

### 6. Where did production occur?

→ [environments](environments/node00-gamc)

Read:

```text
identity
→ environment identity

manifest
→ environment definition

state
→ final environment state

anchors
→ execution anchors preserved from node history

hashes
→ integrity hashes for preserved records

registry
→ artifacts registered by the environment
```

Answers:

- Which environment executed?
- Under which conditions?
- How did it close?
- Which artifacts were registered?
- Which execution anchors were preserved?

---

## Quick Questions

| Question | Location |
|-----------|-----------|
| Did it close? | execution_traces |
| What was recorded? | snapshots |
| How did it evolve? | trajectory |
| What is current? | latest |
| Was continuity reviewed? | audit |
| Where did production occur? | environments |

---

## Invariants

- Execution history can exist without preserving a production environment.
- Production environments cannot exist without recorded execution history.
- Generations and EFOs are independent structures.
- A generation records execution.
- An EFO constrains production.
- An EFO may span one or multiple generations.
- Closed generations remain observable.
- Closed generations are never modified.

---

All observable layers derive from the same recorded node history.