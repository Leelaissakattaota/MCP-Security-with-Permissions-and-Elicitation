# 🛡️ MCP Security: Permissions & Elicitation

[![MCP](https://img.shields.io/badge/Protocol-MCP-blue?style=for-the-badge&logo=google-cloud)](https://modelcontextprotocol.io)
[![Python](https://img.shields.io/badge/Python-3.11+-yellow?style=for-the-badge&logo=python)](https://www.python.org/)
[![Gradio](https://img.shields.io/badge/UI-Gradio-orange?style=for-the-badge)](https://gradio.app/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](https://opensource.org/licenses/MIT)

### 🚀 Overview
This project demonstrates a secure implementation of the **Model Context Protocol (MCP)**. It focuses on building a robust trust layer between AI agents and local tools through **User-in-the-Loop** permissions and structured information elicitation.

---

## 🎨 Key Features

* **🔐 Granular Permissions**: Implements an `ALLOWED`, `DENIED`, and `ASKED` decision matrix for tool execution.
* **📝 Audit Logging**: Comprehensive capture of tool outcomes, user approvals, and full argument capture for forensic debugging.
* **💬 Smart Elicitation**: A conceptual framework using **JSON schemas** to collect missing input via a three-action model: *Accept, Decline, or Cancel*.
* **🤖 Multi-Agent Architecture**: Separate concerns between the protocol logic, a Gradio-based GUI, and an OpenAI-integrated Host App.

---

## 🏗️ Architecture Pattern

| Layer | Responsibility |
| :--- | :--- |
| **Base Client** | Protocol core + Permission Logic |
| **GUI Client** | Interactive Gradio Interface |
| **AI Host** | OpenAI Integration & Agent Coordination |

---

## 🛠️ Tech Stack & Concepts

* **Model Context Protocol (MCP)**: For standardized tool/server communication.
* **Security Compliance**: Structured input validation and timestamped logging.
* **Theia IDE**: Developed and tested in a cloud-based Python 3.11 environment.

---

## 🚀 Getting Started

1. **Clone the repository**:
   ```bash
   git clone [https://github.com/Leelaissakattaota/MCP-Security-with-Permissions-and-Elicitation.git](https://github.com/Leelaissakattaota/MCP-Security-with-Permissions-and-Elicitation.git)
