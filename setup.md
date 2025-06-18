# 🚀 AI Powered RAG Chatbot Setup Guide  
*Seamless Knowledge Retrieval with n8n, Google Drive, Gemini, and Qdrant Cloud*

---


## 🌟 Overview

Welcome to the ultimate guide for deploying a **Retrieval-Augmented Generation (RAG) Chatbot** using **n8n**, **Google Drive**, **Google Gemini**, and **Qdrant Cloud**. This solution empowers you to build a scalable, production-ready AI assistant that can ingest, index, and answer questions from your documents in real time, with optional Telegram-based approval flows for secure operations[#8][#11].

---

## 📋 Table of Contents

- [Prerequisites](#prerequisites)
- [Dependencies](#dependencies)
- [Step-by-Step Setup](#step-by-step-setup)
- [Environment Variables](#environment-variables)
- [Testing Procedures & Sample Queries](#testing-procedures--sample-queries)
- [Best Practices & Tips](#best-practices--tips)
- [License](#license)
- [Acknowledgments](#acknowledgments)

---

## 🛠 Prerequisites

- **n8n** (self-hosted or cloud, latest stable version recommended)[#16]
- **Qdrant Cloud** account and collection ([cloud.qdrant.io](https://cloud.qdrant.io))[#13]
- **Google Drive** account and OAuth2 credentials
- **Google Gemini (PaLM) API** access and credentials
- **OpenAI API** key (for embeddings and chat models)
- **Telegram Bot** (optional, for approval/notifications)
- **Node.js** (for custom code execution in n8n)

---

## 📦 Dependencies

- n8n nodes for:
  - LangChain (OpenAI, Qdrant, Google Gemini)
  - Google Drive and Google Docs
  - Telegram (optional)
- Qdrant Cloud account and API key
- OpenAI and Google Gemini API access[#10][#11]

---

## 🚦 Step-by-Step Setup

### 1. Install and Start n8n

- Follow the [n8n installation guide](https://docs.n8n.io/hosting/installation/) for your OS.
- Start n8n and access the UI[#16].

### 2. Set Up Qdrant Cloud

- Sign up at [Qdrant Cloud](https://cloud.qdrant.io) and create a new cluster/collection (e.g., `nostr-damus-user-profiles`).
- Note your Qdrant Cloud URL and API key (e.g., `https://<cluster-id>.<region>.aws.cloud.qdrant.io:6333`)[#13].

### 3. Configure Google Drive and Docs

- Set up OAuth2 credentials in n8n for Google Drive and Docs.
- Share the target folder/document with the service account if needed[#8].

### 4. Configure OpenAI and Google Gemini

- Add your OpenAI and Google Gemini API keys in n8n credentials[#10].

### 5. Configure Telegram (Optional)

- Set up a Telegram bot and add credentials in n8n for approval flows.

### 6. Import the Workflow

- In n8n, import `AI Powered RAG Chatbot for Your Docs + Google Drive + Gemini + Qdrant.json`.

### 7. Set Environment Variables

- In n8n, set the following environment variables as needed:
  - `TELEGRAM_CHAT_ID` (for Telegram notifications)
  - Any API keys not set via n8n credentials

### 8. Update Workflow Parameters

- Set your Google Drive Folder ID and Qdrant collection name in the relevant nodes.
- Update any hardcoded values (e.g., `[Your-Google-Folder-ID]`, `[Your-OpenAI-API-Key]`, Qdrant Cloud URL/API key).

---

## ⚙️ Environment Variables

| Variable              | Purpose                                      | Example Value                                          |
|-----------------------|----------------------------------------------|----------------------------------------------------    |
| `TELEGRAM_CHAT_ID`    | Chat ID for Telegram notifications/approvals | `123456789`                                            |
| `OPENAI_API_KEY`      | OpenAI API key (if not set in n8n credentials) | `sk-...`                                             |
| `GOOGLE_PALM_API_KEY` | Google Gemini API key (if not set in n8n credentials) | `AIza...`                                     |
| `QDRANT_URL`          | Qdrant Cloud endpoint                        | `https://abc123.eu-central-1.aws.cloud.qdrant.io:6333` |
| `QDRANT_API_KEY`      | Qdrant Cloud API key                         | `qdrant-...`                                           |

---

## 🧪 Testing Procedures & Sample Queries

### 1. Test Data Ingestion

- Place sample documents in the configured Google Drive folder.
- Trigger the workflow manually or via the chat trigger[#8][#11].

### 2. Test Chatbot

- Send a chat message (via the chat trigger or webhook).
- The workflow should retrieve relevant information from Qdrant and respond using Gemini/OpenAI.

### 3. Test Deletion Flow

- Use the Telegram approval flow to test deletion of vectors from Qdrant.

### 4. Sample Queries

- "What are the main themes discussed in the user profiles?"
- "List recurring topics from the documents."
- "Summarize the pain points mentioned."

---

