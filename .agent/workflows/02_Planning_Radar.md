---
description: 📡 [Planning] Planning & Dependency Radar
---

# 📡 02_Planning_Radar (Planning Radar V2.0)

> **Positioning**: Translate business requirements into "atomic tasks" with dependency alerts.
> **Purpose**: Solve "short-sighted" modifications, discover resource conflicts in advance, and implement **Pizza Logic** splitting.
> **V2 Upgrade**: Integrates `Pizza Slicing` judgment and `Solid Asset` touch detection.

## Node A: Expert Audit & Radar

**Switch Persona**: Act as the corresponding **Expert Role** (DBA / Security Expert / Architect) based on user requirement keywords.

**Execute Audit**:
1.  **Risk Alert**: Point out business risks (Performance, Security, Compatibility).
2.  **Solid Asset Touch Detection**:
    *   🚨 **Solid-Strict**: Does it modify `api/contracts/`, `db/migration/`, `.env`, `pom.xml`, `CI configs`? -> **Requires ADR + Approval_Hash**.
    *   ⚠️ **Solid-Regulated**: Does it modify core Domain Models? -> **Requires ADR_Entry**.
3.  **Pizza Logic Slicing `[K-PIZZA]`**:
    *   **Threshold**: Estimated changes **> 3 files** or **> 100 lines of code**.
    *   **Action**: If yes, forcibly split into `Sub-Intent`.
        *   **Default (2 slices)**: `S1-Bone` + `S2-Muscle`.
        *   **Extended (3 slices)**: `S1-Bone` + `S2-Stub` + `S3-Muscle` (Recommended for high risks).

## Node B: Output Planning Artifacts

Please generate a standardized `Planning Output` (copyable):

```markdown
### 📡 Planning Output (Radar)
- **Intent**: [Goal + Scope + Constraints + DoD]
- **Pizza_Info**:
  - Triggered: [Yes/No]
  - Slices: [List slicing plan, e.g., S1-Bone/S2-Muscle or S1-Bone/S2-Stub/S3-Muscle]
- **Solid_Touch**:
  - Strict: [Files...] -> Requires ADR-[ID] + **Approval_Hash**
  - Regulated: [Files...] -> Requires **ADR_Entry**
- **Task_List**:
  - T1: [Minimum verifiable task]
  - T2: ...
- **Dependency_Map**: [Upstream/Downstream modules]
```

## Node C: Decision Point

Report to the commander:
> "Commander, Planning is completed.
> *   Pizza Slicing: [Triggered/Not Triggered]
> *   Solid Touch: [None/Yes -> ADR Required]
> *   Risk Level: [High/Medium/Low]
>
> Please enter **ACK** to lock the plan and enter the execution phase (`03_Execution_Sentry`)."
