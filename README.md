🧠 AI-Powered RAG Chatbot for Dynamic Document Intelligence
🚀 Overview
This repository presents a robust, production-ready AI-powered Retrieval-Augmented Generation (RAG) chatbot workflow. Engineered with n8n for orchestration, Google Drive for document management, Google Gemini (PaLM) and OpenAI for advanced language capabilities, and Qdrant Cloud for efficient vector search, this solution revolutionizes how users interact with their documents. It facilitates seamless, context-aware conversations by grounding responses in the latest, most relevant information, thereby overcoming the limitations of static Large Language Model (LLM) knowledge.

✨ Key Features
Intelligent Document Ingestion: Automated fetching and processing of documents directly from Google Drive, ensuring your knowledge base is always current.

Sophisticated Metadata Extraction & Embeddings: Leverages cutting-edge LLMs (OpenAI, Gemini) for precise metadata extraction and high-quality vector embeddings, enabling semantic understanding.

Optimized Vector Storage & Retrieval: Utilizes Qdrant Cloud for scalable and lightning-fast storage and retrieval of document vectors, powering efficient semantic search.

Dynamic Conversational AI: A natural language chat interface, powered by Gemini and OpenAI, delivers contextually rich and highly relevant responses.

Human-in-the-Loop Safeguards: Integrates Telegram for critical operational approvals (e.g., vector deletions), ensuring data integrity and control.

Modular & Extensible Workflow: Built with a modular n8n workflow design, allowing for easy customization, maintenance, and scalable deployment.

🏗️ High-Level Architecture
The system's architecture is meticulously designed for performance and reliability:

graph TD;
    User-->|Chat/Query|n8n
    n8n-->|Ingests|GoogleDrive
    n8n-->|Embeddings|OpenAI
    n8n-->|Embeddings|Gemini
    n8n-->|Store/Retrieve|QdrantCloud
    n8n-->|Notifications|Telegram
    n8n-->|Response|User

n8n: Serves as the central orchestration engine, seamlessly connecting all integrated services.

Google Drive: Acts as the primary source for all ingested documents, ensuring centralized document management.

OpenAI & Google Gemini: Provide versatile LLM capabilities, handling both advanced natural language understanding and high-fidelity embedding generation.

Qdrant Cloud: The backbone for vector storage and semantic search, delivering rapid and accurate context retrieval.

Telegram: (Optional) Facilitates real-time notifications and enables human oversight for critical workflow decisions.

⚡ Quick Start Guide
Get your AI-powered RAG chatbot up and running swiftly:

Review SETUP.md: Begin by checking all prerequisites and following the comprehensive step-by-step setup guide.

Import Workflow: Load the provided n8n workflow JSON file directly into your n8n instance.

Configure Credentials: Securely set up all necessary API keys and environment variables for Google, OpenAI, Gemini, Qdrant, and Telegram.

Engage: Populate your designated Google Drive folder with documents, and start interacting with your intelligent AI chatbot!

📚 Comprehensive Documentation
SETUP.md: Contains detailed setup instructions, environment variable configurations, and robust testing procedures.

TECHNICAL_DOCUMENTATION.md: Provides an in-depth exploration of the technical approach, intricate workflow design, and core code components.
