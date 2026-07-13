# Annex A: Business Model & Sustainability Plan
### AI-Based QMS Research & Practitioner Assistant

This document contains the completed business model and sustainability plan requested in Annex A of the AI4I Product Readiness guidelines, addressing key operating costs, sustainability structures, and financial assumptions.

---

## 📊 Business Model Canvas (Annex A Template)

| Field | Participant Response |
| :--- | :--- |
| **Problem** | Quality Management Specialists and Auditors spend days manually cross-referencing complex ISO standards (9001, 14001) with internal procedures, leading to delays, administrative fatigue, and critical compliance gaps (e.g., weak Root Cause Analyses). |
| **Primary User** | • **Tendai** (Quality Management Specialist): Needs fast, standard-compliant SOP and policy drafts.<br>• **Ruvimbo** (Lead Compliance Auditor): Needs to easily log audit findings and formulate robust corrective action plans. |
| **Beneficiary** | • The host organization (avoids non-compliance penalties, maintains ISO certification).<br>• Departmental supervisors and staff who get clear, actionable SOPs. |
| **Customer or Payer** | • Regulatory authorities (e.g., POTRAZ), governmental departments, and medium-to-large enterprises seeking to establish or maintain ISO compliance. |
| **Value Proposition** | • Reduces compliance audit preparation and SOP drafting time by up to 70%.<br>• Minimizes recurring audit findings through structured, automated Root Cause Analyses. |
| **Revenue or Funding Model** | • **Pay-per-Token Model**: Users and organizations buy token credits (bundles of generation credits) to run AI SOP drafting, Policy creation, and Root Cause Analysis.<br>• **Local Mobile Money Payments**: Integrated via gateways like Paynow to accept local payment methods (EcoCash, OneMoney) and international cards (Visa/Mastercard) for purchasing token credits. |
| **Cost Drivers** | • LLM API inference costs (Gemini & Claude).<br>• Local Zimbabwean VPS/Server space hosting.<br>• Personnel for system setup, maintenance, and integration of local payment gateways. |
| **Partnerships** | • **Standards Association of Zimbabwe (SAZ)**: For official ISO documentation updates.<br>• **Local Payment Gateways (e.g., Paynow)**: To facilitate token purchases via EcoCash/OneMoney.<br>• **Local Zimbabwean Hosting Providers (e.g., TelOne, Liquid Intelligent Technologies)**: For local server infrastructure. |
| **Pilot Market** | • POTRAZ Compliance and Internal Quality Management departments. |
| **Adoption Risks** | • **Data Sovereignty**: Addressed by hosting on local Zim server space.<br>• **Payment Friction**: Mitigated by providing simple mobile money payments for token top-ups. |
| **Success Metrics** | • **30-Day**: Integrate local hosting and payment gateways; onboard 20 pilot users with initial free token allocations.<br>• **60-Day**: Record 100+ paid token top-up transactions; run 20+ SOP/Audit drafts.<br>• **90-Day**: Transition 100% of pilot users to self-sustained token purchases. |

---

## 💰 Detailed Operating Costs & Assumptions

To ensure the long-term sustainability of the QMS assistant, we have mapped out key financial assumptions and projected monthly operating costs under a local hosting and token-based monetization model.

### 1. Key Cost Drivers & Estimates

Assuming a pilot group of **20 active users** at a single institution querying the locally hosted app:

| Cost Category | Description | Monthly Cost (USD) |
| :--- | :--- | :--- |
| **AI LLM APIs** | Gemini 1.5 Flash API calls (for drafting SOPs, Policies, and conducting RAG queries). | ~$15.00 |
| **Vector Database** | Pinecone Serverless or Weaviate locally hosted (storing indexed ISO clauses). | ~$10.00 |
| **Local Zim Hosting** | Local VPS hosting package (e.g., TelOne Cloud or Liquid Intelligent Technologies server space). | ~$45.00 |
| **Payment Gateway Fees** | Paynow/EcoCash transaction processing fees (approx. 2% on credit purchases). | ~$10.00 |
| **User Support & Maintenance**| Local developer/support support retainer for troubleshooting and gateway maintenance. | ~$150.00 |
| **Total Estimated Operating Cost**| | **~$230.00 / month** |

### 2. Financial & Token-Based Assumptions

* **Token Consumption & Pricing**:
  * Users buy token credit bundles (e.g., $10 for 50 compliance queries/generations).
  * A single query costs the user approximately $0.20, while only costing us ~$0.002 in Gemini 1.5 Flash API fees (based on 10k input tokens + 1.5k output tokens).
  * This creates a high-margin revenue model where token sales comfortably cover the fixed local hosting and support costs of $230/month once the user base exceeds ~1,200 queries/month.
* **Zimbabwe Context Integration**:
  * Payments are integrated with Paynow to allow checkout via **EcoCash** or **OneMoney**, keeping the onboarding frictionless for Zimbabwean compliance professionals.
* **Onboarding & Training Cost**: A one-time setup cost of $500 is budgeted for running the 2-day on-site training workshop and configuring the pilot database.

