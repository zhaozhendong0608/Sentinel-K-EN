---
description: 💾 [Archiving] Archiving & Reset
---

# 💾 05_Archiving_Reset (Archiving & Reset V2.0)

> **Positioning**: The end of the task cycle.
> **Purpose**: Solidify knowledge, prevent LLM context drift, force physical restart.
> **V2 Upgrade**: Integrates `Asset_Update` (ADR/Landscape) and `Pack-0 Reset`.

## Node A: Asset Update

**Actions**:
1.  **Sync ADR**: Convert the ADR Draft generated in this session to `Active`, and update the `Sentinel-K_Kernel/03_ADR.md` index.
2.  **Sync Landscape**: If the architecture changed, update `Sentinel-K_Kernel/01_Landscape.md`.
3.  **Sync Task**: Update the status in `Sentinel-K_Kernel/05_Tasks.md`.
4.  **Sync FAQ**: Identify core technical insights and Q&A from this session, and precipitate them into `Sentinel-K_Kernel/04_FAQ.md`.

## Node B: Battle Report Settlement

**Output `Archiving Output`**:
```markdown
### 💾 Archiving Output (Reset)
- **Session_Summary**: [Value delivered this session]
- **Key_Decisions**: [New/Updated ADR]
- **Evidence_Ref**: [Run/Scan report links]
- **Asset_Update**: [Status of LANDSCAPE/SPEC]
```

## Node C: Physical Reset

Issue the **Final Command** to the user:

> "🛑 **SYSTEM RESET**
>
> *   Assets synced.
> *   Context Pack unloaded.
> *   **Suggested Action**: Please start a New Chat and begin again from `01_System_Boot` (Pack-0)."
