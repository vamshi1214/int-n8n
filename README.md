# int-n8n
AI Powered RAG Chatbot for Your Docs + Google Drive + Gemini + Qdrant Cloud
![Google Gemini](https://img.shields.io/badge/google%20gemini-8E75B2?style=for-the-badge&logo=google%20gemini&logoColorimg.shields.io/badge/openai-412991?style=for-the-badge&logo=openai&logoColor=white](https://img.shields.io/badge/qdrant-4B8BBE?style=for-the-badge&logo=qdrant://img.shields.io/badge/n8n-FF6A00?style=for-the-badge&logo=n8n&logoColor=white](https://img.shields.io/badge/google%20drive-4285F4?style=for-the-badge&logo=google-drive&logoColor=white.shields.io/badge/telegram-26A5E4?style=for-the-badge&logo=telegram&logoColor= Overview
This repository delivers a production-ready, AI-powered Retrieval-Augmented Generation (RAG) chatbot workflow using n8n, Google Drive, Google Gemini (PaLM), OpenAI, and Qdrant Cloud. The solution enables seamless, context-aware conversations with your documents, leveraging state-of-the-art LLMs and vector search for highly relevant answers23.
✨ Features
Document Ingestion: Automatically fetch and process documents from Google Drive.
Metadata Extraction & Embeddings: Use OpenAI and Gemini for extracting metadata and generating high-quality embeddings.
Vector Storage & Retrieval: Store and search document vectors efficiently with Qdrant Cloud.
Conversational AI: Chat interface powered by Gemini and OpenAI for natural, context-rich responses.
Human-in-the-Loop: Telegram-based approval for critical operations (e.g., vector deletions).
Modular Workflow: Easily extensible n8n workflow for rapid customization and scaling23.
🏗️ High-Level Architecture

graph TD;
    User-->|Chat/Query|n8n
    n8n-->|Ingests|GoogleDrive
    n8n-->|Embeddings|OpenAI
    n8n-->|Embeddings|Gemini
    n8n-->|Store/Retrieve|QdrantCloud
    n8n-->|Notifications|Telegram
    n8n-->|Response|User

Architecture visualized using Mermaid for clarity and GitHub compatibility42.

n8n: Orchestrates the entire workflow, connecting all services.
Google Drive: Serves as the document source.
OpenAI & Gemini: Provide LLM and embedding capabilities.
Qdrant Cloud: Handles vector storage and semantic search.
Telegram: (Optional) For notifications and human approvals24.
⚡ Quick Start
Review SETUP.md: Check prerequisites and follow the step-by-step setup guide.
Import Workflow: Load the provided n8n workflow JSON into your n8n instance.
Configure Credentials: Set up API keys and environment variables for Google, OpenAI, Gemini, Qdrant, and Telegram as needed.
Start Chatting: Place your documents in the designated Google Drive folder and interact with your AI chatbot!32
📚 Documentation
SETUP.md: Complete setup instructions, environment variables, and testing procedures.
TECHNICAL_DOCUMENTATION.md: In-depth technical approach, workflow design, and code components23.
