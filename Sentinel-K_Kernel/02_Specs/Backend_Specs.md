# Backend Coding Standards v2.0

> **Core Principles**: Alibaba guidelines as base layer, RuoYi architecture as middle layer, AI cooperation as top layer.
> **Positioning**: Highest red line for all AI coding and code reviews.

---

## 🛑 Core Red Lines (Mandatory)

### 1. Layered Architecture
- ✅ Strictly follow `Controller → Service → Mapper` 3-tier architecture.
- ❌ **No Cross-layering**: Controllers are prohibited from calling Mappers directly; Services must contain business logic.
- ❌ **No Circular Dependencies**: Discovered circular dependencies must be decoupled by introducing intermediary Services or refactoring.

### 2. Concurrency and Memory Safety (Alibaba Essence)
- ❌ **No Manual Thread Creation**: Must acquire threads through the defined `ThreadPoolTaskExecutor` to prevent resource exhaustion.
- ✅ **ThreadLocal Safety**: `ThreadLocal` variables must be explicitly `remove()`d in the `finally` block to prevent memory leaks.
- ✅ **Collection Initialization**: When initializing a collection, the initial capacity must be specified `new HashMap<>(16)` to reduce resizing overhead.

### 3. Numerical Precision and Types (Stability)
- ❌ **Prohibit using float/double for currencies**: When calculating high precision, measurement thresholds, or amounts, **`BigDecimal`** must be used.
- ✅ **BigDecimal Comparison**: Must use `compareTo()`, strictly forbid using `equals()`.
- ✅ **Enum Usage**: Status fields must define Enum or constant classes, prohibiting hardcoding "Magic Numbers" in code.

### 4. Extreme SQL Performance (DB Red Lines)
- ❌ **No SELECT ***: Fields must be explicitly specified on-demand to reduce IO and network overhead.
- ❌ **Looping Queries**: Database queries within a `for` loop are strictly forbidden. Must use `IN` queries or batch Joins.
- ✅ **Pagination Limits**: All pagination query interfaces must set a default maximum Limit (500 recommended) to protect the DB.
- ✅ **Upsert Strategy**: When importing or syncing data, prioritize using `saveOrUpdate` (based on unique code).

### 5. Exceptions and Logs
- ✅ **Business Exceptions**: Must throw `ServiceException`. Logs must contain context parameters (full Chinese description).
- ✅ **Stack Protection**: `log.error` must include e ( `log.error("context", e)` ).
- ✅ **Jackson Uniqueness**: Use Jackson globally; introducing Fastjson that causes serialization conflicts is strictly prohibited.

### 6. Comments and AI Cooperation
- ✅ **ADR Registration**: Major refactorings, Solid Asset touches, or adding operator components must be registered in `Sentinel-K_Kernel/03_ADR.md` (following `[K-ADR]`).
- ✅ **Reverse Proof**: Core logic changes must provide `Reverse_Proof` evidence (following `[K-TEST]`).
- ✅ **Slicing Awareness**: When task scale triggers `[K-PIZZA]` threshold (3 files/100 lines), it must proactively apply for slicing.

---

## 🏗️ Code Examples (Quick Reference)

### A. BigDecimal Calculation
```java
// ✅ Correct: Construct using String and use compareTo
BigDecimal val = new BigDecimal("0.1");
if (other.compareTo(val) > 0) { ... }
```

### B. Thread Pool Usage (RuoYi)
```java
// ✅ Correct: Inject existing thread pool
@Autowired
@Qualifier("threadPoolTaskExecutor")
private ThreadPoolTaskExecutor executor;
```

---

## 📂 Package Structure Rules (Sentinel-K Exclusive)
- `com.zhendong.sentinel.core`: Core engine, algorithm orchestration logic.
- `com.zhendong.sentinel.mapper`: Database persistence layer.
- `com.zhendong.sentinel.service.strategy`: Strategy implementation classes for different storage engines.
