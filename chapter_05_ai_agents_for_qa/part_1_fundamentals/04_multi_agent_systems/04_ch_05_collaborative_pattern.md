# Collaborative Pattern

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 What is the Collaborative Pattern?

Peer agents that work together, passing work back and forth, each improving the output.

---

## 🔄 How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                 COLLABORATIVE WORKFLOW                           │
└─────────────────────────────────────────────────────────────────┘

    ┌──────────┐         ┌──────────┐         ┌──────────┐
    │  WRITER  │ ──────► │ REVIEWER │ ──────► │  EDITOR  │
    │  AGENT   │         │  AGENT   │         │  AGENT   │
    └──────────┘         └──────────┘         └──────────┘
         ▲                                         │
         └─────────────────────────────────────────┘
                    (Iteration if needed)
```

---

## 📝 QA Example: Test Case Review

```
Test Writer Agent → Generates test cases
        ↓
Test Reviewer Agent → Reviews for gaps, suggests improvements  
        ↓
Test Writer Agent → Incorporates feedback
        ↓
Final Output → Polished test cases
```

---

## ✅ When to Use

- Quality-critical outputs
- Peer review workflows
- Iterative improvement needed
- Multiple perspectives valuable

---

## 🎯 Example: Bug Report Enhancement

```python
# Agent 1: Bug Writer
initial_bug = """
Summary: Login broken
Steps: Click login, enter credentials, click submit
Result: Error
"""

# Agent 2: Bug Reviewer
review = """
Missing:
- Expected result
- Environment info
- Error message text
- Screenshots
"""

# Agent 1: Enhanced Bug
final_bug = """
Summary: Login fails with "Invalid credentials" for valid users
Environment: Chrome 120, macOS, Production
Steps:
1. Navigate to /login
2. Enter valid email: test@example.com
3. Enter valid password: ********
4. Click Submit
Expected: Redirect to dashboard
Actual: Error message "Invalid credentials"
Severity: P0 - Blocks all users
"""
```

---

## 📚 See Also

- [Supervisor Pattern](ch_05_supervisor_pattern.md)
- [Swarm Pattern](ch_05_swarm_pattern.md)
