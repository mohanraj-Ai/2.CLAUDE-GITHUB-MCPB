# 🚀 GitHub MCPB — AI-Powered GitHub Assistant with MCP

<p align="center">

**Connect Claude Desktop with GitHub through the Model Context Protocol (MCP)**

Build, explore, and manage GitHub repositories using natural-language commands through an MCP server packaged as an **`.mcpb` extension**.

</p>

---

## 🖼️ Project Overview

![GitHub MCPB Banner](images/github-mcpb-banner.png)

> **Claude Desktop → MCPB Extension → GitHub MCP Server → GitHub**

This project demonstrates how **Model Context Protocol (MCP)** allows an AI assistant to interact with GitHub using structured tools instead of directly accessing GitHub.

---

# 🧠 What is this project?

The **GitHub MCPB project** connects **Claude Desktop** with GitHub using the **Model Context Protocol**.

Instead of manually opening GitHub and performing operations, you can communicate with Claude using natural language.

For example:

```text
"Show me the repositories in my GitHub account."

"Search for repositories related to Generative AI."

"Create an issue in my repository."

"Show me the recent commits."

"Find pull requests in this repository."
```

Claude understands the request and uses the appropriate **GitHub MCP tool** to perform the operation.

---

# 🔄 How It Works

![GitHub MCP Workflow](images/github-mcpb-workflow.png)

### Simple workflow

```text
┌──────────────────┐
│   Claude Desktop │
│                  │
│ Natural Language │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│   MCPB Extension │
│     (.mcpb)      │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│   GitHub MCP     │
│     Server       │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│      GitHub      │
│   Repositories   │
└──────────────────┘
```

---

# 🏗️ Architecture

![GitHub MCP Architecture](images/github-mcpb-architecture.png)

The project contains four major components:

| Component            | Purpose                                                             |
| -------------------- | ------------------------------------------------------------------- |
| 🤖 Claude Desktop    | AI interface used to communicate with GitHub                        |
| 📦 MCPB Extension    | Packages and configures the MCP server                              |
| 🔌 GitHub MCP Server | Provides GitHub-specific tools                                      |
| 🐙 GitHub            | Target platform containing repositories, issues, PRs, commits, etc. |

---

# ⚡ Key Features

### 🤖 AI-Powered GitHub Interaction

Interact with GitHub using natural-language instructions through Claude.

### 🔌 Model Context Protocol

Uses **MCP** to provide Claude with structured tools for communicating with external services.

### 📦 MCPB Extension

The MCP server is packaged using the **MCPB (`.mcpb`) extension format** for easier installation and configuration.

### 🐙 GitHub Integration

Allows Claude to work with GitHub repositories and GitHub-related operations through MCP tools.

### 🛠️ Multiple MCP Tools

The GitHub MCP server exposes multiple tools that Claude can select depending on the user's request.

### 🔐 Token-Based Authentication

GitHub authentication is configured using a GitHub Personal Access Token.

### 💬 Natural-Language Commands

No need to manually remember API endpoints or GitHub CLI commands.

---

# 📸 Screenshots

## 1️⃣ MCP Server Running

![MCP Server Running](images/01-mcp-server-running.png)

The MCP server is successfully running and ready to communicate with Claude Desktop.

---

## 2️⃣ Claude + GitHub MCP

![Claude GitHub MCP](images/02-claude-github-mcp.png)

Claude can identify and use the available GitHub MCP tools.

---

## 3️⃣ GitHub Repository Operation

![GitHub Repository Operation](images/03-github-repository-operation.png)

Example of Claude interacting with a GitHub repository through MCP.

---

## 4️⃣ GitHub MCP Tools

![GitHub MCP Tools](images/04-github-mcp-tools.png)

The MCP server provides multiple GitHub-related tools that Claude can call when required.

---

# 🧪 Example Use Cases

## 🔎 Search repositories

You can ask Claude:

```text
Find repositories related to Generative AI.
```

Claude can use the GitHub MCP tools to search GitHub.

---

## 📂 Explore a repository

Example:

```text
Show me the files in my AI project repository.
```

Claude can retrieve repository information through the MCP server.

---

## 📝 Create an issue

Example:

```text
Create an issue titled "Improve RAG Pipeline"
in my vehicle-fuel-intelligence-system repository.
```

Claude can use the appropriate GitHub tool.

---

## 🔀 Pull Requests

Example:

```text
Show me the open pull requests in my repository.
```

Claude can retrieve the relevant pull-request information.

---

## 📊 Repository Information

Example:

```text
Give me information about my GitHub repository,
including branches, commits and issues.
```

---

