# Enterprise AI Lead-to-Appointment & CRM Engine

An end-to-end autonomous lead qualification and CRM orchestration engine built in n8n and powered by Google Gemini. This enterprise workflow ingests raw leads, standardizes and validates data, manages CRM contact states, leverages an AI Qualification Agent to assess conversion fit, creates pipeline opportunities, and crafts personalized executive follow-up emails.

---

## 📌 Workflow Architecture

<img width="1665" height="918" alt="image" src="https://github.com/user-attachments/assets/136f58c2-8b41-4df0-938e-7397081741f5" /><img width="1655" height="926" alt="image" src="https://github.com/user-attachments/assets/02bc0736-e9ba-4a01-93ca-29bd92138c4b" />



### Key Process Stages:

1. **Lead Ingestion & Data Sanitization:**
   - Ingests inbound leads via Webhooks.
   - Cleans and standardizes incoming contact parameters.
   - Validates data integrity (filters invalid leads into a Google Sheet for audit).

2. **CRM Contact Search & Synchronization:**
   - Queries CRM endpoints to verify contact existence.
   - Dynamically branches to either update existing contact profiles or generate new CRM contact entities.

3. **Autonomous AI Lead Qualification:**
   - Ingests standardized context into a specialized **Google Gemini Chat Model** agent.
   - Analyzes intent, company fit, and buyer readiness against qualification criteria.
   - Parses qualification outputs into structured decision parameters.

4. **Dynamic Severity & Qualification Routing:**
   - **Qualified Leads:**
     - Checks and updates/creates Opportunity deals in the CRM pipeline.
     - Hands off data to a **Personalized Message Generation Agent (Gemini)**.
     - Dispatches tailored outreach and appointment invitations via Gmail.
   - **Unqualified Leads:**
     - Tags lead records inside CRM for follow-up nurturing.
     - Logs disqualified inquiries into audit sheets for analysis.

---

## 🛠 Tech Stack
- **Automation & Orchestration:** n8n
- **AI / LLM Engine:** Google Gemini Chat Models
- **CRM Integration:** REST APIs / HTTP Request Nodes
- **Outreach & Logging:** Gmail API, Google Sheets API

---

## 🚀 Setup & Deployment

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/malikzafarabbasawan5/enterprise-ai-lead-to-appointment-crm-engine.git](https://github.com/malikzafarabbasawan5/enterprise-ai-lead-to-appointment-crm-engine.git)
