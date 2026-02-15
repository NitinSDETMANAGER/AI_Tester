# Agent Components

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

**Purpose:** Deep dive into the core components of AI Agents  
**Chapter:** 5 - AI Agents for QA  
**Part:** 1 - Fundamentals

---

## 🎯 Overview

Every AI agent consists of these core components working together:

```
┌─────────────────────────────────────────────────────────────────┐
│                    AGENT ARCHITECTURE                            │
└─────────────────────────────────────────────────────────────────┘

                         ┌─────────────┐
                         │    USER     │
                         │    GOAL     │
                         └──────┬──────┘
                                │
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│                         AGENT CORE                               │
│  ┌─────────────────────────────────────────────────────────────┐│
│  │                    LLM (BRAIN)                              ││
│  │              Claude / GPT-4 / Llama                         ││
│  └─────────────────────────────────────────────────────────────┘│
│         │              │              │              │          │
│         ▼              ▼              ▼              ▼          │
│   ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐   │
│   │PERCEPTION│   │ MEMORY   │   │ PLANNING │   │  TOOLS   │   │
│   │          │   │          │   │          │   │          │   │
│   │• Input   │   │• Short   │   │• Goals   │   │• APIs    │   │
│   │• Context │   │• Long    │   │• Tasks   │   │• DBs     │   │
│   │• State   │   │• Vector  │   │• Steps   │   │• Browser │   │
│   └──────────┘   └──────────┘   └──────────┘   └──────────┘   │
└─────────────────────────────────────────────────────────────────┘
                                │
                                ▼
                         ┌─────────────┐
                         │   OUTPUT    │
                         │   ACTION    │
                         └─────────────┘
```

---

## 🧩 The 6 Core Components

### 1. 🧠 LLM (Brain)

The reasoning engine that powers the agent.

| Aspect | Description |
|--------|-------------|
| **Purpose** | Understanding, reasoning, decision-making |
| **Examples** | GPT-4, Claude, Llama, Gemini |
| **QA Role** | Analyze requirements, generate tests |

### 2. 👁️ Perception

How the agent understands its environment.

| Input Type | Example |
|------------|---------|
| User text | "Write tests for login" |
| File content | requirements.md |
| API response | JSON from Jira |
| Screen state | DOM elements |

### 3. 🧠 Memory

What the agent remembers.

| Memory Type | Duration | Example |
|-------------|----------|---------|
| **Working** | Current task | Current test being written |
| **Short-term** | Session | Conversation history |
| **Long-term** | Persistent | Past test results, known bugs |
| **Episodic** | Events | What happened last deployment |
| **Semantic** | Facts | Testing best practices |

### 4. 📋 Planning

How the agent breaks down goals.

```
Goal: "Test the checkout flow"
            │
            ▼
    ┌───────────────┐
    │   PLANNER     │
    └───────┬───────┘
            │
            ▼
Step 1: Read requirements
Step 2: Identify scenarios
Step 3: Write test cases
Step 4: Generate code
Step 5: Execute tests
Step 6: Report results
```

### 5. 🔧 Tools

Actions the agent can take.

| Tool Category | Examples |
|---------------|----------|
| **File I/O** | read_file, write_file |
| **Code** | execute_python, run_tests |
| **API** | jira_create, slack_send |
| **Browser** | navigate, click, type |
| **Database** | query_sql, insert_record |

### 6. 🎬 Actions

The execution of decisions.

```
Decision: "I need to read the requirements"
    │
    ▼
Action: read_file("requirements.md")
    │
    ▼
Result: "Login should support email/password..."
    │
    ▼
Next Decision: Based on result
```

---

## 🔄 How Components Work Together

```
User: "Generate tests for the payment API"

1. PERCEPTION
   └── Parse goal: generate tests, target: payment API

2. MEMORY
   └── Recall: Previous payment tests, API specs

3. PLANNING
   └── Plan: Read spec → Identify endpoints → Write tests

4. TOOL: read_file("payment_api.yaml")
   └── Got: API specification

5. LLM REASONING
   └── Analyze spec, design test cases

6. TOOL: write_file("test_payment.py")
   └── Created test file

7. ACTION: execute("pytest test_payment.py")
   └── Tests executed

8. OUTPUT
   └── "Created 15 tests, all passing ✓"
```

---

## 📊 Component Comparison

| Component | Without It | With It |
|-----------|------------|---------|
| **LLM** | No reasoning | Intelligent decisions |
| **Perception** | Blind | Context-aware |
| **Memory** | Forgetful | Learns from past |
| **Planning** | Chaotic | Organized execution |
| **Tools** | Talk only | Can take action |
| **Actions** | Plans only | Actually executes |

---

## 🎯 QA-Specific Examples

| Component | QA Application |
|-----------|----------------|
| **Perception** | Read Jira tickets, parse test results |
| **Memory** | Remember flaky tests, known issues |
| **Planning** | Test strategy, execution order |
| **Tools** | Playwright, Jira API, Slack |
| **Actions** | Run tests, file bugs, notify team |

---

## 📝 Key Takeaways

1. **All components are essential** — Missing one limits the agent
2. **LLM is the brain** — But it needs hands (tools)
3. **Memory enables learning** — Agents get better over time
4. **Planning enables complex tasks** — Multi-step workflows
5. **Tools enable action** — The difference from pure LLMs

---

## 📚 See Also

- [Agent Tools](ch_05_agent_tools.md)
- [Agent Memory](ch_05_agent_memory.md)
- [Agent Reasoning](ch_05_agent_reasoning.md)
- [Agent Planning](ch_05_agent_planning.md)
