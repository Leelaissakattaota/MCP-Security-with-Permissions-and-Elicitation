# 🛡️ MCP Security: Permissions & Elicitation

![Language](https://img.shields.io/badge/Language-Python%203.11-3776AB?style=flat-square&logo=python&logoColor=white)
![Framework](https://img.shields.io/badge/Framework-FastMCP-0052CC?style=flat-square)
![Protocol](https://img.shields.io/badge/Protocol-Model%20Context%20Protocol-6A0DAD?style=flat-square)
![UI](https://img.shields.io/badge/UI-Gradio-FF7C00?style=flat-square)
![LLM](https://img.shields.io/badge/LLM-OpenAI%20GPT--4o--mini-412991?style=flat-square&logo=openai&logoColor=white)
![Focus](https://img.shields.io/badge/Focus-Agentic%20AI%20Security-2E7D32?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)

---

## 📌 Project Overview

This project demonstrates a **secure, production-ready implementation 
of the Model Context Protocol (MCP)** — the emerging standard for 
connecting AI agents to real-world tools and systems.

It builds a robust **trust layer between AI agents and local tools** 
through granular permission management, user-in-the-loop elicitation, 
and full audit logging — making AI agent actions transparent, 
controllable, and safe.

**Domain:** Agentic AI Security & MCP  
**Language:** Python 3.11  
**Architecture:** Client-Server (STDIO transport)  

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────┐
│              AI Host App                     │
│   (OpenAI GPT-4o-mini + MCP Integration)    │
└──────────────────┬──────────────────────────┘
                   │
┌──────────────────▼──────────────────────────┐
│           Base Permission Client             │
│  (Permission Check → Allow / Ask / Deny)    │
│  (Audit Logging + Elicitation Framework)    │
└──────────────────┬──────────────────────────┘
                   │
┌──────────────────▼──────────────────────────┐
│         FastMCP Server                       │
│  Tools: read_file │ write_file               │
│         delete_file │ execute_command        │
│  Resources: audit/log │ config/permissions   │
│  Prompts: security_review                    │
└─────────────────────────────────────────────┘
```

---

## 📂 Project Structure

```
mcp-security-permissions-elicitation/
│
├── mcp_permission_server.py        # FastMCP server with 4 tools
├── mcp_permission_client_base.py   # Base client with permission logic
├── mcp_permission_client_app.py    # Gradio GUI client application
├── mcp_permission_host_app.py      # OpenAI-integrated AI host app
│
├── data/
│   ├── permissions.json            # Permission config (allow/ask/deny)
│   ├── audit.log                   # Timestamped audit trail
│   └── test.txt                    # Sample test file
```

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| MCP Framework | FastMCP |
| MCP Protocol | Model Context Protocol (MCP) |
| Language | Python 3.11 |
| UI | Gradio |
| LLM Integration | OpenAI GPT-4o-mini |
| Security Layer | Role-based Permission System |
| Logging | Timestamped Audit Logging |
| Transport | STDIO (Client-Server) |
| IDE | Theia Cloud IDE |

---

## 🔐 Permission System

Each MCP tool is assigned a risk level and default permission:

| Tool | Risk Level | Default Permission |
|---|---|---|
| `read_file` | 🟢 LOW | `allow` — auto-execute |
| `write_file` | 🟡 MEDIUM | `ask` — requires approval |
| `delete_file` | 🔴 HIGH | `deny` — always blocked |
| `execute_command` | ⚫ CRITICAL | `deny` — always blocked |

### Permission Decision Flow
```
Tool Call Request
      │
      ▼
Check permissions.json
      │
   ┌──┴──┐
allow   ask   deny
  │      │      │
  ▼      ▼      ▼
Execute  Show  Block &
Tool    Approval  Log
        Dialog
```

---

## 🚀 Key Features

**🔐 Granular Permission Management**
- Three-level decision matrix: `ALLOW` / `ASK` / `DENY`
- Argument-specific permission overrides
- Runtime permission updates via Gradio UI

**📝 Full Audit Logging**
- Every tool call logged with timestamp and decision
- Tracks approvals, denials, and elicitation requests
- Accessible via MCP resource endpoint `file://audit/log`

**💬 Elicitation Framework**
- JSON schema-based structured user input collection
- Three-action model: Accept / Decline / Cancel
- User-in-the-loop approval for sensitive operations

**🤖 Multi-Layer Architecture**
- Separate concerns: Protocol core, GUI client, AI Host
- OpenAI GPT-4o-mini integrated as the reasoning agent
- MCP tools exposed as OpenAI function-calling tools

**🛡️ Security Prompts**
- Built-in `security_review` prompt template
- Analyses operations for risk, impact, and audit needs
- Generates structured security recommendations

---

## ⚙️ How to Run

**Step 1 — Install dependencies:**
```bash
pip install fastmcp mcp gradio openai
```

**Step 2 — Set OpenAI API key:**
```bash
export OPENAI_API_KEY="your-api-key-here"
```

**Step 3 — Start the MCP Server:**
```bash
python mcp_permission_server.py
```

**Step 4 — Launch GUI Client:**
```bash
python mcp_permission_client_app.py
```

**Step 5 — Launch AI Host App:**
```bash
python mcp_permission_host_app.py
```

---

## 📊 Permissions Configuration

The `data/permissions.json` file controls all tool permissions:

```json
{
  "read_file": "allow",
  "write_file": "ask",
  "delete_file": "deny",
  "execute_command": "deny"
}
```

You can update permissions dynamically through the Gradio UI 
without restarting the server.

---

## 🎓 Skills Demonstrated

- Model Context Protocol (MCP) implementation with FastMCP
- Agentic AI security — permission management & trust layers
- User-in-the-loop AI design patterns
- OpenAI function calling & tool integration
- Role-based access control (RBAC) for AI tools
- Audit logging & forensic debugging
- Gradio UI development for AI applications
- Async Python programming (asyncio, AsyncExitStack)
- Client-server architecture with STDIO transport
- JSON schema-based elicitation frameworks

---

## 📜 Certifications

| Certification | Issuer | Platform |
|---|---|---|
| IBM Data Science Professional Certificate | IBM | Coursera |
| IBM Generative AI Professional Certificate | IBM | Coursera |
| IBM Agentic AI with RAG Certificate | IBM | Coursera |
| IBM RAG and Agentic AI Professional Certificate | IBM | Coursera |

---

## 🤝 Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Leela%20A-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/leela-a)
[![Gmail](https://img.shields.io/badge/Gmail-attotaleelaissak@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:attotaleelaissak@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-Leelaissakattaota-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Leelaissakattaota)
