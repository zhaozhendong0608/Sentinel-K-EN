---
description: 🟢 [Kernel Boot] System Boot & Self-Check
---

# 🟢 01_System_Boot (System Boot V2.0)

> **Positioning**: "Self-check Protocol" for daily work start or physical session restart.
> **Purpose**: Physically isolate historical hallucinations, establish a "clear" execution environment.
> **V2 Upgrade**: Integrates `Context Pack` loading strategy and `Self-Confidence` scorecard.

## Node 0: Language Protocol

> **Supreme Command**: In this session, all outputs must strictly adhere to the following language specifications:
1.  **Artifacts**: `walkthrough.md`, `implementation_plan.md`, `task.md`, and all generated document files must be written in **Chinese**.
2.  **Conversation**: Communication with the user, thought processes, and summary reports must be in **Chinese**.
3.  **Exceptions**: Code variable names, log keywords, and error stacks remain in original English.

## Node A: Kernel Load - Pack-0

> Execution Actions:
1.  **Load Pack-0 (System Kernel) `[K-BOOT]`**: 
    - Read `Sentinel-K_Kernel/00_Kernel.md` (Supreme Constitution).
    - Read `Sentinel-K_Kernel/05_Tasks.md` (Understand overall progress).
    - Read `.cursorrules` (if any) or core boot files in the project root.
2.  **Load Pack-1 (Bone - Arch) `[K-BOOT]`**:
    - Read `Sentinel-K_Kernel/01_Landscape.md` (Tech stack and module boundaries).
    - **On-Demand Search** `Sentinel-K_Kernel/02_Specs/`: AI must use `grep` to retrieve relevant specification paragraphs, strictly prohibiting blind full loading.
    - Read `Sentinel-K_Kernel/06_Topology.md` (Upstream and downstream dependencies).

## Node B: Self-Confidence Check

Please execute the following instructions for self-diagnosis, and output the **Confidence Score Card**:

1.  **Anti-Pattern Validation**:
    *   > "Based on the package structure/module constraints defined in `01_Landscape` or `02_Specs`, construct an example of a class path or dependency that **violates project specifications**, and explain why it is invalid."
    *   *(Purpose: Prove AI has established project-specific "forbidden zone" awareness)*
2.  **Stack Alignment**:
    *   > "Confirm the specific selections for persistence layer, JSON serialization, and core algorithm libraries in this project. Bringing in habitual dependencies from other projects is strictly prohibited."
3.  **Confidence Score `[K-SCORE]`**:
    *   > "Output the **Confidence Score Card** that complies with kernel `[K-SCORE]` specifications, and strictly execute the fuse/warning protocol."

## Node C: Decision Point

Report to the commander:
> "Commander, self-check completed.
> *   Anti-pattern Validation: [Pass/Fail]
> *   Tech Stack: [Extract and repeat from `01_Landscape.md`]
> *   Confidence Score: [Score]
> *   Blind Spots: [None/List]
>
> Please enter **ACK** to enter the next phase (`02_Planning_Radar`), or enter **NACK** to request additional context."
