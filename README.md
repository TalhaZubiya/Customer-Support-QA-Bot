# Customer Support Q&A Bot

An AI-powered customer support chatbot built with n8n, OpenAI, Pinecone, and Retrieval-Augmented Generation (RAG).

<p align="center">
  <img src="https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white" alt="n8n">
  <img src="https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white" alt="OpenAI">
  <img src="https://img.shields.io/badge/Pinecone-Vector_DB-000000?style=for-the-badge" alt="Pinecone">
  <img src="https://img.shields.io/badge/RAG-AI%20Knowledge%20Retrieval-6C47FF?style=for-the-badge" alt="RAG">
</p>

---

## Overview

This project demonstrates how a customer support system can use a company knowledge base to answer customer questions without relying only on the language model's general knowledge.

The workflow combines:

- AI Agent
- Retrieval-Augmented Generation (RAG)
- Vector database
- Semantic search
- Conversation memory
- Automated knowledge ingestion
- Customer-facing chat interface

The fictional SaaS company used in this project is **Clario**, with **Clario Workspace** as its product.


---

## How It Works

Customer
   │
   ▼
Chat Interface
   │
   ▼
Customer Support AI Agent
   │
   ├──────────────► Conversation Memory
   │
   ▼
Knowledge Base Search
   │
   ▼
Pinecone Vector Database
   │
   ▼
Relevant Knowledge
   │
   ▼
AI Agent
   │
   ▼
Customer Response

The knowledge base is converted into embeddings and stored in Pinecone. When a customer asks a question, the AI Agent retrieves relevant information from the knowledge base and generates a response using the retrieved context.

---

## Key Features

### AI Customer Support

Answers customer questions using an AI Agent connected to a company knowledge base.

### RAG Knowledge Retrieval

Retrieves relevant information from the knowledge base before generating an answer.

### Vector Search

Uses Pinecone for semantic similarity search across stored knowledge.

### Conversation Memory

Maintains recent conversation context to provide more natural interactions.

### Automated Knowledge Ingestion

A separate n8n workflow monitors Google Drive for new knowledge files and stores their content in the vector database.

### SaaS Support Use Case

The knowledge base covers realistic SaaS topics such as:

- Account management
- Workspaces
- Team members
- User roles
- Customer management
- Support tickets
- Billing
- Subscription plans
- Security
- Integrations
- Automation
- Troubleshooting

---

## Tech Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and AI orchestration |
| OpenAI | AI model and embeddings |
| Pinecone | Vector database and semantic search |
| RAG | Knowledge-grounded responses |
| Google Drive | Knowledge base source |
| Chat Trigger | Customer interaction |
| Simple Memory | Conversation context |

---

## Project Architecture

The project contains two main workflows.

### 1. Knowledge Base Ingestion

Google Drive
     │
     ▼
New Document Trigger
     │
     ▼
Download Knowledge File
     │
     ▼
Document Loader
     │
     ▼
OpenAI Embeddings
     │
     ▼
Pinecone

This workflow prepares company knowledge for semantic retrieval.

### 2. Customer Support Q&A

Customer Query
     │
     ▼
Chat Trigger
     │
     ▼
AI Agent
     │
     ├──► Conversation Memory
     │
     └──► Knowledge Base Search
                 │
                 ▼
              Pinecone
                 │
                 ▼
          Relevant Information
                 │
                 ▼
              AI Agent
                 │
                 ▼
          Customer Response

---

## Knowledge Base

The project uses a fictional SaaS company named **Clario**.

The knowledge base contains information about:

- Company overview
- Getting started
- Account management
- Workspaces
- Team members
- Roles and permissions
- Customer management
- Support tickets
- AI customer support
- Billing
- Subscription plans
- Security and privacy
- Integrations
- Automation
- Troubleshooting
- Support escalation

This allows the chatbot to simulate a realistic SaaS customer support environment.

---

## Example Questions

The chatbot can answer questions such as:

- How do I create a Clario account?
- How can I reset my password?
- How do I invite a team member?
- What are the different user roles?
- What subscription plans does Clario offer?
- How can I upgrade my subscription?
- How do I cancel my subscription?
- What integrations does Clario support?
- Why didn't my automation run?
- Where can I find my invoices?
- Can I export my customer data?
- How can I contact Clario Support?

---

## AI Response Policy

The AI Agent is designed to prioritize information retrieved from the Clario Knowledge Base.

It should:

- Use the knowledge base when relevant information is available.
- Avoid inventing company policies or features.
- Avoid claiming that an action was completed unless a connected tool actually performed it.
- Provide accurate and concise customer support responses.
- Escalate questions when the available knowledge is insufficient.

---

## Repository Structure

Customer-Support-QA-Bot/
│
├── workflows/
│   ├── Customer-Support-QA-Bot.json
│   └── Customer-Support-QA-Bot-Part-1.json
│
├── knowledge-base/
│   └── Clario-Customer-Support-Knowledge-Base.pdf
│
├── screenshots/
│   ├── chatbot.png
│   └── n8n-workflow.png
│
└── README.md

---

## Setup

### 1. Import the Workflows

Import the provided JSON workflow files into n8n.

### 2. Configure Credentials

Connect your own credentials for:

- OpenAI
- Pinecone
- Google Drive

API keys and credentials are intentionally not included in this repository.

### 3. Configure Pinecone

Create a Pinecone index and connect it to the vector store node.

### 4. Add the Knowledge Base

Upload the Clario knowledge base to Google Drive and configure the Google Drive nodes according to your environment.

### 5. Run the Ingestion Workflow

Run the knowledge ingestion workflow to process the document and store its embeddings in Pinecone.

### 6. Start the Chatbot

Activate the customer support workflow and use the n8n chat interface to test customer questions.

---

## Security

No API keys, passwords, or private credentials are included in this repository.

Before importing or running the workflows, configure your own credentials inside n8n.

---

## Project Purpose

This project was built to practice and demonstrate:

- AI Agents
- RAG pipelines
- Vector databases
- Semantic search
- n8n automation
- AI-powered customer support
- Knowledge-grounded AI systems

It represents a practical example of combining AI with automation to build a useful business workflow.

---

## Author

**Talha Zubiya**

CSE Student | AI Agent & Automation Builder

[GitHub](https://github.com/TalhaZubiya) • [LinkedIn](https://www.linkedin.com/in/talhazubiya/)

---

## Disclaimer

Clario is a fictional SaaS company created for demonstration and learning purposes. The workflows, knowledge base, and business information in this project are not connected to a real company.
