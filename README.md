# 🛡️ AgentSentinel AI Security Gate (GitHub Action)

[![GitHub Release](https://img.shields.io/github/v/release/sparkysolutions10-pixel/agentsentinel-action?color=blue&logo=github)](https://github.com/sparkysolutions10-pixel/agentsentinel-action/releases)
[![Marketplace](https://img.shields.io/badge/Marketplace-AgentSentinel%20Security%20Gate-blue?logo=github&logoColor=white)](https://github.com/marketplace/actions/agentsentinel-ai-security-gate)
[![License](https://img.shields.io/badge/License-Apache%202.0-green.svg)](LICENSE)
[![Zero-Trust](https://img.shields.io/badge/Security-Zero--Trust%20AST-emerald)](https://getagentsentinel.com)

> **Deterministic Zero-Trust AST Security Gate & Prompt-Injection Interceptor for Autonomous AI Agents, Tool Calls, and MCP Servers.**

---

## ⚡ What is AgentSentinel?

Modern LLMs (Claude Code, Cursor, AutoGen, CrewAI, LangChain) are probabilistic engines. When an agent is granted tool-calling access (`execute_command`, `sql_query`, `transfer_funds`), adversaries can use **indirect prompt injection** to trick the agent into wiping databases, leaking API keys, or executing unbacked transactions.

Traditional linters (Snyk, SonarQube) only scan static code syntax — **they cannot inspect runtime agent tool calls or prompt exfiltration vectors.**

**AgentSentinel** intercepts code and tool definitions before they hit production:
- ❌ **Blocks Destructive Shell Execution** (`rm -rf`, `DROP TABLE`, remote binary curls)
- ❌ **Intercepts Adversarial Prompt Injections** (System prompt exfiltration probes)
- ❌ **Quarantines Leaked Credentials** (AWS keys, GitHub PATs, Private Keys)
- ❌ **Enforces Web3 Invariants** (Infinite token allowances, unbacked bridge mints)
- ✅ **Drops an Official Security Audit Badge** directly onto your Pull Request.

### 🌐 Trusted by Autonomous Multi-Agent Protocols
- **[AgentRail Protocol](https://github.com/SorobanAgents/agentrail)** (Autonomous AI Agent Allowance & Settlement on Stellar / Soroban) — Audits every Pull Request with AgentSentinel.

---

## 🚀 Quick Start (Add in 30 Seconds)

Add this workflow to your repository at `.github/workflows/agentsentinel.yml`:

```yaml
name: AgentSentinel Security Gate

on:
  push:
    branches: [main, master, develop]
  pull_request:
    branches: [main, master, develop]

jobs:
  agent-security-audit:
    name: Zero-Trust AI Agent Audit
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Codebase
        uses: actions/checkout@v4

      - name: Run AgentSentinel Security Gate
        uses: sparkysolutions10-pixel/agentsentinel-action@v1
        with:
          api-key: ${{ secrets.AGENTSENTINEL_KEY }}
          strict: 'true'
```

---

## ⚙️ Action Inputs

| Input | Description | Required | Default |
| :--- | :--- | :--- | :--- |
| `api-key` | AgentSentinel Pro/Enterprise license key (Optional for Community Trial) | No | `""` (5 Free Scans) |
| `path` | Repository path or sub-directory to audit | No | `.` |
| `strict` | Fail CI build with exit code `1` if critical threats are intercepted | No | `true` |

---

## 📊 Action Outputs

| Output | Description |
| :--- | :--- |
| `threats-detected` | Total number of intercepted security vulnerabilities |
| `files-scanned` | Total number of scanned codebase files |
| `verdict` | Overall gate security verdict (`PASS` or `BLOCK`) |

---

## 🏢 Enterprise & Pro Upgrades

Free community accounts include **5 free trial PR scans**. 

For continuous production protection, SOC-2 compliance reports, and custom AST policy rules:
👉 **[Upgrade to AgentSentinel Pro ($299/mo)](https://getagentsentinel.com)**

---

## 📄 License & Attribution

Licensed under the [Apache License 2.0](LICENSE).  
Maintained with ❤️ by **Sparky Solutions (Mukesh Biswas)**.
