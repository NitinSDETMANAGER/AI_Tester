# Jira Integration

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 Overview

Integrate your QA agents with Jira for bug management and test tracking.

---

## 📦 Setup

```bash
pip install jira
```

---

## 🛠️ Basic Operations

```python
from jira import JIRA

# Connect to Jira
jira = JIRA(
    server="https://your-domain.atlassian.net",
    basic_auth=("email@example.com", "api_token")
)

# Create a bug
def create_bug(title: str, description: str, priority: str = "Medium"):
    issue = jira.create_issue(
        project="QA",
        summary=title,
        description=description,
        issuetype={"name": "Bug"},
        priority={"name": priority}
    )
    return issue.key

# Search issues
def search_bugs(query: str):
    jql = f'project = QA AND type = Bug AND summary ~ "{query}"'
    issues = jira.search_issues(jql)
    return [{"key": i.key, "summary": i.fields.summary} for i in issues]

# Update issue
def update_status(issue_key: str, status: str):
    issue = jira.issue(issue_key)
    jira.transition_issue(issue, status)
```

---

## 🔧 Agent Tool Integration

```python
from langchain.tools import Tool

tools = [
    Tool(
        name="create_jira_bug",
        func=lambda x: create_bug(*x.split("|")),
        description="Create Jira bug. Input: 'title|description|priority'"
    ),
    Tool(
        name="search_jira",
        func=search_bugs,
        description="Search Jira bugs. Input: search query"
    )
]
```

---

## 📊 Automated Bug Filing

```python
def auto_file_bug_from_test_failure(test_result):
    """Automatically create Jira bug from test failure."""
    if test_result["status"] == "failed":
        title = f"Test Failure: {test_result['test_name']}"
        description = f"""
        **Test:** {test_result['test_name']}
        **File:** {test_result['file']}
        **Error:** {test_result['error']}
        **Screenshot:** {test_result['screenshot_url']}
        """
        return create_bug(title, description, "High")
```

---

## 📚 See Also

- [GitHub Integration](ch_05_github_integration.md)
- [Bug Triage Project](../projects/ch_05_bug_triage_project.md)
