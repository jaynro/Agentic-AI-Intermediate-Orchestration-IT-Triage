# 🛠️ Intermediate Level: Orchestration - IT Service Desk Triage Agent

## 🛑 Reviewer Instructions: Submission Checklist 🛑

This project is focused on **Orchestration** and **RAG/Vector Search** integration, defining the **Intermediate Level** of the training. Developers **must** ensure the following requirements are met for review:

1.  **Repository Forking & Naming:** This repository **must be forked** to your personal GitHub account and **renamed** exactly to:
    `Agentic-AI-Foundations-Capstone-Project-2-ITServiceDesk-Triage-Agent`
2.  **Language Requirement:** All code must be implemented using **Python**.
3.  **Topic Coverage:** The implementation must cover **Multi-Agent Orchestration**, **Vector Search/RAG**, and **Tool Integration**.
4.  **Complete Documentation:** All sections of this README (Requirements, Execution, Views) must be fully completed with project-specific details, code, and screenshots.

-----

## 🌟 Project Summary

This project involves building an **IT Service Desk Triage Agent** to automatically process raw help desk tickets. The agent manages a multi-step workflow designed to classify, enrich, and route tickets efficiently:

1.  **Classification:** Determines the issue type and severity from unstructured text.
2.  **Enrichment:** Finds relevant knowledge base articles/FAQs using **Vector Search (RAG)**.
3.  **Routing:** Generates a structured output for the human agent, identifying the correct support team and providing suggested fixes.

This is a demonstration of **multi-agent orchestration** and practical **Vector Search/RAG** implementation on complex, unstructured data (IT tickets).

### Key Technologies:

  * **Core Concept:** **Orchestration: Multi-agent flows** (Intermediate Level).
  * **Data Handling:** Vector search/RAG (for knowledge base lookups).
  * **Structured Output:** Generating a fully classified and enriched support ticket object.

-----

## 🧠 Related Training Topics

This project covers the **Orchestration** section of the training.

| Training Topic | Relevance to This Project | Implementation Details |
| :--- | :--- | :--- |
| **Multi-Agent Orchestration** | Core structure of the project. | Uses a central **Triage Orchestrator Agent** that sequentially calls specialized sub-agents (e.g., a **Classification Agent** then an **Enrichment Agent**) to complete the triage workflow.  |
| **Vector Search / RAG** | Essential for ticket enrichment. | A **Knowledge Base** (internal documentation, FAQs) is indexed using **Vector Search**. The Enrichment Agent uses RAG to retrieve the most relevant articles or fixes based on the classified issue. |
| **Tool Integration** | Supporting actions. | The Enrichment Agent uses a specialized **Vector Search Tool** to query the RAG index. *Optionally*, a **User Profile Tool** could be mocked to look up the user's role or hardware model. |
| **Large Language Models (LLMs)** | Classification and Summary. | The Classification Agent uses the LLM's reasoning ability to assign the correct category (e.g., Network, Software, Account) and severity (e.g., P1, P2) to the unstructured ticket text. |
| **Cloud Deployment** | Production readiness. | **[Placeholder: Briefly describe the target cloud platform (e.g., Google Cloud Run) and how deployment demonstrated production skills.]** |

-----

## 📋 Requirements (Functional and Non-Functional)

### Functional Requirements (FR)

| ID | Requirement | Specific Description | Status |
| :--- | :--- | :--- | :--- |
| **FR01** | Orchestration | The workflow must be managed by a **Root Orchestrator Agent** calling at least two specialized agents sequentially (**Classify -\> Enrich -\> Route**). | `PENDING` |
| **FR02** | Classification | The **Classification Agent** must accurately assign the issue category and severity level to the ticket. | `PENDING` |
| **FR03** | Enrichment (RAG) | The **Enrichment Agent** must query the vectorized Knowledge Base (RAG) to find relevant FAQs and add them to the ticket summary. | `PENDING` |
| **FR04** | Routing Logic | The final output must identify the correct Level 2 support team (e.g., Network, DevOps, HR) based on the classification. | `PENDING` |
| **FR05** | Structured Output | The final output must be a structured JSON containing all classifications, relevant FAQs/links, and the designated support team. | `PENDING` |

### Non-Functional Requirements (NFR)

| ID | Requirement | Category | Metric |
| :--- | :--- | :--- | :--- |
| **NFR01** | Scalability | Performance | The deployed service must handle up to **X** concurrent ticket submissions. |
| **NFR02** | Latency | Performance | The end-to-end triage process must complete in less than **Y** seconds. |
| **NFR03** | Accuracy | Reliability | Classification and routing accuracy must be greater than **90%** on the test set. |
| **NFR04** | Security | Deployment | Service must be deployed using a secure cloud endpoint (HTTPS) with proper API key authentication. |

-----

## 🚀 Implementation and Execution

### 1\. Prerequisites and Setup

Requires **Python 3.9+**, Gemini API Key, and a configured **Vector Database/Index** (e.g., a local index or a cloud vector store) loaded with IT support documentation.

  * **API Key:** Your Gemini API key must be configured in your environment.
  * **RAG Config:** **[Placeholder: Specific environment variables needed to connect to the Vector Store (e.g., DB\_ENDPOINT, INDEX\_ID, etc.).]**

### 2\. How to Build (Install & Index)

In addition to installing libraries, you must build the RAG index for the knowledge base.

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Build the Vector Index (One-time setup)
# This script reads FAQ documents and indexes them for RAG lookup.
python setup_knowledge_base.py --data_path "data/support_faqs/"
```

### 3\. How to Run (Local Testing)

Run the FastAPI application locally for initial testing.

```bash
uvicorn main:app --reload
```

The server will be available at `http://localhost:8000`.

### 4\. How to Test (Local Endpoint)

Test the multi-agent workflow using the `/triage` endpoint.

```bash
# Example curl request submitting a raw ticket description
curl -X POST http://localhost:8000/triage \
     -H "Content-Type: application/json" \
     -d '{
         "ticket_text": "I can\'t log into my email this morning; it keeps saying my password is wrong after the system update."
     }'
```

### 5\. Deployment Instructions

**[Placeholder: Instructions for deploying to the target cloud environment (e.g., Cloud Run, App Engine, or equivalent).]**

-----

## 🖼️ Project Views

Here will be the relevant screenshots demonstrating the successful execution of the orchestration.

### 1\. Multi-Agent Orchestration Log

\![Placeholder for screenshot of the detailed agent execution log showing the sequential call from Orchestrator -\> Classification Agent -\> Enrichment Agent.]

### 2\. Successful Triage JSON Output

\![Placeholder for screenshot of the final structured JSON response containing the category, severity, and relevant FAQ links.]

### 3\. Cloud Deployment View

\![Placeholder for screenshot of the deployed service endpoint in the chosen cloud platform (e.g., Google Cloud Run console).]
