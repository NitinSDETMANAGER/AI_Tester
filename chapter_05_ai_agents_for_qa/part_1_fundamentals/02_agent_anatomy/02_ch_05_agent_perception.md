# Agent Perception

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 Overview

Perception is how agents understand their environment and inputs.

---

## 👁️ What Agents Perceive

| Input Type | Examples | QA Use Case |
|------------|----------|-------------|
| **Text** | User prompts, documents | Requirements, specs |
| **Files** | Code, configs, logs | Test files, results |
| **API Data** | JSON responses | Jira tickets, CI/CD |
| **Web Pages** | DOM, screenshots | UI under test |
| **Images** | Screenshots, charts | Visual regression |

---

## 🔄 Perception Pipeline

```
Raw Input → Parse → Understand → Contextualize
─────────   ─────   ──────────   ────────────
"test login  Extract  "Task is    "Login relates
 feature"    intent   to test"    to auth module"
```

---

## 🎯 Context Understanding

Agents need to understand:

| What | Why | Example |
|------|-----|---------|
| **Intent** | What user wants | "Test" vs "Debug" |
| **Scope** | What's included | "Login only" or "All auth" |
| **Priority** | Urgency | "ASAP" vs "when ready" |
| **Constraints** | Limitations | "No destructive tests" |

---

## 📝 Key Takeaway

Good perception leads to correct actions. Misunderstanding = wrong results.

---

## 📚 See Also

- [Agent Components](ch_05_agent_components.md)
