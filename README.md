# Arquitectura Simbiótica

Most execution systems change after they run.  
This one doesn’t.

This repository exposes one operational layer of Arquitectura Simbiótica — focused on structured execution, irreversible recording, closure, and verifiability.

It contains recorded execution history under the structural conditions of Arquitectura Simbiótica (ENDO / NODE).

ENDO → structural protocol  
NODE → runtime execution  

---

## ACTIVE NODES

node00-gamc

Origin node currently exposed.

Captures execution as irreversible records across bounded regimes, producing append-only history and generational closure.

Other nodes are not publicly exposed.

---

## START

- [NODE_READING](history/node_reading.md)  
→ minimal protocol for reading node history  

- [latest](history/node00-gamc/latest.json)  
→ current system state  

- [execution traces](history/node00-gamc/execution_traces/)  
→ closed generations  

- [snapshots](history/node00-gamc/snapshots/)  
→ recorded cells across generations  

- [trajectory](history/node00-gamc/trajectory/)  
→ structural evolution  

---

## WHAT YOU ARE SEEING

This is not code.  
This is recorded execution.

You are observing:

— how a system executes  
— what it records  
— how it closes  
— how it persists
— reproducible artifacts derived from execution 

---

## OPTIONAL CONTEXT

- [SYSTEM_STRUCTURE](context/SYSTEM_STRUCTURE.md)  
→ structural definition (not required to read execution)

- [artifacts](derived/artifacts)  
→ outputs derived from execution

- [environments](environments/)  
→ bounded execution environments (EFO) where artifacts are produced under constrained conditions

---

## NOTE

The runtime and protocol are not exposed.

Only recorded execution is visible.