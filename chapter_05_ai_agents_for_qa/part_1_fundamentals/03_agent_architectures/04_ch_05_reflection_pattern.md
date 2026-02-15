# Reflection Pattern

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 What is Reflection?

The agent generates output, then critiques and improves it before finalizing.

---

## 🔄 The Pattern

```
┌───────────────────────────────────────────────────────┐
│               REFLECTION PATTERN                       │
└───────────────────────────────────────────────────────┘

    ┌──────────┐     ┌──────────┐     ┌──────────┐
    │ GENERATE │ ──► │ CRITIQUE │ ──► │ IMPROVE  │
    │          │     │          │     │          │
    │ First    │     │ Find     │     │ Fix      │
    │ attempt  │     │ issues   │     │ issues   │
    └──────────┘     └──────────┘     └──────────┘
         │                                  │
         └──────────────────────────────────┘
                     (repeat if needed)
```

---

## 📝 Example

```
Task: "Prioritize these 10 bugs"

GENERATE:
Priority List:
1. BUG-101 (Critical)
2. BUG-105 (High)
...

CRITIQUE:
Issues found:
- BUG-103 should be higher (blocks deployment)
- BUG-107 is duplicate of BUG-102

IMPROVE:
Revised Priority List:
1. BUG-103 (Critical - blocks deployment)
2. BUG-101 (Critical)
3. BUG-105 (High)
...removed BUG-107 (duplicate)
```

---

## ✅ When to Use

| ✅ Good For | ❌ Not Great For |
|-------------|------------------|
| Quality-critical tasks | Speed-critical tasks |
| Complex decisions | Simple tasks |
| Error-prone outputs | Well-defined outputs |
| Bug triage, risk assessment | Routine operations |

---

## 🎯 QA Applications

- Bug prioritization
- Test review
- Risk assessment
- Critical path analysis

---

## 📚 See Also

- [ReAct Pattern](ch_05_react_pattern.md)
- [Agent Reasoning](../agent_anatomy/ch_05_agent_reasoning.md)
