# sintesia-architecture-overview
Architectural overview of SintesIA: An AI-first CRM and autonomous SDR ecosystem built with n8n, Claude, and RAG.

# SintesIA: AI-First CRM & Autonomous SDR Ecosystem 🚀

*Note: The core application is a private B2B SaaS behind a login wall. This repository serves as an architectural overview of the autonomous AI layer.*

## 🧠 Architecture Overview
SintesIA is a GTM and CRM platform built from the ground up to automate lead qualification and revenue operations. The core engine relies on an autonomous AI agent (SDR) that interacts with leads in real-time, extracts business context via RAG, and injects validated JSON payloads directly into the CRM.

## 🛠️ Tech Stack
* **Workflow Orchestration:** n8n 
* **AI / LLM:** Anthropic Claude 3.5 Sonnet / OpenAI (GPT-4o)
* **Data Context:** RAG (Retrieval-Augmented Generation) for strict business rules
* **Frontend:** React, Tailwind CSS
* **Backend/Database:** Supabase (PostgreSQL)
* **Channels:** WhatsApp Business API

## ⚙️ How the Autonomous Layer Works (Unattended)
1. **Ingestion:** Lead interacts via WhatsApp. Webhooks capture the payload.
2. **Context Retrieval (RAG):** The system queries the vector database for the specific commercial rules, pricing, and availability.
3. **Agent Execution:** The LLM is prompted via n8n to act as an SDR, strictly using the retrieved context to avoid hallucinations.
4. **Data Validation:** Before touching the CRM, the agent must output a strict JSON schema. The n8n workflow includes fallback routes to handle schema failures.
5. **CRM Injection:** Validated data updates the pipeline stages automatically, enabling human sales reps to focus only on closing.

*(I am highly open to providing a live technical demonstration of the n8n backend and React frontend during an interview).*
