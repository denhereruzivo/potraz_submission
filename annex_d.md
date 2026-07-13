# Annex D: Backend Architecture Specifications
### AI-Based QMS Research & Practitioner Assistant

This document contains the completed backend architecture questionnaire requested in Annex D of the AI4I Product Readiness guidelines.

---

| Architecture Item | Participant Response |
| :--- | :--- |
| **Users** | • **Internal Auditors**: Query standards, compile audit findings, build non-conformities.<br>• **Quality & Compliance Managers**: Draft SOPs, write organizational policies, track corrective actions.<br>• **Operational Supervisors**: Perform Root Cause Analyses (RCAs) and follow up on corrective actions. |
| **Access Channel** | • **Primary Channel**: Responsive Web Application (optimized for desktop document editing and tablet-based audit walks).<br>• **Offline Channel**: Service Worker-cached forms for local storage data capture when offline. |
| **Frontend** | • **Framework**: HTML5, Vanilla JavaScript, and Tailwind CSS (or standard CSS grid layout) to minimize compilation overhead and ensure high performance on local devices.<br>• **Libraries**: Lightweight editor library (e.g., Quill or Tiptap) for document editing. |
| **Backend** | • **Framework**: Python (FastAPI) due to native compatibility with AI libraries, asynchronous performance, and simple API routing.<br>• **App Server**: Uvicorn running inside a Docker container. |
| **Database** | • **Relational Database**: PostgreSQL (for user profiles, audit logs, and the Corrective Actions/CAPA database).<br>• **Vector Database**: Pinecone (serverless index) or Weaviate (locally hosted instance) to run cosine-similarity queries for RAG context retrieval.<br>• **File Storage**: MinIO or AWS S3 for saving finalized PDF/Markdown compliance documents. |
| **AI Layer** | • **Embedding Model**: `text-embedding-3-small` (1536-dimensional vectors).<br>• **Inference LLM**: Gemini 1.5 Flash (low latency, 1M context window for processing entire ISO manual PDFs) or Claude 3.5 Sonnet (for complex reasoning during Root Cause Analysis).<br>• **Framework**: LangChain/LlamaIndex for vector search retrieval routing. |
| **Integrations** | • **Authentication**: OpenID Connect / OAuth2 (using Auth0 or local Supabase Auth).<br>• **Exports**: PDF/Docx compilation utility (using Python libraries like `reportlab` or `python-docx`).<br>• **Notification Gateway**: SendGrid (email) and Twilio (SMS) for automated alerts when non-conformities are logged. |
| **Security** | • **Auth**: Role-Based Access Control (RBAC) separating Auditor, Manager, and Viewer permissions.<br>• **Encryption**: TLS 1.3 in-transit; AES-256 for database storage at-rest.<br>• **Secrets**: Decoupled environment variables injected via vault/secrets manager (no keys in code). |
| **Monitoring** | • **Application Metrics**: Prometheus and Grafana for monitoring API latency and error rates.<br>• **Logging**: Winston or Python standard logger outputting structured JSON logs to a centralized server. |
| **Outputs** | • **Compliance Artifacts**: Formally structured PDF/Docx SOPs, Policies, and Non-Conformity reports.<br>• **Workflows**: Corrective Action (CAPA) tracking boards and progress dashboards. |
