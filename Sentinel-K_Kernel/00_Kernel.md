# 🟢 Sentinel-K System Kernel

> [!IMPORTANT]
> **SSOT (Single Source of Truth) Note**: This file is the single authoritative source for the Sentinel-K project. All other documentation and AI workflow terminology, thresholds, and rules must reference the anchors defined in this document.

## 1. Glossary `[K-TERM]`
- **Commander**: Human. Responsible for defining boundaries (Intent), security audit (Audit), and accepting results (Accept).
- **Agent**: AI. Responsible for reasoning (Reasoning), atomic execution (Execution), and providing evidence (Evidence).
- **Solid Asset**: Extremely high-risk core files; modifications must follow `[K-ADR]`. See `[K-ASSET]` grading for details.
- **Evidence Block**: A physical validation summary that must accompany code delivery. Format in `[K-EVIDENCE]`.
- **Approval_Hash**: A temporary human authorization identifier for `Solid-Strict` asset changes.
- **ADR_Entry**: A reference and callback note to a specific ADR (Liquid-only is allowed to use `N/A`).

> [!NOTE]
> **Naming Consistency**: To avoid drift, this document uses `Approval_Hash` / `ADR_Entry` / `Compliance_Status` as standard keys; Legacy writings (e.g., "Approval Hash" / "ADR Entry" / "Compliance Status") are treated as synonymous aliases.

## 2. Language Protocol `[K-LANG]`
- **Principle**: Besides code symbols, log keywords, and error stacks, all dialogue, documents (Artifacts), and thought processes must use **Chinese (Simplified)** (Note: Except for this English translation).

## 3. Boot Protocol `[K-BOOT]`
- **Pack-0 (Kernel)**: The foundation. Includes `00_Kernel` + `05_Tasks` + `.cursorrules` (or project-level instructions).
- **Pack-1 (Bone-Arch)**: Architectural blueprint. Loads on top of Pack-0: `01_Landscape` + `02_Specs` + `06_Topology`.
- **Pack-2 (Muscle-Impl)**: Execution package. Loads on top of Pack-1: Business Code + `03_ADR` + `04_FAQ`.

## 4. Core Laws

### 4.1 Pizza Logic `[K-PIZZA]`
- **Threshold**: Estimated changes **> 3 files** or **> 100 lines of code**.
- **Mandatory Constraint**: Once triggered, it must be physically split into `Sub-Intent`.
    - **Stage A (Bone)**: Only defines interfaces, DTOs, contract constants.
    - **Stage B (Stub - Optional)**: Implement Mock returns and run through end-to-end links.
    - **Stage C (Muscle)**: Implement concrete business logic and standard evidence delivery.
- **Collaboration Modes**:
    - **Default Two Slices**: Stage A + Stage C (Skip Stub).
    - **Optional Three Slices**: Stage A + Stage B + Stage C (Recommended for complex/high-risk tasks).

### 4.2 Asset Grading `[K-ASSET]`
- **Solid-Strict**: External contracts, SQL, CI, .env, core dependencies.
    - **Action**: Must register a new entry in `03_ADR.md`, and provide a task-level `Approval_Hash`.
    - **Evidence**: Evidence block must contain `ADR_Entry` and `Asset_Update`.
- **Solid-Regulated**: Core domain models, key business strategies.
    - **Action**: Must register a new entry in `03_ADR.md`.
    - **Evidence**: Evidence block must contain `ADR_Entry` and `Asset_Update`.
- **Liquid**: Business implementations, Controllers, new feature tests.
    - **Action**: Free evolution, no ADR required.
    - **Evidence**: Satisfy the standard evidence chain.

### 4.3 Reverse Testing `[K-TEST]`
- **Scenario**: Core algorithms, security interceptions, complex state transitions.
- **Process**: First write a test to prove its failure (Red) -> Implement business logic (Green) -> Intentionally break business logic to confirm failure again (Destructive) -> Recover (Recover).

### 4.4 Evidence Standard `[K-EVIDENCE]`
Deliverables must contain an evidence block with the following standard keys.

**Ready Template**:
```markdown
### 📢 Verification Evidence (IDE)
- **Compliance_Status**: 🟢 [Pass] | ⚠️ [Warning] | 🔴 [Partial]
- **Context_Log**: [Pack-0/1/2] + [Extra Files]
- **Diff_Summary**: [Modified File Count] | [Logic Summary]
- **Test_Run**: [Runner] -> [Pass/Total] | [Result Link/Img]
- **Scan_Result**: [Runner] -> [Block/Critical Errors Count]
- **Asset_Update**: [Solid-Strict/Regulated change traces | Liquid-only: NO_CHANGE]
- **ADR_Entry**: [ADR-ID] -> [Decision Point Review | Liquid-only: N/A]
- **Reverse_Proof**: [Position] -> [Expected Error] -> [Recovered | N/A if not applicable]
```

**Recommended/Audit-Ready Enhancements**:
- `Evidence_Source`: Original evidence source (e.g. screenshot path, log summary).
- `Artifact_Ref`: Associated artifact reference.
- `Raw_Excerpt`: Raw snippet extract of code/logs.

### 4.5 Confidence Score `[K-SCORE]`
Every major iteration must output a **Confidence Score Card** (integer 0-100):
- **[90 - 100] (Pass)**: Clear path, complete evidence, approved for execution.
- **[80 - 89] (Warning)**: Ambiguities or potential risks exist, requires human intervention or ACK.
- **[0 - 79] (Block)**: Critical omission or serious ambiguity, forced Circuit Break.

**Score Card Template**:
```markdown
### 🧠 Confidence Score Card
- **Score**: [0-100]
- **Status**: [🟢/⚠️/🔴]
- **Reasoning**: [Brief scoring logic]
- **Gaps**: [Remaining risks/Knowledge blind spots]
- **Action**: [Proceed | Need_ACK | Circuit_Break]
```

## 5. Architecture Decision Records (ADR Rules) `[K-ADR]`
- **Trigger**: Modifying `Solid Asset` or introducing a new tech stack, major design change.
- **Storage**: `Sentinel-K_Kernel/03_ADR.md`.

---
> *Revision History:*
> - *2026-02-16 - Established SSOT*
> - *2026-02-16 - Introduced Stub (Stage B) three-slice Pizza model*
> - *2026-02-16 - Completed asset grading, enhanced evidence chain, and scoring circuit break protocol (Standardization Patch)*
