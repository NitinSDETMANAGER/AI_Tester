# Hierarchical Pattern

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 What is the Hierarchical Pattern?

Multiple levels of agents, with managers delegating to leads, who delegate to workers. Like an organizational chart.

---

## 🏗️ Structure

```
                    ┌─────────────┐
                    │   MANAGER   │
                    │   (Top)     │
                    └──────┬──────┘
              ┌────────────┼────────────┐
              ▼            ▼            ▼
        ┌──────────┐ ┌──────────┐ ┌──────────┐
        │ LEAD: UI │ │LEAD: API │ │LEAD: E2E │
        └────┬─────┘ └────┬─────┘ └────┬─────┘
          ┌──┴──┐      ┌──┴──┐      ┌──┴──┐
          ▼     ▼      ▼     ▼      ▼     ▼
        ┌───┐ ┌───┐  ┌───┐ ┌───┐  ┌───┐ ┌───┐
        │W1 │ │W2 │  │W3 │ │W4 │  │W5 │ │W6 │
        └───┘ └───┘  └───┘ └───┘  └───┘ └───┘
```

---

## 🎯 QA Example: Full Test Organization

| Level | Agent | Responsibility |
|-------|-------|---------------|
| Manager | QA Director | Strategy, prioritization |
| Lead | UI Test Lead | UI testing coordination |
| Lead | API Test Lead | API testing coordination |
| Worker | Form Tester | Tests form validation |
| Worker | Auth Tester | Tests authentication |

---

## ✅ When to Use

- Very large test suites
- Multiple test types (UI, API, E2E)
- Need for specialized sub-teams
- Complex organizational structure

---

## 📚 See Also

- [Supervisor Pattern](ch_05_supervisor_pattern.md)
- [Collaborative Pattern](ch_05_collaborative_pattern.md)
