# AMA Questions and Answers

## 1. Adhikya Edammala — What is the use of `.env`?

A `.env` file stores **environment variables and sensitive information** separately from the code.

### Uses

- Stores API keys and passwords.
- Keeps secrets out of source code.
- Makes configuration easy to change.

> **Short answer:** `.env` stores configuration and sensitive environment variables.

---

## 2. Allanki VV Manikanta Sai — What is Compact?

**Compaction** means reducing a large amount of information into a **smaller summary** while keeping the important details.

### Uses

- Saves tokens.
- Reduces context size.
- Helps manage long conversations.

> **Short answer:** Compact means making large context smaller while keeping important information.

---

## 3. Boorle Sowmya Sri Lakshmi — What is Vite?

**Vite** is a fast **frontend development and build tool** used with React, Vue, Svelte, etc.

### Uses

- Fast development server.
- Supports Hot Module Replacement (HMR).
- Builds applications for production.

```bash
npm create vite@latest my-app
```

> **Short answer:** Vite is a fast tool for developing and building frontend applications.

---

## 4. Nayunipatruni Harsha Vardhan — What is an MCP Server?

**MCP Server** is a program that provides **tools and resources to AI applications** using the Model Context Protocol.

### Example

```text
AI → MCP Client → MCP Server → Tool/API/Database
```

> **Short answer:** An MCP server allows AI applications to use external tools and resources.

---

## 5. Rongala Vasu — What are the Different Permission Modes?

Permission modes control what actions an AI or application can perform.

| Mode | Meaning |
|---|---|
| **Allow** | Action is automatically allowed |
| **Ask** | User confirmation is required |
| **Deny** | Action is not allowed |
| **Read-only** | Can read but cannot modify |

> **Short answer:** Permission modes control which actions an AI is allowed to perform.

---

## 6. Vikas Mehta — How Can We Connect to an External Tool Without MCP?

We can directly connect to an external tool using:

- REST API
- SDK
- Python library
- CLI
- Database connection

### Example

```text
Python Application → REST API → External Service
```

> **Short answer:** Yes, we can connect directly using an API or SDK without an MCP server.
