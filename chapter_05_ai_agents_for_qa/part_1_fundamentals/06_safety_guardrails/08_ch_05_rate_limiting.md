# Rate Limiting

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 Overview

Prevent runaway agents from consuming excessive resources.

---

## 📊 Rate Limits to Implement

| Resource | Limit | Period |
|----------|-------|--------|
| API calls | 100 | per minute |
| File writes | 50 | per session |
| LLM requests | 1000 | per hour |
| Token usage | 100K | per task |
| Actions | 500 | per session |

---

## 🛠️ Implementation

```python
from ratelimit import limits, sleep_and_retry

@sleep_and_retry
@limits(calls=100, period=60)
def call_api(endpoint, data):
    return requests.post(endpoint, json=data)
```

---

## 🚨 Circuit Breaker

If limits exceeded repeatedly:
1. Stop the agent
2. Alert the operator
3. Wait for manual restart

---

## 📚 See Also

- [Cost Control](ch_05_cost_control.md)
- [Error Handling](ch_05_error_handling.md)
