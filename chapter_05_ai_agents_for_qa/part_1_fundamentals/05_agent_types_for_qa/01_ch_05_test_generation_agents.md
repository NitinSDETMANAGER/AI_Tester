# Test Generation Agents

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 Overview

Test Generation Agents automatically create test cases, test code, and test data from requirements, specifications, or code.

---

## 📋 Types of Test Generation

| Type | Input | Output | Use Case |
|------|-------|--------|----------|
| **Requirements → Tests** | PRD/User Stories | Test cases | Coverage from specs |
| **API Spec → Tests** | OpenAPI/Swagger | API tests | Contract testing |
| **Code → Tests** | Source code | Unit tests | Test creation |
| **UI → Tests** | Screens/wireframes | E2E tests | UI coverage |
| **Manual → Automated** | Manual test cases | Playwright/Cypress | Migration |

---

## 🔧 Example: Requirements to Test Cases

### Input: User Story
```
As a user, I want to log in with email and password
so that I can access my dashboard.

Acceptance Criteria:
- Valid email format required
- Password minimum 8 characters
- Show error for invalid credentials
- Redirect to dashboard on success
```

### Agent Output: Test Cases
```markdown
## TC-001: Valid Login
- **Precondition:** User exists with valid credentials
- **Steps:** Enter valid email, enter valid password, click login
- **Expected:** User redirected to dashboard

## TC-002: Invalid Email Format
- **Steps:** Enter "invalid-email", enter any password, click login
- **Expected:** Error: "Please enter a valid email"

## TC-003: Password Too Short
- **Steps:** Enter valid email, enter "abc", click login
- **Expected:** Error: "Password must be at least 8 characters"

## TC-004: Wrong Password
- **Steps:** Enter valid email, enter wrong password, click login
- **Expected:** Error: "Invalid credentials"

## TC-005: Empty Fields
- **Steps:** Leave email empty, click login
- **Expected:** Error: "Email is required"
```

---

## 🛠️ Tools for Test Generation

| Tool | Best For |
|------|----------|
| Claude/GPT-4 | General test case generation |
| LangChain + Tools | Automated pipeline |
| n8n Workflows | No-code generation |
| MCP + Playwright | E2E test generation |

---

## 📚 See Also

- [Test Execution Agents](ch_05_test_execution_agents.md)
- [Test Maintenance Agents](ch_05_test_maintenance_agents.md)
