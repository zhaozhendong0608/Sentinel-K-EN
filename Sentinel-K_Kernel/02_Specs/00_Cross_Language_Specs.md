# 00_Cross-Language Specs Comparison

> **Positioning**: Sentinel-K cross-language adaptation guide. When the Commander switches development languages, they should refer to the table below to reset the AI's **Vibe** environment.

## 📊 Core Specs Comparison Matrix

| Dimension             | **Java (Spring/RuoYi)**                  | **Python (FastAPI/AI)**                      | **Go (Gin/Cloud-Native)**                     | **Value Core (Invariant)**       |
| :-------------------- | :--------------------------------------- | :------------------------------------------- | :-------------------------------------------- | :------------------------------- |
| **Industry Standard** | **Alibaba Guidelines (Taishan Edition)** | **Google Style / PEP 8**                     | **Uber Go Style Guide**                       | **Top Industry Consensus**       |
| **Style Check**       | Checkstyle / P3C                         | **Ruff** / Flake8                            | **golangci-lint**                             | **Automated Guard**              |
| **Strong Type Check** | (Native Support)                         | **Mypy** / Pyright                           | (Native Support)                              | **Contract Determinism**         |
| **Test Framework**    | JUnit 5 / AssertJ                        | **pytest**                                   | `go test` / Testify                           | **Machine Witness (Evidence)**   |
| **Formatter**         | IntelliJ / Spotless                      | **Black** / Ruff Format                      | **gofmt** / goimports                         | **Layout Consistency**           |
| **Core Red Lines**    | No `SELECT *`<br/>No cross-layer calls   | Mandatory Type Hints<br/>No global variables | Explicit Error Handling<br/>No `init()` abuse | **Engineering Quality Baseline** |

---

## 🛠️ Sentinel-K Adaptation Suggestions

### 1. Python Adaptation (Vibe: Extremely Fast and Rigorous)
- **AI Tuning Key**: Mandate AI to use **Type Hints** and **Pydantic V2** as `Bone`.
- **Evidence Threshold**: `Ruff check` must have 0 warnings, `pytest` covers core branches.
- **Solid Assets**: `pyproject.toml`, `requirements.txt`, `alembic` (Migration).

### 2. Go Adaptation (Vibe: Simple and Efficient)
- **AI Tuning Key**: Mandatory **Interface** driven design. Require AI to show `golangci-lint` summary in Evidence.
- **Evidence Threshold**: Follow `Uber Style` error handling (`if err != nil` must be handled, strictly forbidden to ignore).
- **Solid Assets**: `go.mod`, `api/*.proto` (Contract files), `internal/` (Sealing private logic).

### 3. Java Adaptation (Vibe: Industrial Stability)
- **AI Tuning Key**: Follow **Alibaba Guidelines**. Mandatory physical isolation of `DTO/VO`.
- **Evidence Threshold**: Strictly execute `[K-PIZZA]` slicing.
- **Solid Assets**: `pom.xml`, `SQL Migration`, `SecurityConfig`.

---

## 🧭 Commander Invocation Commands (Slash Cmds)
When switching environments, issue the following command to the AI:
> "Please read `02_Specs/00_Cross_Language_Specs.md`. Currently entering **[Go/Python]** development mode, please reset your **Confidence Score Card** calculation weights according to the corresponding standards."

---
> *Revision History:*
> - *2026-02-19 - Established cross-language specification synchronization comparison table*
