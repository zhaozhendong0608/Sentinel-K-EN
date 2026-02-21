# Frontend Coding Standards

> **Purpose**: Core constraint checklist for AI coding. Quick reference manual for human developers.

---

## Core Red Lines (Mandatory)

### 1. Component Specifications
- ✅ Must use `<script setup>` syntax
- ✅ Single File Components should not exceed 300 lines (split if exceeded)

### 2. Unified Popups
- ✅ Use `ElMessage.success/error/warning` for all prompts
- ✅ Dangerous operations (delete/clear) must use `ElMessageBox.confirm` for secondary confirmation
- ❌ Prohibit the use of native `alert()` or `confirm()`

### 3. Template Specifications
- ❌ Prohibit writing super long style strings in `class` (split to CSS if more than 5 class names)
- ❌ Prohibit the use of inline styles `:style` (except for special dynamic styles)
- ✅ Use semantic CSS class names

### 4. Exception Handling
- ✅ All asynchronous operations must be try-catched and give user-friendly prompts
- ✅ Error prompts must be in Chinese

### 5. CSS Specifications
- ✅ Must use `scoped` to avoid style pollution
- ✅ Use SCSS nesting syntax
- ✅ **Evidence Complete Loop**: All deliveries must be accompanied by a standard `Evidence Block` (`Diff_Summary`, `Test_Run`, `Scan_Result`).

---

## Project Structure

```
src/
├── views/          # Page components
├── components/     # Common components
│   ├── common/     # Basic components
│   └── business/   # Business components
├── api/            # API interface definitions
├── store/          # Pinia state management
├── router/         # Routing configurations
├── utils/          # Utility functions
└── types/          # TypeScript type definitions
```

---

## Naming Conventions

- Page components: PascalCase + semantic `AlgorithmEditor.vue`
- Common components: PascalCase + prefix `BaseButton.vue`
- API files: lowercase + underscore `product.ts`

---

## API Call Specifications

- ✅ API methods must have comments added for explanation
- ✅ Uniformly use `request` utility class to encapsulate axios

---

## State Management

- ✅ Use Pinia for state management
- ✅ Stores partitioned by modules (user, algorithm, datasource)
- ✅ Asynchronous operations are uniformly placed in `actions`

---

## Git Commit Specifications

Format: `<type>(<scope>): <subject>`

Type Types:
- `feat`: New feature
- `fix`: Bug fix
- `refactor`: Refactoring
- `docs`: Documentation updates
- `style`: Code formatting adjustments
