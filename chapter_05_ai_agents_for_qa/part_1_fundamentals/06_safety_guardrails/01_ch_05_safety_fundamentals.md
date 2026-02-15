# Safety Fundamentals

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 Why Safety Matters

AI Agents can take real actions. Without proper guardrails, they can:
- Delete important files
- Send wrong messages
- Create security vulnerabilities
- Incur massive API costs
- Access sensitive data

---

## 🛡️ Core Safety Principles

### 1. Principle of Least Privilege
Grant only the minimum permissions needed.

```
❌ Bad:  Agent has admin access to everything
✅ Good: Agent can only access test databases
```

### 2. Human-in-the-Loop
Require approval for destructive actions.

```
Agent: "I want to delete 500 old test files"
System: [REQUIRES APPROVAL] ⏳
Human: [Approve] or [Deny]
```

### 3. Sandboxing
Run agents in isolated environments.

```
Production DB  ←── BLOCKED ──  Agent
Test DB        ←── ALLOWED ──  Agent
```

### 4. Rate Limiting
Prevent runaway agents.

```
Max 100 API calls per minute
Max 10 file writes per session
```

### 5. Audit Logging
Track everything the agent does.

```
[2024-01-15 10:30:45] Agent read file: requirements.md
[2024-01-15 10:30:46] Agent created file: test_login.py
[2024-01-15 10:30:47] Agent called Jira API: create ticket
```

---

## 📊 Risk Matrix

| Action | Risk Level | Mitigation |
|--------|------------|------------|
| Read files | Low | Scope to project |
| Write files | Medium | Require review |
| Delete files | High | Human approval |
| Execute code | High | Sandboxed environment |
| Send messages | Medium | Draft review |
| API calls | Medium | Rate limit |
| DB queries | High | Read-only by default |

---

## 📝 Key Takeaways

1. **Assume agents will make mistakes** — Build defenses
2. **Start restrictive** — Open up gradually
3. **Log everything** — For debugging and audit
4. **Test safety measures** — Before production

---

## 📚 See Also

- [Agent Anti-Hallucination](ch_05_agent_anti_hallucination.md)
- [Error Handling](ch_05_error_handling.md)
- [Cost Control](ch_05_cost_control.md)
