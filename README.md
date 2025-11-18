PearlsPartner Hackathon

Project Name: PearlsPartner
Event: MemHack Experiential Learning Lab (ELL), Pace University
📌 Project Overview

PearlsPartner is an AI-powered Supply Account Manager (SAM) assistant designed to help marketplace operations (Amazon-style) streamline communication, track seller interactions, and provide context-aware insights.

Unlike traditional CRMs, PearlsPartner remembers past interactions, escalations, and seller-specific preferences to provide actionable recommendations and reduce repetitive manual tracking.

Goal: Enhance agent workflows with memory-powered AI for continuous learning and better decision-making.

💡 Key Features

Memory-Powered AI: Short-term context and long-term memory via MemMachine

Profile Management: Track seller info, risk tier, preferred communication channels

Episodic Memory: Logs interactions like tickets, emails, and chat notes

Context-Aware Recommendations: Suggests next steps for escalations and account health

Knowledge Integration: Retrieve SOPs, KB articles, and metrics for decision support

LangChain Orchestration: Manages agent workflow, tool calls, and RAG pipelines

🛠 Tech Stack
Layer	Technology / Tool
Frontend	React + Vite
Backend	FastAPI (Python)
Memory Layer	MemMachine (episodic + profile memory)
Databases	Neo4j (episodic), PostgreSQL (profile)
AI / LLM	OpenAI GPT-4 (or alternative LLM provider)
Agent Orchestration	LangChain + LangGraph
Containerization	Docker Compose
Tools	Ticket / CRM fetch, Knowledge search, Metrics fetch

🏗 System Architecture

High-Level Workflow:

[SAM User (Agent)]
       │
       ▼
[LangChain Agent Orchestrator]
       │
       ├─> [MemMachine Memory Layer (episodic + profile)]
       │
       ├─> [LLM for recommendations & summaries]
       │
       └─> [Data Connectors: CRM, KB, Metrics]


LangChain orchestrates conversations, tools, and RAG pipelines.

MemMachine stores both short-term (working) and long-term (episodic/profile) memories.

LLM generates context-aware responses and actionable next steps.

🚀 Setup Instructions
Prerequisites

Python 3.12+

Docker & Docker Compose

OpenAI API Key (or other LLM provider)
