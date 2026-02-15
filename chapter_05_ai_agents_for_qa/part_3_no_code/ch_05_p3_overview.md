# Part 3: No-Code Agent Platforms Overview

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

**Purpose:** Build AI agents without code using visual platforms  
**Chapter:** 5 - AI Agents for QA  
**Part:** 3 - No-Code Agent Platforms

---

## 🎯 What You'll Learn

By the end of Part 3, you will be able to:

1. ✅ Install and configure n8n for AI workflows
2. ✅ Build test automation agents in n8n
3. ✅ Use LangFlow for visual agent development
4. ✅ Create RAG-powered QA assistants
5. ✅ Compare no-code platforms for different use cases

---

## 📋 Part 3 Contents

| Section | Topics |
|---------|--------|
| [n8n Setup](n8n/ch_05_n8n_setup.md) | Installation, configuration |
| [n8n AI Nodes](n8n/ch_05_n8n_ai_nodes.md) | AI Agent, LLM Chain, Memory |
| [n8n Projects](n8n/ch_05_n8n_test_plan_generator.md) | Test Plan Generator |
| [LangFlow Setup](langflow/ch_05_langflow_setup.md) | Installation, configuration |
| [LangFlow Components](langflow/ch_05_langflow_components.md) | Agents, Chains, RAG |
| [LangFlow Projects](langflow/ch_05_langflow_jira_rag.md) | Jira → Test Case RAG |
| [Platform Comparison](ch_05_platform_comparison.md) | n8n vs LangFlow vs code |
| [Best Practices](ch_05_nocode_best_practices.md) | When to use what |

---

## 🆚 No-Code vs Code

```
┌─────────────────────────────────────────────────────────────────┐
│                   WHEN TO USE WHAT                               │
└─────────────────────────────────────────────────────────────────┘

NO-CODE (n8n, LangFlow)           CODE (LangChain, CrewAI)
──────────────────────           ─────────────────────────
✅ Rapid prototyping              ✅ Complex logic
✅ Business user friendly         ✅ Custom integrations
✅ Visual debugging               ✅ Production scale
✅ Quick iterations               ✅ Version control
✅ No developer needed            ✅ Fine-grained control

Use no-code when:                Use code when:
• Speed > control                • Complexity > speed
• POC/Demo needed               • Production deployment
• Non-technical users           • Custom requirements
• Standard workflows            • High performance needs
```

---

## 🛠️ Platform Overview

### n8n
- **Type:** Workflow automation platform
- **Best For:** Multi-step automations, integrations
- **AI Features:** LLM chains, AI agents, memory
- **Self-host:** Yes (Docker)
- **Cloud:** n8n.cloud

### LangFlow
- **Type:** Visual LangChain builder
- **Best For:** LLM pipelines, RAG systems
- **AI Features:** Full LangChain in visual UI
- **Self-host:** Yes (pip install)
- **Cloud:** Astra Langflow

---

## 📁 Part 3 File Structure

```
part_3_no_code/
├── ch_05_p3_overview.md              # This file
├── n8n/
│   ├── ch_05_n8n_setup.md
│   ├── ch_05_n8n_ai_nodes.md
│   └── ch_05_n8n_test_plan_generator.md
├── langflow/
│   ├── ch_05_langflow_setup.md
│   ├── ch_05_langflow_components.md
│   └── ch_05_langflow_jira_rag.md
├── ch_05_platform_comparison.md
└── ch_05_nocode_best_practices.md
```

---

## 🚀 Prerequisites

Before starting Part 3, ensure you have:

- ✅ Completed Part 1 (Agent Fundamentals)
- ✅ Docker installed (for n8n)
- ✅ Python 3.10+ (for LangFlow)
- ✅ API keys for Claude or OpenAI

---

## 📚 Navigation

| Previous | Up | Next |
|----------|------|------|
| [Part 2: MCP](../part_2_mcp/ch_05_p2_overview.md) | [Chapter 5](../ch_05_ai_agents_for_qa.md) | [Part 4: Advanced](../part_4_advanced/ch_05_p4_overview.md) |
