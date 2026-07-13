# User Journey Map
### AI-Based QMS Research & Practitioner Assistant

This document outlines the target user personas and maps their step-by-step interactions with the QMS system.

---

## 👥 User Personas

### 1. Tendai, Quality Management Specialist
* **Role**: Quality Manager at a large infrastructure organization.
* **Goals**: Regularly update Standard Operating Procedures (SOPs) and corporate quality policies to maintain compliance with ISO 9001 and ISO 14001.
* **Pain Points**: Spends days cross-referencing dense, technical ISO documents against old company templates. Reviewing updates with department heads is slow.
* **System Need**: A fast way to generate regulatory-compliant SOP drafts and policies using company templates.

### 2. Ruvimbo, Lead Compliance Auditor
* **Role**: Internal Auditor.
* **Goals**: Identify process gaps, document non-conformities during internal audits, and guide departments toward effective corrective actions.
* **Pain Points**: Documenting non-conformities is tedious. Teams often write weak Root Cause Analyses (RCAs) that fail to identify the core issue, resulting in recurring audit findings.
* **System Need**: A tool that converts raw audit notes into structured non-conformity records and guides departments through a robust RCA process.

---

## 🗺️ Core User Journeys

### Journey 1: Writing an Environmental Waste SOP (Tendai)

```
[Define Topic] ──> [Query AI Assistant] ──> [RAG Lookup] ──> [Review & Edit] ──> [Export & Publish]
```

1. **Initiation**: Tendai needs to draft a new SOP for *E-Waste Disposal* to comply with a new environmental mandate (ISO 14001).
2. **Form Interaction**: Tendai navigates to the **User Input Forms** in the Web Interface. He selects "SOP Creation Form".
3. **Drafting Parameters**:
   * He enters the scope: *E-waste disposal in regional warehouses*.
   * He selects the standard: *ISO 14001 (Clause 8.1 - Operational Planning and Control)*.
   * He uploads a sample organizational template.
4. **Agent Action**: The **Procedure Agent** coordinates with the RAG database to pull specific Zimbabwean waste disposal rules and ISO 14001 clauses, feeding them to the AI Engine.
5. **Editing**: Within seconds, the generated draft appears in the **Document Editor**. Tendai reviews it, adjusts localized vocabulary, and locks the document for final approval.

---

### Journey 2: Logging an Audit Finding & Performing RCA (Ruvimbo)

```
[Log Finding] ──> [Structured Audit Report] ──> [Request RCA] ──> [Corrective Action Suggestions] ──> [Log to CAPA DB]
```

1. **On-Site Logging**: During an inspection, Ruvimbo finds that warehouse staff are not recording daily calibration records.
2. **Input**: Ruvimbo opens the QMS app on her tablet, goes to "Log Non-Conformity", and enters raw notes: *"Calibration logs missing for past 3 days in Harare North warehouse. Operators said they forgot."*
3. **Structured Build**: The **Audit Agent** processes the input and structures it into a formal Non-Conformity Report, mapping it directly to **ISO 9001 (Clause 8.5.1 - Control of production and service provision)**.
4. **RCA Assistance**: The system automatically prompts: *"Would you like to initiate a Root Cause Analysis?"*
5. **RCA Generation**: The **Root Cause Agent** uses the "5 Whys" method to query similar historical records. It suggests potential root causes (e.g., lack of automated reminders, training gaps) and proposes a corrective action plan:
   * *Correction*: Immediate calibration check.
   * *Corrective Action*: Implement a digital reminder system and retrain warehouse supervisors.
6. **Resolution**: Ruvimbo approves the RCA and registers the plan in the **Corrective Action Database**.