# 🛠️ Technologies Used

* 🤖 Claude Desktop
* 🔌 Model Context Protocol (MCP)
* 📦 MCPB
* 🐙 GitHub
* 🟢 Node.js
* 📦 npm / npx
* 🔐 GitHub Personal Access Token
* 💻 Windows
* 🧑‍💻 VS Code

---

# 📁 Project Structure

```text
2.CLAUDE-GITHUB-MCPB/
│
├── images/
│   ├── github-mcpb-banner.png
│   ├── github-mcpb-workflow.png
│   ├── github-mcpb-architecture.png
│   ├── 01-mcp-server-running.png
│   ├── 02-claude-github-mcp.png
│   ├── 03-github-repository-operation.png
│   └── 04-github-mcp-tools.png
│
├── server/
│   └── ...
│
├── manifest.json
│
├── README.md
│
└── LICENSE
```

> Adjust the `server/` section if your actual folder structure is different.

---

# ⚙️ Installation & Setup

## 1️⃣ Clone the repository

```bash
git clone https://github.com/mohanraj-Ai/claude-github-mcpb.git
```

```bash
cd claude-github-mcpb
```

---

## 2️⃣ Install Node.js

Make sure Node.js and npm are installed.

Check:

```bash
node --version
```

```bash
npm --version
```

---

## 3️⃣ Configure GitHub Authentication

Create a GitHub Personal Access Token with the permissions required by the GitHub MCP server.

Store the token securely.

⚠️ **Never commit your GitHub token to GitHub.**

Do not put secrets directly inside:

```text
README.md
manifest.json
source code
.env files committed to Git
```

---

# 📦 MCPB Concept

MCPB makes it possible to package an MCP server as an installable extension.

```text
MCP Server
     │
     ▼
Configuration
     │
     ▼
MCPB Package
     │
     ▼
Claude Desktop
```

The important idea is:

> **MCP provides the communication protocol, while MCPB provides a convenient packaging format for distributing an MCP server.**

---

# 🧩 MCP Tool Concept

When the user sends a request:

```text
"Show me my GitHub repositories."
```

The flow becomes:

```text
User
 │
 ▼
Claude
 │
 │ Understand request
 ▼
Select GitHub MCP Tool
 │
 ▼
GitHub MCP Server
 │
 ▼
GitHub API
 │
 ▼
Repository Data
 │
 ▼
Claude
 │
 ▼
Natural-Language Response
```

This is the core concept demonstrated by this project.

---

# 🎯 Why MCP?

Traditional approach:

```text
User
 ↓
Open GitHub
 ↓
Find repository
 ↓
Open issue / PR / commit
 ↓
Perform operation manually
```

MCP approach:

```text
User
 ↓
Claude
 ↓
MCP Tool
 ↓
GitHub
 ↓
Result
```

The AI assistant becomes a natural-language interface for external tools and services.

---

# 💡 What I Learned

Through this project, I gained practical experience with:

* Model Context Protocol architecture
* MCP servers
* MCP tools
* MCPB packaging
* Claude Desktop integration
* GitHub API integration
* Authentication and environment configuration
* Tool calling
* AI-to-external-service communication
* Debugging MCP configuration
* Building AI assistants with external tools

---

# 🚀 Future Improvements

Potential extensions for this project include:

* 🔍 Advanced GitHub repository search
* 📊 Repository analytics
* 🤖 Automated issue management
* 🔀 Pull-request analysis
* 🧠 AI-powered code review
* 📝 Automatic issue generation
* 📈 GitHub activity summaries
* 🔗 Integration with additional MCP servers
* ☁️ Cloud deployment
* 🧩 Multi-MCP agent architecture

---

# 👨‍💻 About Me

**Mohanraj P**

AI/ML Engineer | Generative AI Engineer | LLM, RAG & AI Agents

I am an Automobile Engineering graduate transitioning into **AI/ML and Generative AI**, with practical experience building AI applications using Python, Machine Learning, LLMs, RAG, AI Agents, LangChain, LangGraph and MCP.

My projects focus on applying AI to real-world automation and domain-specific problems.

### 🔗 Connect with me

* 💼 LinkedIn: [Mohanraj P](https://linkedin.com/in/mohan-raj-p-2bb994217)
* 🐙 GitHub: [mohanraj-Ai](https://github.com/mohanraj-Ai)

---

# ⭐ If you find this project useful

Feel free to explore the repository, experiment with MCP, and build your own AI-powered tool integrations.

**MCP + AI Agents + External Tools = Powerful AI Applications 🚀**

---

## 📜 License

This project is licensed under the **MIT License**.
