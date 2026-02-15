# ReAct Pattern

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 What is ReAct?

ReAct = **Re**asoning + **Act**ing

The agent alternates between thinking (reasoning) and doing (acting), using observations to guide next steps.

---

## 🔄 The ReAct Loop

```
┌────────────────────────────────────────────────────────┐
│                    ReAct LOOP                          │
└────────────────────────────────────────────────────────┘

    ┌──────────┐
    │  THOUGHT │  ← "I need to check the API spec"
    └────┬─────┘
         │
         ▼
    ┌──────────┐
    │  ACTION  │  ← read_file("api_spec.yaml")
    └────┬─────┘
         │
         ▼
    ┌──────────┐
    │OBSERVATION│ ← "Found 5 endpoints..."
    └────┬─────┘
         │
         ▼
    ┌──────────┐
    │  THOUGHT │  ← "Now I should write tests for each"
    └────┬─────┘
         │
         ▼
       (repeat)
```

---

## 📝 ReAct Example

```
Task: "Write tests for the user registration API"

Thought: I need to understand the registration endpoint first.
Action: read_file("docs/api/registration.md")
Observation: Endpoint: POST /api/users, requires name, email, password

Thought: I should create test cases for valid and invalid inputs.
Action: write_file("tests/test_registration.py", test_code)
Observation: File created successfully

Thought: I should run the tests to verify they work.
Action: run_command("pytest tests/test_registration.py")
Observation: 5 tests passed, 0 failed

Thought: Task complete. Tests are working.
Final Answer: Created 5 tests for registration API, all passing.
```

---

## ✅ When to Use ReAct

| ✅ Good For | ❌ Not Great For |
|-------------|------------------|
| Interactive tasks | Simple one-shot tasks |
| Tool-heavy workflows | Pure reasoning |
| Exploratory work | Fixed procedures |
| Uncertain outcomes | Highly predictable tasks |

---

## 🎯 QA Applications

- Test generation with file/API access
- Bug investigation
- Exploratory testing
- Test maintenance

---

## 📚 See Also

- [Plan-Execute Pattern](ch_05_plan_execute_pattern.md)
- [Reflection Pattern](ch_05_reflection_pattern.md)
