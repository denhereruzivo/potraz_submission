# Annex B: Deployment & Operational Plan
### AI-Based QMS Research & Practitioner Assistant

This document contains the completed deployment and operations plan requested in Annex B of the AI4I Product Readiness guidelines.

---

| Field | Participant Response |
| :--- | :--- |
| **Deployment Environment** | **Hybrid / Institutional System**:<br>• The web frontend and database are hosted on a localized Zimbabwean cloud instance.<br>• Metadata databases can also run on local servers within target organizations to comply with data privacy policies regarding internal procedures. |
| **Hosting Provider or Site** | • **Local Zim Cloud Hosting**: TelOne Cloud, Liquid Intelligent Technologies, or Econet/Cassava Smarttech data centers in Harare for localized, high-speed regional access.<br>• **Alternative/On-Premise Option**: Deployed on local VMware/Proxmox servers within the public or private enterprise server rooms (e.g. POTRAZ headquarters). |
| **Operator** | • Primary operation and technical maintenance will be managed by the development team (SaaS model).<br>• The organization's internal IT systems administrator will manage user directories, API keys, and local backups. |
| **Pilot Site** | • **POTRAZ (Postal and Telecommunications Regulatory Authority of Zimbabwe)** or a selected local partner manufacturing firm seeking ISO 9001/14001 certification. |
| **Users to Onboard** | • **Initial Batch**: 15–20 core users including 3 Quality Managers, 5 Internal Auditors, and 12 Departmental Compliance Representatives. |
| **Training & Support** | • **Onboarding**: A 2-day hands-on workshop with auditors and managers.<br>• **In-App support**: Walkthrough tooltips, a searchable PDF user manual, and a dedicated feedback button.<br>• **Ticketing**: Email/WhatsApp Business support channel for prompt bug logging. |
| **Monitoring** | • **Application Health**: Uptime Kuma for checking system availability.<br>• **Usage Logs**: Audit trails recording user actions, document creation stats, and system latency metrics. |
| **Backup & Recovery** | • **PostgreSQL Database**: Automated daily incremental backups stored in an isolated, encrypted S3 bucket.<br>• **Recovery Point Objective (RPO)**: 24 hours.<br>• **Recovery Time Objective (RTO)**: Under 2 hours. |
| **Connectivity Plan** | • **Zimbabwe Context Optimization**:<br>1. **Offline Mode**: Local storage cache stores audit logging forms. Users can record audit findings on their tablets in connectivity-dead zones; data auto-syncs when reconnecting to Wi-Fi/4G.<br>2. **Payload Reduction**: Images uploaded during audits are compressed client-side before submission. |
| **Scale Pathway** | • **Phase 1**: Pilot testing at the designated institution (1 month).<br>• **Phase 2**: Standardize template support for broader compliance rules (ISO 27001, OHSAS 18001) and release to 3-5 external companies.<br>• **Phase 3**: Transition to a multi-tenant commercial SaaS platform. |
| **Milestones** | • **30-Day**: Finalize UI wireframes, complete the Vector DB pipeline structure, and run sample query validation tests.<br>• **60-Day**: Launch the web prototype with forms and basic agent generation; conduct usability tests with 5 pilot users.<br>• **90-Day**: Implement offline forms, integrate user feedback into the document editor, compile final reports, and run security compliance checks. |
