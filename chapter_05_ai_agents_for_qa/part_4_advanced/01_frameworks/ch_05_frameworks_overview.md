# Agent Frameworks Overview

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 Overview

Choose the right framework for your QA agent needs.

---

## 📊 Framework Comparison

| Framework | Type | Strengths | QA Use Case |
|-----------|------|-----------|-------------|
| **LangChain** | General-purpose | Flexibility, ecosystem | Custom agents |
| **CrewAI** | Multi-agent | Easy team setup | QA team simulation |
| **AutoGen** | Multi-agent | Conversational | Pair programming |
| **LlamaIndex** | RAG-focused | Document handling | QA knowledge base |
| **Instructor** | Structured | Type-safe outputs | Test case extraction |

---

## 🔧 Quick Start Examples

### LangChain

```python
from langchain.agents import create_react_agent
from langchain_anthropic import ChatAnthropic
from langchain.tools import Tool

llm = ChatAnthropic(model="claude-3-5-sonnet-20241022")

tools = [
    Tool(name="run_tests", func=run_tests, description="Run pytest"),
    Tool(name="create_bug", func=create_jira_bug, description="Create Jira bug"),
]

agent = create_react_agent(llm, tools, prompt)
```

### CrewAI

```python
from crewai import Agent, Task, Crew

test_writer = Agent(
    role="Test Writer",
    goal="Write comprehensive test cases",
    llm="claude-3-5-sonnet-20241022"
)

test_reviewer = Agent(
    role="Test Reviewer",
    goal="Review and improve test cases",
    llm="claude-3-5-sonnet-20241022"
)

crew = Crew(agents=[test_writer, test_reviewer], tasks=[...])
crew.kickoff()
```

### AutoGen

```python
from autogen import AssistantAgent, UserProxyAgent

qa_agent = AssistantAgent(
    name="QA_Agent",
    system_message="You are a QA automation expert.",
    llm_config={"model": "gpt-4"}
)

user = UserProxyAgent(name="User")
user.initiate_chat(qa_agent, message="Write tests for login")
```

---

## 🎯 Framework Selection Guide

```
START
  │
  ▼
Need multi-agent collaboration?
  │
  ├── YES → CrewAI (easy) or AutoGen (conversational)
  │
  └── NO ↓
          │
          ▼
     Building RAG system?
          │
          ├── YES → LlamaIndex
          │
          └── NO ↓
                  │
                  ▼
             Need structured outputs?
                  │
                  ├── YES → Instructor
                  │
                  └── NO → LangChain (general purpose)
```

---

## 📚 See Also

- [LangChain Agents](ch_05_langchain_agents.md)
- [CrewAI Teams](ch_05_crewai_teams.md)
