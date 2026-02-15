# MCP VS Code Setup

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 Overview

Use MCP with VS Code via extensions like Continue or Cline.

---

## 🔌 Option 1: Continue Extension

### Install Continue
1. Open VS Code Extensions
2. Search "Continue"
3. Install the Continue extension

### Configure MCP
Edit `~/.continue/config.json`:

```json
{
  "models": [...],
  "mcpServers": [
    {
      "name": "playwright",
      "command": "npx",
      "args": ["-y", "@anthropic/mcp-playwright"]
    }
  ]
}
```

---

## 🔌 Option 2: Cline Extension

### Install Cline
1. Search "Cline" in Extensions
2. Install Cline

### Configure MCP
Cline has built-in MCP support:
1. Open Cline sidebar
2. Go to Settings
3. Add MCP servers

---

## ✅ Verify Setup

1. Open the AI assistant panel
2. Ask: "What tools do you have?"
3. Check for MCP tools in response

---

## 📚 See Also

- [MCP Claude Desktop](ch_05_mcp_claude_desktop.md)
- [MCP Cursor Setup](ch_05_mcp_cursor.md)
