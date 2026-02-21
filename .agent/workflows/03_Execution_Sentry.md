---
description: 🛡️ [Execution] Atomic Execution & Sentry - **Core Flow**
---

# 🛡️ 03_Execution_Sentry (Execution Sentry V2.0)

> **Positioning**: Core production phase.
> **Purpose**: Eliminate "verbal green lights" through **Evidence Block** and **Reverse Testing** for mandatory physical verification.
> **V2 Upgrade**: Integrates `Reverse Testing` and standardized evidence block delivery.

## Node A: Scope Lock & Pack Loading (Scope & Pack)

**Instructions**:
1.  Lock the `Scope` of the current Task (strictly prohibit out-of-bounds modifications).
2.  **Atomic Load `Pack-2` (Execution) `[K-BOOT]`**:
    - **Only Load**: Target Files identified by `/02_Planning_Radar`.
    - **Search**: Directly related Interfaces/DTOs, entirely loading the whole module directory is strictly prohibited.
    - **Reference**: Related `03_ADR` entries.

## Node B: Atomic Execution

**Execution Principles (Sentry Iron Rules)**:
1.  **Patch-First**: Output Diff preview first, then Apply.
2.  **Test-First**: For core logic, write Test (Red) first, then Impl (Green).
3.  **Reverse_Proof**: Core algorithm/security logic must execute "destructive proof" `[K-TEST]`.
4.  **Solid Protection**:
    - Touching `Solid-Strict` -> Must have `Approval_Hash`, and provide `ADR_Entry` + `Asset_Update` in Evidence.
    - Touching `Solid-Regulated` -> Must provide `ADR_Entry` + `Asset_Update` in Evidence.

## Node C: Generate Evidence

**Deliverables must contain a standard Evidence Block (copyable)**:

```markdown
### 📦 Context Evidence `[K-EVIDENCE]`
- **Compliance_Status**: 🟢 [Pass] | ⚠️ [Warning] | 🔴 [Partial]
- **Context_Log**: [Pack-0 + Pack-X]
- **Diff_Summary**: [List of files + Summary of key logic changes]
- **Test_Run**: `[TEST_RUNNER]` -> [Pass/Fail]
- **Scan_Result**: `[SCAN_RUNNER]` -> [Blocker Count]
- **Reverse_Proof**: (If applicable)
  - Position: [Symbol]
  - Action: [Intentional destructive action]
  - Error: [Expected red light error]
  - Recover: [Green light after recovery]
- **Asset_Update**: [Solid-Strict/Regulated change traces | Liquid-only: NO_CHANGE]
- **ADR_Entry**: [ADR-ID -> Decision Point Review | Liquid-only: N/A]
```

## Node D: Decision Point

Report to the commander:
> "Commander, Task execution completed.
> *   Evidence: [Complete/Missing]
> *   Reverse_Proof: [Passed/Skipped]
> *   Solid Touch: [None/Yes]
>
> Please enter **ACK** to confirm and merge evidence, or **Reject** to send back for rewrite."
