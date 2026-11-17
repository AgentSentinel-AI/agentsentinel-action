<div align="center">
  <img src="assets/agentsentinel_luxury_logo_1024.png" width="160" height="160" alt="AgentSentinel Logo" style="border-radius: 22%; box-shadow: 0 0 25px rgba(0, 245, 255, 0.4);" />
  <h1>🛡️ AgentSentinel AI Security Gate</h1>
  <p><strong>Zero-Trust AST Runtime Firewall & Prompt-Injection Interceptor for Autonomous AI Agents, Tool Calls, and MCP Servers</strong></p>

  <p>
    <a href="https://github.com/sparkysolutions10-pixel/agentsentinel-action/releases"><img src="https://img.shields.io/github/v/release/sparkysolutions10-pixel/agentsentinel-action?color=blue&logo=github" alt="GitHub Release"></a>
    <a href="https://github.com/marketplace/actions/agentsentinel-ai-security-gate"><img src="https://img.shields.io/badge/Marketplace-AgentSentinel%20Security%20Gate-blue?logo=github&logoColor=white" alt="Marketplace"></a>
    <a href="LICENSE"><img src="https://img.shields.io/badge/License-Apache%202.0-green.svg" alt="License"></a>
    <a href="https://getagentsentinel.com"><img src="https://img.shields.io/badge/Official%20Site-getagentsentinel.com-00f5ff?logo=safari&logoColor=white" alt="Official Site"></a>
  </p>
</div>

---

## ⚡ What is AgentSentinel?

Modern LLMs and AI Agents (Claude Code, Cursor, AutoGen, CrewAI, LangChain, MCP tools) are probabilistic engines. When an agent is granted tool-calling access (`execute_command`, `sql_query`, `transfer_funds`), adversaries can use **indirect prompt injection** or malicious code commits to trick the agent into wiping databases, leaking private keys, or bypassing financial spending limits.

Traditional linters (Snyk, SonarQube) only scan static syntax — **they cannot inspect runtime agent tool calls, wallet allowance invariants, or prompt exfiltration vectors.**

**AgentSentinel** intercepts code and tool definitions before they hit production:
- ❌ **Blocks Destructive Shell Execution** (`rm -rf`, `DROP TABLE`, remote binary curls)
- ❌ **Intercepts Adversarial Prompt Injections** (System prompt exfiltration probes)
- ❌ **Quarantines Leaked Credentials** (AWS keys, GitHub PATs, Stellar & EVM Private Keys)
- ❌ **Enforces Web3 Invariants** (Infinite token allowances, unbacked bridge mints)
- ✅ **Drops an Official Zero-Trust Security Audit Badge** directly onto your Pull Request comments.

### 🌐 Trusted by Autonomous Multi-Agent Protocols
- **[AgentRail Protocol](https://github.com/SorobanAgents/agentrail)** (Autonomous AI Agent Allowance & Micro-Settlement on Stellar / Soroban) — Audits every Pull Request with AgentSentinel.

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
    permissions:
      contents: read
      pull-requests: write
      issues: write

    steps:
      - name: Checkout Codebase
        uses: actions/checkout@v4

      - name: Run AgentSentinel Security Gate
        uses: sparkysolutions10-pixel/agentsentinel-action@v1
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          strict: 'true'
```

---

## ⚙️ Action Inputs

| Input | Description | Required | Default |
| :--- | :--- | :---: | :---: |
| `github-token` | GitHub token for posting audit reports directly on PR comments | **Yes** | `${{ secrets.GITHUB_TOKEN }}` |
| `strict` | Fail CI build with exit code `1` if critical vulnerabilities are detected | No | `'true'` |
| `path` | Directory path or repository root to audit | No | `'.'` |
| `api-key` | AgentSentinel Pro/Enterprise license key (optional for 5-scan free trial) | No | `''` |

---

## 📊 Action Outputs

| Output | Description |
| :--- | :--- |
| `threats-detected` | Total count of intercepted agent security threats |
| `verdict` | Final Gate verdict: `PASS` or `BLOCK` |
| `files-scanned` | Total number of scanned codebase files |

---

## 🛡️ Example Pull Request Audit Report

When AgentSentinel scans a pull request, it posts an official Zero-Trust audit report:

```markdown
## 🛡️ AgentSentinel AI Security Gate v1.0.0
### Zero-Trust AST Firewall & Prompt-Injection Interceptor

| Metric | Result |
| :--- | :--- |
| **Files Audited** | 68 |
| **Threats Detected** | 0 |
| **Strict TypeScript / Zod** | ✅ Verified |
| **Dependency Telemetry Scan** | ✅ Clean (0 external network leaks) |
| **Security Verdict** | 🟢 **PASSED (Zero-Trust Verified)** |

> All automated safety invariants and AST security rules have passed successfully. PR is clean and safe to merge.
```

---

## 🏢 Enterprise & Commercial Licensing
For custom on-premise enclaves, hardware HSM attestation, and unlimited team licenses, visit:
👉 **[getagentsentinel.com](https://getagentsentinel.com)**

Developed with ❤️ by **Sparky Solutions** (Mukesh Biswas).
