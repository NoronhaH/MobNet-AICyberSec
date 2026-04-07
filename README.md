# MobNet-AICyberSec — System Prompts

This repository contains the deterministic system prompts used in an AI-driven cybersecurity framework for threat detection, analysis, and automated response in private mobile networks (5G/NPN).

## 🧠 Overview

These prompts are designed to control the behavior of multiple AI agents operating in a real-world SOC (Security Operations Center) pipeline.

Unlike generic prompts, these are:

- Deterministic and rule-constrained
- Designed for production environments
- Integrated with real security tools and workflows
- Built to minimize hallucinations and enforce structured outputs

The agents operate in a coordinated pipeline:

**Detection → Analysis → Decision → Response**

## 🤖 Agents

### 1. TechDiag (Technical Diagnosis)

- Analyzes raw security logs (Wazuh / Suricata)
- Produces strictly formatted JSON output
- Identifies attack patterns (DoS, scanning, etc.)
- Applies strict parsing and correlation rules

📄 `tech_diag.md`

---

### 2. SOC Guardian (Executive Communication)

- Translates technical analysis into executive-level alerts
- Formats messages for human decision-makers
- Emphasizes risk, impact, and urgency
- Requests explicit approval for mitigation

📄 `soc_guardian.md`

---

### 3. Decision Validator

- Interprets human responses
- Classifies decisions strictly as:
  - `APROVADO`
  - `REJEITADO`
- Handles ambiguity with secure defaults

📄 `decision_validator.md`

---

### 4. Response Agent (Executor)

- Evaluates historical context (RAG / memory)
- Checks current system state (blocked IPs)
- Executes actions via external tools (MCP)
- Ensures safe and consistent mitigation decisions

📄 `executor.md`

---

## ⚙️ Design Principles

These prompts follow strict engineering principles:

- **Determinism over creativity**
- **Explicit rules over implicit reasoning**
- **Structured outputs (machine-readable)**
- **Human-in-the-loop validation**
- **Auditability and traceability**
- **Safe interaction with real infrastructure**

## 🔐 Key Features

- JSON-only enforcement for critical agents
- Strict formatting constraints
- Built-in anti-hallucination rules
- Context-aware decision making (RAG)
- Operational safety constraints (whitelisting, validation)

## 🧩 Use Case

Designed for:

- SOC automation
- Incident response pipelines
- AI-assisted cybersecurity operations
- Critical infrastructure environments
- Private 5G/mobile networks

## ⚠️ Disclaimer

These prompts are designed for controlled environments.  
Improper use without validation layers or infrastructure safeguards is not recommended.
