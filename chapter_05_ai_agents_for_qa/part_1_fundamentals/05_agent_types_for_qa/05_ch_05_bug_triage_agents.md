# Bug Triage Agents

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 Overview

Bug Triage Agents automatically classify, prioritize, and route bugs to the right teams.

---

## 📊 Triage Workflow

```
New Bug Report
     │
     ▼
┌─────────────────────────────────────────┐
│         BUG TRIAGE AGENT                 │
│                                          │
│  1. Parse bug description               │
│  2. Classify by type (UI, API, etc.)    │
│  3. Determine severity                  │
│  4. Check for duplicates                │
│  5. Assign to team                      │
│  6. Set priority                        │
│  7. Add labels                          │
└─────────────────────────────────────────┘
     │
     ▼
Jira Ticket Updated & Assigned
```

---

## 🏷️ Classification

| Category | Keywords | Team |
|----------|----------|------|
| UI/UX | layout, button, display | Frontend |
| API | endpoint, response, 500 | Backend |
| Auth | login, password, session | Security |
| Performance | slow, timeout, lag | Platform |
| Data | incorrect, missing, sync | Data |

---

## 📝 Example Triage

```
Input Bug:
  "Users can't complete checkout. Getting 500 error after clicking Pay."

Agent Output:
  Type: API
  Severity: P0 (Critical)
  Component: Payment
  Team: Backend
  Duplicate: No
  Labels: [payment, api, production, critical]
  Priority: Immediate
```

---

## 🔄 Duplicate Detection

```
New bug: "Login page shows blank screen on Safari"

Similar bugs found:
  - BUG-123: Safari login page white screen (98% match) - OPEN
  - BUG-089: Browser compatibility issue (72% match) - CLOSED

Agent: Marking as duplicate of BUG-123
```

---

## 📚 See Also

- [Bug Detection Agents](ch_05_bug_detection_agents.md)
- [Jira Integration](../../part_4_advanced/integrations/ch_05_jira_integration.md)
