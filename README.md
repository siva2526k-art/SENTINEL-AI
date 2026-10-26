# 🛡️ SENTINEL — Autonomous Zero-Trust AI Cyber Threat & Fraud Triage Platform

> **An Indigenous, Privacy-Preserving AI SOC Analyst Protecting Public Digital Infrastructure, Educational Institutions, and Citizen Data.**

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)
[![Python: 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/API-FastAPI-009688.svg)](https://fastapi.tiangolo.com/)
[![ChromaDB](https://img.shields.io/badge/Vector_DB-ChromaDB-orange.svg)](https://www.trychroma.com/)
[![Local AI: Ollama](https://img.shields.io/badge/Local_AI-Ollama-black.svg)](https://ollama.ai/)
[![Prototype Status: 10/10 PASS](https://img.shields.io/badge/Prototype_Verification-10%2F10_PASS-success.svg)](scripts/test_all_prototype_levels.py)

---

## 🇮🇳 Hackathon & Track Alignment
* **Event:** Hack for Social Cause — Viksit Bharat Young Leaders Dialogue (VBYLD) 2027
* **Organized by:** Ministry of Youth Affairs & Sports (MoYAS), Govt. of India & IIT Bombay
* **Primary Track:** **Theme 8: Digital Safety & Cyber Fraud Awareness**
* **Secondary Track:** **Theme 7: AI & Emerging Technologies for Social Good**
* **Target UN SDGs:** 
  - **SDG 9:** Industry, Innovation, and Resilient Cyber Infrastructure
  - **SDG 16:** Peace, Justice, and Strong Public Institutions (Protecting public services from digital extortion)
* **Lead Architect & Developer:** **Sivabalan T** (Department of Computer Science & Engineering, Sri Sai Ram Engineering College, Chennai, Tamil Nadu)

---

## 📌 The Problem: Alert Fatigue & Citizen Data Leakage
As India moves toward **Viksit Bharat 2047**, public institutions (universities, district hospitals, municipal bodies, and cooperative banks) face an escalating wave of cyber fraud and ransomware attacks:
1. **Severe Alert Fatigue:** Security Operations Centers (SOCs) receive 5,000+ alerts daily. Manual human investigation takes 30–45 minutes per alert, causing ~70% of alerts to go unreviewed.
2. **Citizen Data Privacy Violations:** Passing raw telemetry logs to commercial public cloud AI models (ChatGPT, Gemini) leaks sensitive citizen PII, employee credentials, and internal network maps, directly violating India's **Digital Personal Data Protection (DPDP) Act 2023**.
3. **High Licensing Costs:** Enterprise commercial SOAR software (Splunk, Palo Alto) costs lakhs of rupees annually, leaving public welfare institutions without modern defenses.

---

## 💡 The Solution: SENTINEL Architecture
SENTINEL is an indigenous, open-source-aligned autonomous AI security platform that automates alert triage in **under 30 seconds** while preserving 100% data sovereignty:

```
[Raw Telemetry Ingestion: Wazuh / Syslog / Suricata JSON Webhooks]
                                 │
                                 ▼
┌────────────────────────────────────────────────────────────────────────┐
│ 1. In-RAM Zero-Trust Privacy Shield (Volatile Memory Only)             │
│    • 100% scrubbing of IP addresses, MACs, emails, tokens              │
│    • Replaces real values with synthetic tokens: [USER_1], [IP_1]      │
│    • Neutralizes adversarial prompt injection overrides                │
└────────────────────────────────────────────────────────────────────────┘
                                 │
                                 ▼ (Sanitized Telemetry Only)
┌────────────────────────────────────────────────────────────────────────┐
│ 2. Semantic Context & Vector RAG Memory                                │
│    • MITRE ATT&CK taxonomy mapping across Tactics & Techniques          │
│    • ChromaDB vector memory with cosine similarity threat correlation  │
└────────────────────────────────────────────────────────────────────────┘
                                 │
                                 ▼
┌────────────────────────────────────────────────────────────────────────┐
│ 3. 3-Tier Sovereign AI Router (Cost & Offline Resilience)             │
│    • Tier 1: Local Ollama (deepseek-r1:8b) → 90% of alerts at ₹0 cost  │
│    • Tier 2: Groq Cloud (deepseek-r1:70b) → Fast complex reasoning     │
│    • Tier 3: Gemini 2.0 Flash → High-context multi-stage threat triage │
└────────────────────────────────────────────────────────────────────────┘
                                 │
                                 ▼
┌────────────────────────────────────────────────────────────────────────┐
│ 4. AST Forensic Sandbox & Active Defense Engine                        │
│    • Opcode-whitelisted Python AST execution (eliminates host escapes) │
│    • Dual-View RBAC Dashboard (Masked vs Authorized Re-identification) │
│    • Automated firewall rules, process isolation & C-suite PDF brief   │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 🌟 Key Technical Highlights

1. **🔒 Zero-Trust In-RAM Data Tokenizer (`src/sanitizer.py`)**:
   - Cryptographically tokenizes sensitive PII in volatile memory. 
   - Zero bytes of raw citizen PII or internal infrastructure topologies leave the local host.
   - Authorized analysts can re-identify data locally via secure RBAC session endpoints.

2. **🤖 3-Tier Dynamic AI Router (`src/router.py`)**:
   - Resolves ~90% of routine alerts 100% offline via local quantized GGUF models at **₹0 cloud expense**.
   - Enables complete operational readiness in **air-gapped defense, police, and government networks**.

3. **🛡️ AST-Enforced Forensic Sandbox (`src/sandbox.py`)**:
   - Uses Python's Abstract Syntax Tree (`ast`) to strictly whitelist permitted forensic opcodes, blocking destructive system calls (`exec`, `eval`, `os.system`).

4. **⚡ High-Concurrency Ingestion & REST API (`src/api/` & `src/ingestion/`)**:
   - FastAPI server with asynchronous webhook listeners processing Wazuh JSON alerts, Syslog events, and Suricata network logs in real time.

5. **📄 Automated Courtroom & Executive PDF Reporting (`src/reports/`)**:
   - Instant compilation of clean, audit-compliant C-suite incident briefs and timeline breakdowns.

---

## 📁 Repository Structure

```
SENTINEL-AI/
├── src/
│   ├── sanitizer.py           # Zero-Trust In-RAM PII & Prompt Injection Sanitizer
│   ├── router.py              # 3-Tier Sovereign AI Router
│   ├── memory.py              # ChromaDB Vector Threat RAG Store
│   ├── sandbox.py             # AST Opcode-Whitelisted Execution Sandbox
│   ├── triage_agent.py        # 9-Stage Autonomous Triage Pipeline
│   ├── mitre_mapper.py        # MITRE ATT&CK Matrix Classifier
│   ├── audit_logger.py        # Cryptographic Audit Event Logger
│   ├── ai_client.py           # Multi-Provider AI Inference Client
│   ├── demo_runner.py         # End-to-End Incident Demo Runner
│   ├── api/                   # FastAPI Server with Dual-View RBAC Endpoints
│   ├── correlation/           # Attack Graph & Temporal Correlation Engine
│   ├── ingestion/             # Wazuh Syslog JSON Webhook Listener
│   ├── response/              # Active Defense Controllers (Firewall, Process, Host)
│   ├── reports/               # Automated Executive PDF Brief Compiler
│   └── samples/               # Realistic Attack Log Samples (SSH, PowerShell, Exfil)
├── scripts/
│   └── test_all_prototype_levels.py  # 10-Level Comprehensive Verification Suite
├── docs/
│   ├── TamilNadu_TeamSENTINEL_PresentationDeck.pdf # Official 7-Slide Pitch Deck
│   └── SENTINEL_Executive_Incident_Report.pdf      # Sample Automated Incident Brief
├── requirements.txt           # Project Dependencies
├── .env.example               # Environment Configuration Template
├── .gitignore
└── LICENSE                    # Apache 2.0 License
```

---

## 🚀 Quickstart & Setup Guide

### 1. Clone the Repository
```bash
git clone https://github.com/siva2526k-art/SENTINEL-AI.git
cd SENTINEL-AI
```

### 2. Create Virtual Environment & Install Dependencies
```bash
python -m venv venv
# On Windows:
.\venv\Scripts\activate
# On Linux/macOS:
source venv/bin/activate

pip install -r requirements.txt
```

### 3. Configure Environment Variables
```bash
cp .env.example .env
# Edit .env with your optional API keys (Groq / Gemini) or use 100% offline Ollama:
# OLLAMA_HOST=http://localhost:11434
# OLLAMA_MODEL=deepseek-r1:8b
```

### 4. Run the 10-Level Prototype Verification Suite
```bash
python scripts/test_all_prototype_levels.py
```

### 5. Run an Autonomous Triage Demo Scenario
```bash
python -m src.demo_runner --scenario 1
```

### 6. Launch the REST API & Webhook Ingestor
```bash
uvicorn src.api.main:app --host 0.0.0.0 --port 8000 --reload
```
Access the interactive Swagger documentation at: `http://localhost:8000/docs`

---

## 🏆 Proven Recognition
* **National Finalist & Pitching Selectee at Hac'KP 2026** — National Cyber Hackathon organized by Kerala Police Cyberdome @ Zoho Corporation Campus, Tenkasi.

---

## 📜 Ethical AI Disclosure & Licensing
* **AI Disclosure:** In accordance with open-source ethical standards, AI tools (Antigravity IDE / Gemini) were utilized for code boilerplate scaffolding and documentation formatting (~25% of development effort), while all core security algorithms, in-RAM tokenization logic, AST opcode sandboxing, and system architecture were independently conceptualized and authored by **Sivabalan T**.
* **License:** Licensed under the [Apache License 2.0](LICENSE).
