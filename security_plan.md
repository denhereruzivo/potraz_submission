# Security, Privacy & Responsible AI Safeguards
### AI-Based QMS Research & Practitioner Assistant

This document outlines the security controls, data protection policies, and responsible AI safeguards engineered into the QMS system.

---

## 🔒 Security & Data Protection Controls

Quality Management Systems contain sensitive organizational procedures, operational audit reports, and employee details. The system adopts a **Medium-to-High Risk** security control posture:

### 1. Identity & Access Control (RBAC)
We enforce a strict Role-Based Access Control (RBAC) matrix:
* **Administrator**: System setup, API key management, audit logs inspection, and full database access.
* **Quality Manager**: Draft, edit, and approve SOPs and policies. Can view audit findings.
* **Internal Auditor**: Create audit logs, write non-conformity reports, and initiate RCA workflows. Cannot edit approved SOPs.
* **General Employee**: Read-only access to approved SOPs and policies.

### 2. Encryption Standards
* **In-Transit**: All communication between the Web UI, API backend, and database is encrypted using TLS 1.3.
* **At-Rest**: Postgres database storage and uploaded files (PDFs, templates) are encrypted using AES-256.
* **Vector Database**: Pinecone vector endpoints utilize secure HTTPS with API keys kept as server-side secrets.

### 3. Secrets Management
* No credentials, passwords, or LLM API keys are committed to the code repository.
* All keys are injected via an environment configuration file (`.env`) on the host system.

---

## 🛡️ Responsible AI & Guardrails

### 1. Human-in-the-Loop Gate
Because QMS documents govern physical operations (such as e-waste handling or electrical calibrations), **unreviewed AI output must never be directly published**.
* **Draft Flagging**: Any document created by the *Procedure* or *Policy Agent* is marked as `[DRAFT - AI Generated]` and cannot be exported or distributed.
* **Approval Step**: A Quality Manager must manually review the document in the **Document Editor**, make necessary edits, and click "Approve and Sign" to clear the draft flag.

### 2. Context Grounding (RAG Guardrails)
To prevent hallucinations where the LLM might fabricate a standard requirement:
* The prompt templates restrict the model to *only* base its answers on the matching ISO clauses retrieved from the Vector DB.
* If no relevant clauses are found, the system is instructed to output: *"I cannot find reference clauses in the standard. Please consult the official manual."*

### 3. Data Minimisation & Compliance
* The system does not require or collect Personal Identifiable Information (PII) of employees beyond basic audit logging credentials (auditor name, email).
* Organizations can opt to host the database and vector index locally, keeping all operational knowledge within their private network.
