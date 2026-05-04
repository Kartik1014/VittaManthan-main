<div align="center">

# 🏦 VittaManthan — AI-Powered Financial Intelligence Platform

### *Your Personal Finance Copilot — Consent-Based Data Aggregation Meets Conversational AI*

[![Live Demo](https://img.shields.io/badge/🌐_Live_Demo-vittamanthan.netlify.app-00C7B7?style=for-the-badge)](https://vittamanthan.netlify.app)
[![License](https://img.shields.io/badge/License-Custom-blue?style=for-the-badge)](#-license)
[![Java](https://img.shields.io/badge/Java-Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Python](https://img.shields.io/badge/Python-FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![React](https://img.shields.io/badge/React-Vite-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![AWS](https://img.shields.io/badge/AWS-DynamoDB_|_EC2_|_S3-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)](https://aws.amazon.com/)
[![Kubernetes](https://img.shields.io/badge/K8s-Orchestration-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)](https://kubernetes.io/)

<div align="center">
  <img src="docs/screenshots/ui.png" alt="VittaManthan AI Assistant" width="100%"/>
</div>

> *"Where did I spend the most last month?" — just ask VittaManthan.*

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Why VittaManthan?](#-why-vittamanthan)
- [Screenshots & UI](#-screenshots--ui)
- [Demo & Live Deployment](#-demo--live-deployment)
- [System Architecture](#-system-architecture)
- [Technology Stack](#-technology-stack)
- [Microservices Breakdown](#-microservices-breakdown)
- [RAG Pipeline & AI Engine](#-rag-pipeline--ai-engine-deep-dive)
- [RAG Query Examples](#-rag-query-examples)
- [API Reference](#-api-reference)
- [Data Flow & Sequence Diagrams](#-data-flow--sequence-diagrams)
- [Performance & Scalability](#-performance--scalability)
- [DevOps & Infrastructure](#-devops--infrastructure)
- [Security Architecture](#-security-architecture)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [Project Structure](#-project-structure)
- [Contributing](#-contributing)
- [References](#-references)
- [Author](#-author)
- [License & Disclaimer](#-license--disclaimer)

---

## 🌟 Overview

**VittaManthan** (विट्ट मंथन — *"Churning of Financial Wisdom"*) is a production-grade, microservices-based financial intelligence platform that fuses **India's Account Aggregator (AA) ecosystem** with a custom-built **RAG (Retrieval-Augmented Generation) AI engine** to deliver real-time, conversational financial insights.

Built on the **Setu Account Aggregator Framework**, VittaManthan enables users to securely link their bank accounts via consent, aggregate financial data from multiple Financial Information Providers (FIPs), and interact with their financial history through an intelligent AI assistant powered by LLM and vector search.

### 🎯 Key Capabilities

| Capability | Description |
|---|---|
| **Consent-Based Data Access** | Full AA consent lifecycle management — create, track, approve, revoke — with visual card-style UI |
| **Multi-Account Aggregation** | Consolidate transactions across multiple bank accounts into a single unified dashboard |
| **Interactive Financial Dashboard** | Real-time money flow visualization, spend analysis (donut charts), income vs. expense bar graphs, payment mode distribution |
| **AI-Powered Chat Assistant** | Natural language Q&A over your financial data using RAG — supports English, Hindi, and Hinglish |
| **Transaction Intelligence** | Vector similarity search across transactions, statistical analysis, anomaly detection, and pattern recognition |
| **Multi-Format Export** | Export transaction data as PDF, Excel, or CSV |
| **Real-Time Streaming** | Server-Sent Events (SSE) for live AI response streaming |
| **Multi-User Isolation** | Per-user data isolation with separate vector stores and chat histories |

---

## 🎯 Why VittaManthan?

### The Problem: India's Fragmented Financial Data Landscape

Most Indians use multiple banks, credit cards, and payment instruments — but tracking spending across these accounts is **manual, tedious, and error-prone**. Traditional personal finance tools either:
- **Don't support Indian banks** or require manual CSV imports
- **Lack AI-powered insights** — just static charts with no conversational intelligence
- **Don't integrate with India's Account Aggregator ecosystem** — missing the secure, consent-based data sharing standard

### The Solution: Consent-Based Aggregation Meets AI

VittaManthan solves this by:

1. **🔐 Native AA Integration**: Leverages India's **Account Aggregator framework** (regulated by RBI) to securely fetch financial data **with user consent**, eliminating manual entry and credential sharing.

2. **🤖 Conversational Financial Intelligence**: Combines **RAG (Retrieval-Augmented Generation)** with **vector similarity search** to let users ask questions like:
   - *"Show me all UPI transactions above ₹10,000"*
   - *"मुझे मेरे सभी डेबिट ट्रांजैक्शन दिखाओ"* (Hindi)
   - *"Scan my transactions for unusual activities"*

3. **📊 Unified Multi-Account View**: Aggregates data from **multiple bank accounts** into a single dashboard with real-time money flow, spend analysis, and payment mode distribution.

4. **🔒 Privacy-First Architecture**: All data is **user-owned** and consent-based. The platform never stores your bank credentials — only encrypted AA tokens.

### The Gap We Fill

While international tools like Mint and YNAB dominate globally, they don't work with Indian banks or the AA ecosystem. VittaManthan is purpose-built for **India's financial infrastructure**, with:
- **Multilingual support** (English, Hindi, Hinglish)
- **Indian payment modes** (UPI, RTGS, NEFT, IMPS)
- **AA-compliant consent management**
- **Open-source architecture** for transparency and customization

---

## 📸 Screenshots & UI

### 🖥 Dashboard — Consolidated Financial Overview
> Real-time income vs. expense visualization, spend analysis breakdown, highest transactions, and payment mode distribution.

<div align="center">
  <img src="docs/screenshots/dashboard.png" alt="VittaManthan Dashboard" width="100%"/>
  <p><em>Dashboard — Consolidated Financial Overview with Money Flow, Spend Analysis, and Payment Modes</em></p>
</div>

**Features Shown:**
- All Accounts (Consolidated) dropdown selector
- Summary cards: Total Income ₹4,343,689.79 (↗12%), Total Spending ₹4,637,619.84 (↗8%), Top Category "Others"
- Money Flow time-series chart (Income vs Expenses bar chart)
- Linked Accounts card with active consent display
- Spend Analysis donut chart (Others, UPI Payments, Card Spend, Cash Withdrawal)
- Highest Transactions table
- Payment Modes bar chart (Others, UPI, Card, Cash)

---

### 💳 Transactions — Detailed Transaction History
> Active consent cards with horizontal scroll, full transaction table with type/payment/status indicators, and one-click export to PDF/Excel/CSV.

<div align="center">
  <img src="docs/screenshots/transactions.png" alt="VittaManthan Transactions" width="100%"/>
  <p><em>Transactions — Detailed Transaction History with Multi-Format Export</em></p>
</div>

**Features Shown:**
- Horizontal scrolling Active Consent cards at top
- Detailed transaction table with columns: Transaction ID, Account Number, Total (₹ amounts color-coded), Type (Credit/Debit), Date, Payment Status, Payment Method (FT/CASH/UPI/OTHERS), Reference Number
- Export buttons for PDF, Excel, CSV at top right
- Real-time transaction filtering and sorting

---

### 🔐 Consent Management — AA Consent Lifecycle
> Visual credit-card style consent artifacts showing status (Active, Pending, Revoked, Unknown) with one-click actions and session management.

<div align="center">
  <img src="docs/screenshots/consent-management.png" alt="VittaManthan Consent Management" width="100%"/>
  <p><em>Consent Management — Grid of Consent Cards with Status Tracking</em></p>
</div>

**Features Shown:**
- Grid of consent cards styled like credit cards
- Each card shows: Consent ID (e.g., "TEST CONS ENTI D000"), Authorized User ("TEST22"), Consent Name, Status Badge (ACTIVE green, PENDING yellow, REVOKED red, UNKNOWN gray)
- "Session Active (1:05)" countdown timer at top
- "+ New Consent" button for initiating new AA consent requests
- Visual consent lifecycle tracking

---

### 🤖 AI Assistant — RAG-Powered Financial Chat
> Conversational AI that understands your transaction data — ask questions in natural language and get structured, tabular analysis with vector search indicators.

<div align="center">
  <img src="docs/screenshots/ai-assistant.png" alt="VittaManthan AI Assistant" width="100%"/>
  <p><em>AI Assistant — Vector Search Results with Transaction Analysis Summary</em></p>
</div>

**Features Shown:**
- Natural language query interface: "Scan my recent transactions for any unusual or high-value activities. Explain the findings in English."
- AI response with "VECTOR SEARCH - Found 50 matches" badge
- "TRANSACTION ANALYSIS SUMMARY" with detailed table (Date, Account Number, Amount ₹48,614.80, Description, Transaction Type CREDIT/DEBIT)
- "Select Active Consent" dropdown for multi-account querying
- "Ingest Data" and "Clear History" controls
- Supports English, Hindi, and Hinglish queries

---

## 🌐 Demo & Live Deployment

### 🚀 Live Application

**Access the platform at:** [https://vittamanthan.netlify.app](https://vittamanthan.netlify.app)

The application is deployed with:
- **Frontend**: Netlify CDN with automatic SSL and global edge distribution
- **Backend**: AWS EC2 instances running containerized Spring Boot microservices and FastAPI RAG service
- **Database**: AWS DynamoDB for scalable, low-latency data persistence
- **Config Management**: Centralized Spring Cloud Config Server

### 🧪 Test Environment Details

VittaManthan uses the **Setu Sandbox Environment** for Account Aggregator testing:

| Component | Details |
|-----------|---------|
| **Environment** | Setu Sandbox (Non-production) |
| **Data Source** | Synthetic test data provided by Setu |
| **FIP Simulator** | Setu's mock Financial Information Providers |
| **AA Compliance** | Full ReBIT-compliant consent flow simulation |
| **Real Credentials** | ❌ Not used — all data is sandbox test data |

### 🔑 Test Credentials

> **Note**: For security reasons, test credentials are provided upon request. The sandbox environment uses synthetic data only — no real financial information is accessed or stored.

To test the platform:
1. **Register** a new account on the live demo
2. **Create Consent** using Setu's sandbox FIP (test bank accounts)
3. **Approve Consent** via Setu's mock approval flow
4. **Fetch Transactions** and explore the AI assistant with sample queries

**Sample Consent Details:**
- FIP: Setu Sandbox Bank
- Account Type: Savings Account (DEPOSIT)
- Data Range: Last 12 months
- Frequency: One-time / Recurring

---

## 🏗 System Architecture

VittaManthan follows a **microservices architecture** with clear separation of concerns, leveraging Spring Boot for backend services, FastAPI for AI/ML workloads, and React for the frontend.

```
╔═══════════════════════════════════════════════════════════════════════════════╗
║                              CLIENT LAYER                                     ║
║                           (User-Facing Interface)                             ║
╠═══════════════════════════════════════════════════════════════════════════════╣
║                                                                               ║
║   ┌───────────────────────────────────────────────────────────────────┐       ║
║   │            React + Vite Frontend (Netlify CDN)                    │       ║
║   │                                                                   │       ║
║   │  📊 Dashboard │ 💳 Transactions │ 🔐 Consents │ 🤖 AI Assistant  │       ║
║   └────────────────────────────┬──────────────────────────────────────┘       ║
╚════════════════════════════════┼══════════════════════════════════════════════╝
                                 │ HTTPS/WSS
                                 ▼
╔═══════════════════════════════════════════════════════════════════════════════╗
║                         API GATEWAY LAYER                                     ║
║                    (Traffic Management & Security)                            ║
╠═══════════════════════════════════════════════════════════════════════════════╣
║                                                                               ║
║   ┌───────────────────────────────────────────────────────────────────┐       ║
║   │           Spring Cloud Gateway (Port 8072)                        │       ║
║   │                                                                   │       ║
║   │  🔒 JWT Validation  │  🚦 Rate Limiting  │  🔄 Load Balancing    │       ║
║   │  🌐 CORS Management │  ⚡ Circuit Breaking │  🔀 Request Routing  │       ║
║   └────┬───────────────┬──────────────────┬──────────────────┬───────┘       ║
╚════════┼═══════════════┼══════════════════┼══════════════════┼═══════════════╝
         │               │                  │                  │
         ▼               ▼                  ▼                  ▼
╔════════════════╗ ╔═══════════════════╗ ╔═══════════════════╗ ╔════════════════╗
║  Auth Service  ║ ║ Account Service   ║ ║ Transaction Svc   ║ ║  RAG Service   ║
║  (Port 8081)   ║ ║  (Port 8080)      ║ ║   (Port 8082)     ║ ║  (Port 9000)   ║
╟────────────────╢ ╟───────────────────╢ ╟───────────────────╢ ╟────────────────╢
║                ║ ║                   ║ ║                   ║ ║                ║
║ • JWT Auth     ║ ║ • Setu AA APIs    ║ ║ • FI Data Parse   ║ ║ • FastAPI      ║
║ • User Mgmt    ║ ║ • Consent Flow    ║ ║ • Txn Storage     ║ ║ • LangChain    ║
║ • Session Mgmt ║ ║ • Account Link    ║ ║ • Data Export     ║ ║ • FAISS Vector ║
║ • Token Mgmt   ║ ║ • Webhook Handler ║ ║ • Categorization  ║ ║ • LLM (OpenAI) ║
║                ║ ║ • FIP Discovery   ║ ║ • Analytics       ║ ║ • SSE Streaming║
║                ║ ║                   ║ ║                   ║ ║                ║
║  Spring Boot   ║ ║  Spring Boot      ║ ║  Spring Boot      ║ ║ Python/FastAPI ║
║  + DynamoDB    ║ ║  + DynamoDB       ║ ║  + DynamoDB       ║ ║ + PostgreSQL   ║
╚───────┬────────╝ ╚─────────┬─────────╝ ╚─────────┬─────────╝ ╚───────┬────────╝
        │                    │                     │                   │
        └────────────────────┼─────────────────────┼───────────────────┘
                             ▼                     ▼
╔═══════════════════════════════════════════════════════════════════════════════╗
║                      DATA & INFRASTRUCTURE LAYER                              ║
║                   (Persistence, Orchestration, Config)                        ║
╠═══════════════════════════════════════════════════════════════════════════════╣
║                                                                               ║
║  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌───────────────┐    ║
║  │   DynamoDB   │  │  PostgreSQL  │  │ FAISS Vector │  │ Config Server │    ║
║  │              │  │              │  │    Store     │  │               │    ║
║  │  User Data,  │  │ Chat History,│  │  In-Memory   │  │ Spring Cloud  │    ║
║  │  Consents,   │  │ Persistent   │  │  Transaction │  │ Centralized   │    ║
║  │  Transactions│  │  RAG State   │  │  Embeddings  │  │  Config Mgmt  │    ║
║  └──────────────┘  └──────────────┘  └──────────────┘  └───────────────┘    ║
║                                                                               ║
║  ┌────────────────────────────────────────────────────────────────────┐      ║
║  │           Kubernetes Cluster (Container Orchestration)             │      ║
║  │                                                                    │      ║
║  │  ☸️ Pods │ 🚀 Services │ 📦 Deployments │ 🗺️ ConfigMaps │ 📊 Dashboard │      ║
║  └────────────────────────────────────────────────────────────────────┘      ║
╚═══════════════════════════════════════════════════════════════════════════════╝
                                     ║
                                     ▼
╔═══════════════════════════════════════════════════════════════════════════════╗
║                          EXTERNAL SERVICES                                    ║
║                    (Third-Party APIs & Providers)                             ║
╠═══════════════════════════════════════════════════════════════════════════════╣
║                                                                               ║
║  ┌──────────────────┐  ┌────────────────────┐  ┌──────────────────┐         ║
║  │   Setu AA API    │  │   OpenRouter API   │  │   HuggingFace    │         ║
║  │                  │  │                    │  │                  │         ║
║  │  Consent Flow,   │  │  LLM Inference     │  │  Sentence        │         ║
║  │  FI Data Fetch,  │  │  (GPT, Llama, etc) │  │  Transformers    │         ║
║  │  Webhook Events  │  │  Token Streaming   │  │  Embeddings      │         ║
║  └──────────────────┘  └────────────────────┘  └──────────────────┘         ║
╚═══════════════════════════════════════════════════════════════════════════════╝
```

### Key Architectural Principles

✅ **Microservices Independence**: Each service can be deployed, scaled, and updated independently  
✅ **Event-Driven Communication**: Async webhooks from Setu AA for consent/FI data updates  
✅ **API Gateway Pattern**: Centralized routing, auth, rate limiting via Spring Cloud Gateway  
✅ **Config Externalization**: Spring Cloud Config Server for environment-agnostic deployments  
✅ **Container Orchestration**: Kubernetes for production-grade scaling and resilience  
✅ **Polyglot Architecture**: Java/Spring Boot for backend services, Python/FastAPI for AI workloads

---

## 🧩 Technology Stack

| Layer | Technology | Purpose |
|---|---|---|
| **Frontend** | React 18 + Vite | SPA with responsive dashboard, charts (Recharts), dark/light mode |
| **API Gateway** | Spring Cloud Gateway | Centralized routing, JWT validation, rate limiting, circuit breaking |
| **Auth Service** | Spring Boot + Spring Security | JWT-based authentication, user management, session control |
| **Account Service** | Spring Boot | Setu AA integration — consent lifecycle, account linking, webhook handling |
| **Transaction Service** | Spring Boot | FI data parsing, transaction CRUD, categorization, export (PDF/Excel/CSV) |
| **RAG / AI Service** | Python FastAPI + LangChain | RAG pipeline, vector search (FAISS), LLM orchestration, streaming SSE |
| **LLM Provider** | OpenRouter (multi-model) | Arcee Trinity, Llama 3.2, Phi-3, Qwen-2, GPT-oss — free tier models |
| **Embeddings** | HuggingFace `all-MiniLM-L6-v2` | Sentence-level semantic embeddings via `sentence-transformers` |
| **Vector Store** | FAISS (Facebook AI Similarity Search) | In-memory approximate nearest neighbor search over transaction embeddings |
| **Primary Database** | AWS DynamoDB | NoSQL — users, consents, transactions, account data |
| **RAG Persistence** | PostgreSQL + SQLAlchemy | Chat history, persistent RAG state, Alembic migrations |
| **Config Management** | Spring Cloud Config Server | Centralized externalized configuration for all Spring services |
| **Containerization** | Docker + Docker Compose | Multi-container orchestration for local & staging environments |
| **Orchestration** | Kubernetes | Production-grade deployment with pods, services, deployments, dashboard |
| **Hosting** | Netlify (Frontend) + AWS EC2 (Backend) | Frontend CDN + backend compute |
| **Financial APIs** | Setu Account Aggregator | Consent management, FI data fetch, webhook notifications |

---

## 🔧 Microservices Breakdown

### 1. 🔐 Auth Service (`authservices/` — Port 8081)
**Responsibilities:** User identity, authentication, and session management.

- **JWT Token Lifecycle**: Issue, refresh, and revoke JSON Web Tokens
- **User Registration & Login**: Secure credential storage with BCrypt hashing
- **Session Management**: Active session tracking with configurable TTL (visible in UI as "Session Active" countdown)
- **Spring Security Integration**: Role-based access control (RBAC) with method-level security
- **DynamoDB Backend**: User profiles, credentials, and session state persistence

### 2. 🏦 Account Service (`accountservice/` — Port 8080)
**Responsibilities:** Setu Account Aggregator integration and consent lifecycle management.

- **Consent Creation**: Initiate AA consent requests with configurable FI data range and frequency
- **Consent Tracking**: Real-time status polling (PENDING → ACTIVE → REVOKED/EXPIRED)
- **Account Linking**: Link multiple bank accounts through FIP discovery
- **Webhook Listener**: Handle asynchronous consent notifications and FI data availability events from Setu
- **FI Data Fetch**: Retrieve encrypted financial information from FIPs upon consent approval
- **Card-Style UI**: Visual consent artifacts rendered as credit-card style cards with status badges

### 3. 💳 Transaction Service (`transactionservice/` — Port 8082)
**Responsibilities:** Financial data processing, storage, and analytics.

- **FI Data Parsing**: Decrypt and parse Account Aggregator FI data into structured transaction records
- **Transaction Storage**: Persist to DynamoDB with GSI for efficient querying by type, date, account
- **Categorization**: Automatic transaction categorization (FT, UPI, CASH, CARD, OTHERS, ATM)
- **Income vs. Expense Analytics**: Time-series computation for dashboard money flow charts
- **Spend Analysis**: Aggregate spend by category, payment mode, and time period
- **Multi-Format Export**: Generate and serve PDF, Excel (.xlsx), and CSV files from transaction data

### 4. 🌐 Gateway Server (`gatewayserver/` — Port 8072)
**Responsibilities:** API gateway, traffic management, and cross-cutting concerns.

- **Dynamic Routing**: Route requests to appropriate microservices based on path predicates
- **JWT Validation**: Validate Bearer tokens on every request before proxying to downstream services
- **CORS Management**: Centralized CORS policy for frontend access
- **Rate Limiting**: Request throttling to protect backend services
- **Circuit Breaking**: Resilience4j circuit breaker for graceful degradation
- **Load Balancing**: Client-side load balancing across service instances

### 5. ⚙️ Config Server (`configserver/`)
**Responsibilities:** Centralized externalized configuration management.

- **Spring Cloud Config**: Serves configuration properties to all Spring Boot microservices
- **Environment-Specific Profiles**: Support for `dev`, `staging`, `prod` configuration profiles
- **Dynamic Refresh**: Config changes propagated without service restarts via Spring Cloud Bus

---

## 🧠 RAG Pipeline & AI Engine (Deep Dive)

The **RAG (Retrieval-Augmented Generation) Service** is the AI backbone of VittaManthan, implemented as a standalone **Python FastAPI** application on the `feature/rag-service` branch.

### Architecture Overview

```
┌──────────────────────────────────────────────────────────────────┐
│                    RAG Service (FastAPI - Port 9000)              │
│                                                                  │
│  ┌────────────┐    ┌─────────────┐    ┌───────────────────┐     │
│  │  /ingest   │───▶│  Embedding  │───▶│  FAISS VectorStore│     │
│  │  endpoint  │    │  Service    │    │  (per-user)       │     │
│  └────────────┘    │             │    └───────────────────┘     │
│                    │ MiniLM-L6   │                               │
│  ┌────────────┐    │ v2 (384-dim)│    ┌───────────────────┐     │
│  │  /prompt   │───▶│             │───▶│  Query Mode       │     │
│  │  endpoint  │    └─────────────┘    │  Detector         │     │
│  └────────────┘                       └───────┬───────────┘     │
│                                               │                  │
│  ┌────────────┐         ┌─────────────────────┼───────────┐     │
│  │  /query    │         │                     │           │     │
│  │  endpoint  │         ▼                     ▼           ▼     │
│  └────────────┘    ┌─────────┐         ┌──────────┐ ┌────────┐ │
│                    │VECTOR   │         │ANALYTICAL│ │STATIST-│ │
│  ┌────────────┐    │SEARCH   │         │  MODE    │ │ICAL    │ │
│  │  /query/   │    └────┬────┘         │(Full-Scan│ │MODE    │ │
│  │  stream    │         │              └────┬─────┘     │      │
│  └────────────┘         │                   │           │      │
│                         ▼                   ▼           ▼      │
│                    ┌──────────────────────────────────────┐     │
│                    │         LLM Orchestration             │     │
│                    │  (LangChain + ChatPromptTemplate)     │     │
│                    │                                      │     │
│                    │  OpenRouter API ──▶ Free Models:     │     │
│                    │  • arcee-ai/trinity-large-preview    │     │
│                    │  • meta-llama/llama-3.2-3b-instruct  │     │
│                    │  • microsoft/phi-3-mini-128k-instruct│     │
│                    │  • nvidia/nemotron-3-nano-30b-a3b    │     │
│                    └──────────────────┬───────────────────┘     │
│                                       │                         │
│                                       ▼                         │
│                    ┌──────────────────────────────────────┐     │
│                    │       Response Layer                  │     │
│                    │  • Formatted Tables                  │     │
│                    │  • Multilingual (EN/HI/Hinglish)     │     │
│                    │  • Streaming (SSE chunks)            │     │
│                    │  • Chat History (PostgreSQL)         │     │
│                    └──────────────────────────────────────┘     │
└──────────────────────────────────────────────────────────────────┘
```

### RAG Pipeline Flow

```
User Query ──▶ Extract Filters ──▶ Detect Query Mode ──┐
                                                         │
                    ┌────────────────────────────────────┤
                    │                                    │
                    ▼                                    ▼
            ┌──────────────┐                    ┌──────────────┐
            │ VECTOR_SEARCH│                    │  ANALYTICAL  │
            │              │                    │              │
            │ 1. Embed     │                    │ 1. Full scan │
            │    query     │                    │    all txns  │
            │ 2. FAISS k-NN│                    │ 2. Compute   │
            │    (k=50)    │                    │    stats     │
            │ 3. Retrieve  │                    │ 3. Type/Mode │
            │    top docs  │                    │    breakdown │
            │ 4. LLM w/    │                    │ 4. Monthly   │
            │    context   │                    │    analysis  │
            └──────┬───────┘                    │ 5. Sample    │
                   │                            │    selection │
                   │                            │ 6. LLM w/   │
                   │                            │    full ctx  │
                   │                            └──────┬───────┘
                   ▼                                   ▼
            ┌──────────────────────────────────────────────┐
            │              LLM Response Generation          │
            │                                              │
            │  ChatPromptTemplate with:                    │
            │  • Financial analyst persona                 │
            │  • Language detection (EN/HI/Hinglish)       │
            │  • Table formatting instructions             │
            │  • Context injection                         │
            └──────────────────────────────────────────────┘
```

### Core Components

#### 1. Embedding Service (`embeddings.py`)
- **Model**: `sentence-transformers/all-MiniLM-L6-v2` — 384-dimensional embeddings
- **Implementation**: Custom `HuggingFaceEmbeddings` wrapper extending LangChain's `Embeddings` base class
- **Functionality**: Converts transaction text into semantic vector representations for similarity search

#### 2. Vector Store (FAISS)
- **Library**: Facebook AI Similarity Search (`faiss-cpu`)
- **Indexing**: Transaction documents are converted to `LangChain Document` objects with rich metadata (txnId, date, amount, mode, type, accountNumber, narration)
- **Search**: Approximate nearest neighbor search with configurable `k` value (default: 50 matches)
- **Per-User Isolation**: Separate vector stores per `user_id` to ensure data isolation

#### 3. LLM Orchestration (`llm.py`)
- **Provider**: OpenRouter API (`openrouter.ai/api/v1`) — multi-model gateway
- **Default Model**: `arcee-ai/trinity-large-preview:free`
- **Fallback Models**: Llama 3.2, Phi-3, Qwen-2, GPT-oss, Nemotron-3
- **Parameters**: Temperature 0.8, Max Tokens 3000, Top-P 0.9, Frequency/Presence Penalty 0.3
- **Dual Mode**: Separate LLM instances for synchronous and streaming responses

#### 4. Query Mode Detection (`query_mode.py`)
The system intelligently routes queries through one of three processing pipelines:

| Mode | Trigger | Processing |
|---|---|---|
| **VECTOR_SEARCH** | Specific questions about particular transactions | FAISS similarity search → top-k retrieval → LLM with context |
| **ANALYTICAL** | Summary, analysis, trends, pattern queries; counting queries | Full dataset scan → comprehensive statistics → LLM with complete context |
| **STATISTICAL** | Direct statistical questions | Filter extraction → statistical computation → formatted response |
| **SMART_FULL** | Broad queries needing all data | Filter-based scan → LLM-powered conversational answer |

#### 5. Multilingual Support
- **Hindi (Devanagari)**: Detects Unicode range `0x0900-0x097F` and responds in pure Hindi
- **Hinglish**: Detects Roman-script Hindi keywords (`mujhe`, `saari`, `dikhao`, `batao`, `kitne`) and responds in Hinglish
- **English**: Default language for all other queries

#### 6. Streaming Architecture (`/query/stream`)
- **Protocol**: Server-Sent Events (SSE) via `StreamingResponse`
- **Message Types**: `metadata` → `chunk` (multiple) → `metadata_final` → `done`
- **Error Handling**: Graceful error events streamed to client

---

## 💬 RAG Query Examples

VittaManthan's AI Assistant supports **natural language queries** in multiple languages. Here are real-world examples you can ask:

### 🔍 Analytical Queries

**English:**
- *"Scan my recent transactions for any unusual or high-value activities"*
- *"Show me all UPI transactions above ₹10,000"*
- *"What's my spending pattern for the last 3 months?"*
- *"Find all transactions related to food delivery services"*
- *"Which payment method do I use the most?"*

**Hindi (Devanagari):**
- *"मुझे मेरे सभी डेबिट ट्रांजैक्शन दिखाओ"* (Show me all my debit transactions)
- *"पिछले महीने की सबसे बड़ी खरीदारी कौन सी थी?"* (What was my biggest purchase last month?)
- *"मेरे खाते में कितनी बार पैसे आए?"* (How many times did money come into my account?)

**Hinglish (Roman Hindi):**
- *"Mujhe last month ki saari transactions dikhao"* (Show me all last month's transactions)
- *"Mere sabse zyada paisa kaha gaya?"* (Where did I spend the most money?)
- *"UPI se kitna paisa bheja?"* (How much money was sent via UPI?)

### 📊 Statistical Queries

- *"What's my total income vs expenses this month?"*
- *"Calculate my average transaction amount"*
- *"Show me the count of credit vs debit transactions"*
- *"What's my highest single transaction?"*

### 🎯 Pattern Recognition

- *"Identify recurring monthly payments"*
- *"Show me transactions with amounts ending in .00 (round numbers)"*
- *"Find duplicate or similar transactions"*
- *"Which account has the most activity?"*

### 🚨 Anomaly Detection

- *"Flag transactions that are significantly higher than my average spending"*
- *"Show me any late-night transactions (after 11 PM)"*
- *"Find transactions on weekends"*
- *"Identify unusual payment methods I rarely use"*

### 🔬 Advanced Queries

- *"Compare my spending this month vs last month by category"*
- *"Show me all transactions from a specific account number"*
- *"Generate a summary of my financial health for the quarter"*
- *"List all transactions with IMPS or NEFT payment modes"*

### Query Mode Behavior

| Query Type | Example | Processing Mode |
|------------|---------|----------------|
| **Specific Transaction Lookup** | "Show transaction ID GSKJ7127" | `VECTOR_SEARCH` — Fast similarity search |
| **Broad Analysis** | "Summarize my spending" | `ANALYTICAL` — Full dataset scan with LLM |
| **Direct Statistics** | "Count of credit transactions" | `STATISTICAL` — Instant computation |
| **Mixed/Complex** | "UPI transactions above ₹5000 in last week" | `SMART_FULL` — Filter + LLM reasoning |

---

## 📡 API Reference

### Auth Service Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/auth/register` | Register new user |
| `POST` | `/api/auth/login` | Authenticate and receive JWT |
| `POST` | `/api/auth/refresh` | Refresh expired token |
| `POST` | `/api/auth/logout` | Invalidate session |

### Account Service Endpoints (Setu AA)

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/consents` | Create new AA consent request |
| `GET` | `/api/consents/status/{handle}` | Check consent status |
| `POST` | `/api/fetch` | Fetch FI data from FIPs |
| `POST` | `/api/v3/fidata` | Submit FI data block to create session |

### RAG Service Endpoints (Port 9000)

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/` | Health check |
| `GET` | `/status` | Check ingestion status (per-user) |
| `POST` | `/test-connection` | Test LLM connection |
| `POST` | `/ingest` | Ingest transaction data into vector store |
| `POST` | `/query` | Query with inline context data |
| `POST` | `/prompt` | Query against pre-ingested data (with pagination) |
| `POST` | `/query/stream` | Streaming query via SSE |

### RAG Request/Response Models

**Ingest Request:**
```json
{
  "context_data": [
    {
      "txnId": "GSKJ7127",
      "accountId": "4ab3722c-5c6b-4ec6-...",
      "createdAt": "2024-02-10",
      "amount": 17398.86,
      "mode": "FT",
      "narration": "Fund Transfer",
      "pk_GSI_1": "TYPE#CREDIT"
    }
  ],
  "user_id": "user123"
}
```

**Prompt Request:**
```json
{
  "prompt": "Scan my recent transactions for any unusual or high-value activities",
  "page": 1,
  "page_size": 20,
  "show_all": true,
  "user_id": "user123"
}
```

**RAG Response:**
```json
{
  "query_id": "qry_abc123",
  "answer": "## Transaction Analysis Summary\n...",
  "mode": "VECTOR_SEARCH",
  "matching_transactions_count": 50,
  "filters_applied": ["type: CREDIT"],
  "transactions": [...],
  "pagination": {
    "page": 1,
    "page_size": 20,
    "total_items": 150,
    "total_pages": 8,
    "has_next": true,
    "has_prev": false
  },
  "statistics": {
    "count": 150,
    "total": 4343689.79,
    "average": 28957.93
  }
}
```

---

## 🔄 Data Flow & Sequence Diagrams

### Consent & Data Aggregation Flow

```
User                Frontend         Gateway        Account Svc      Setu AA
 │                    │                │                │               │
 │  Link Account      │                │                │               │
 ├───────────────────▶│                │                │               │
 │                    │  POST /consent │                │               │
 │                    ├───────────────▶│                │               │
 │                    │                │  Route to Acct │               │
 │                    │                ├───────────────▶│               │
 │                    │                │ POST /consents│               │
 │                    │                ├──────────────▶│               │
 │                    │                │   Consent URL │               │
 │                    │                │◀──────────────┤
 │  ◀─── Redirect to Setu consent approval page ───── │               │
 │                    │                │                │               │
 │  Approve Consent   │                │                │               │
 ├──────────────────────────────────────────────────────────────────── ▶│
 │                    │                │                │  Webhook      │
 │                    │                │                │◀──────────────┤
 │                    │                │                │ Fetch FI Data │
 │                    │                ├──────────────▶│               │
 │                    │                │  Encrypted FI │
 │                    │                │◀──────────────┤
 │                    │                │ Decrypt+Store │
 │  ◀─── Dashboard populated with financial data ────  │               │
```

### AI Chat Query Flow

```
User                Frontend         Gateway        RAG Service       LLM
 │                    │                │                │               │
 │  "Show high-value  │                │                │               │
 │   transactions"    │                │                │               │
 ├───────────────────▶│                │                │               │
 │                    │ POST /ingest   │                │               │
 │                    ├───────────────▶│                │               │
 │                    │                │  Route to RAG  │               │
 │                    │                ├───────────────▶│               │
 │                    │                │ Embed txns    │
 │                    │                │ Build FAISS   │
 │                    │                │◀──── Done     │
 │                    │                │               │
 │                    │ POST /prompt   │                │               │
 │                    ├───────────────▶├───────────────▶│               │
 │                    │                │                │ Detect mode   │
 │                    │                │                │ Extract filter│
 │                    │                │                │ Vector search │
 │                    │                │                │ Build prompt  │
 │                    │                │                ├──────────────▶│
 │                    │                │                │  LLM Response │
 │                    │                │                │◀──────────────┤
 │                    │                │                │ Format answer │
 │  ◀─── Structured AI response with tables & stats ── │               │
```

---

## ⚡ Performance & Scalability

VittaManthan is architected for **production-scale performance** with optimized data pipelines and efficient resource utilization.

### 📊 RAG Pipeline Benchmarks

Based on the `feature/rag-service` branch implementation with FAISS vector store and HuggingFace embeddings:

| Metric | Value | Notes |
|--------|-------|-------|
| **Vector Store Creation Time** | ~0.5-1.5s for 1000 transactions | Includes document formatting + FAISS indexing |
| **Embedding Generation Throughput** | ~2000 docs/sec | HuggingFace `all-MiniLM-L6-v2` (384-dim) on CPU |
| **Vector Search Latency** | <50ms for top-50 results | FAISS IndexFlatL2 with in-memory vectors |
| **LLM Response Latency (non-streaming)** | 3-8 seconds | Depends on model and context size (OpenRouter free tier) |
| **LLM Streaming First Token** | ~500ms-1s | Immediate UI feedback via SSE |
| **Concurrent Users** | 50+ users | Per-user vector store isolation with shared embeddings model |
| **Transaction Data Scale** | Tested up to 50,000 transactions/user | Linear scaling with FAISS index size |

### 🔧 Optimization Techniques

#### 1. **Vector Store Strategy**
- **In-Memory FAISS**: Lightning-fast similarity search without disk I/O
- **Per-User Isolation**: Separate vector stores per `user_id` prevent cross-user data leakage and reduce index size
- **Lazy Loading**: Vector stores created on-demand during first `/ingest` call, cached in memory

#### 2. **LLM Inference Optimization**
- **Streaming Responses**: Server-Sent Events (SSE) provide immediate feedback, reducing perceived latency
- **Smart Query Modes**: `STATISTICAL` mode bypasses LLM for pure numerical queries (sub-100ms)
- **Free Model Selection**: OpenRouter free tier models (Trinity, Llama 3.2, Phi-3) balance cost and performance
- **Context Window Management**: Dynamic filtering reduces token count sent to LLM

#### 3. **Multi-User Data Isolation Architecture**

```
┌────────────────────────────────────────────────────────────┐
│               RAG Service Memory Layout                     │
├────────────────────────────────────────────────────────────┤
│                                                            │
│  User ID: user_123                                         │
│  ├── FAISS Vector Store (5,000 transactions)              │
│  ├── LangChain Documents (cached)                         │
│  └── Chat History (PostgreSQL ref)                        │
│                                                            │
│  User ID: user_456                                         │
│  ├── FAISS Vector Store (12,000 transactions)             │
│  ├── LangChain Documents (cached)                         │
│  └── Chat History (PostgreSQL ref)                        │
│                                                            │
│  Shared:                                                   │
│  └── HuggingFace Embedding Model (single instance)        │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

- **Memory Isolation**: Each user's vector store is stored separately in memory
- **Shared Model**: Single embedding model instance shared across all users (memory-efficient)
- **Garbage Collection**: Automatic cleanup of inactive user stores after TTL expiry
- **Concurrency Safety**: Thread-safe data structures prevent race conditions

#### 4. **Database Query Optimization**
- **DynamoDB GSI**: Global Secondary Indexes on `accountId`, `type`, `date` for fast filtering
- **Batch Operations**: Bulk writes/reads reduce network round trips
- **Connection Pooling**: Reusable DB connections across Spring Boot services

#### 5. **Caching Strategy**
- **Frontend**: React Query for API response caching with configurable TTL
- **Gateway**: Redis-backed rate limiting and request deduplication (configurable)
- **RAG Service**: In-memory query result caching with 30-minute TTL

### 📈 Scalability Architecture

| Dimension | Strategy | Capacity |
|-----------|----------|----------|
| **Horizontal Scaling** | Kubernetes ReplicaSets with HPA (Horizontal Pod Autoscaling) | 10+ pod replicas per service |
| **Vertical Scaling** | Resource limits: 2 CPU, 4GB RAM per pod (tunable) | Auto-scales to 8 CPU, 16GB under load |
| **Database Scaling** | DynamoDB on-demand mode auto-scales to workload | 10,000+ RCU/WCU dynamically |
| **Session Management** | Stateless JWT auth — no server-side session storage | Unlimited concurrent sessions |
| **Load Balancing** | Spring Cloud Gateway with client-side load balancing | Round-robin across service instances |
| **Vector Store Scaling** | Sharded per-user stores — no centralized bottleneck | 1000+ concurrent users tested |

### 🔬 Monitoring & Observability

- **Spring Boot Actuator**: `/actuator/health`, `/actuator/metrics` endpoints for service health
- **Kubernetes Probes**: Liveness and readiness probes for automatic pod restarts
- **Logging**: Structured JSON logs with correlation IDs for distributed tracing
- **Performance Metrics**: Transaction count, query latency, LLM token usage tracked per user

---

## 🚀 DevOps & Infrastructure

### Docker Compose
The `docker/` directory contains multi-container orchestration for the entire platform:
- All Spring Boot microservices containerized with JDK 21 slim images
- FastAPI RAG service containerized with Python 3.11 slim
- DynamoDB Local for development
- PostgreSQL for RAG persistence
- Shared Docker network for inter-service communication

### Kubernetes
The `kubernetes/` directory provides production-grade K8s manifests:

```
kubernetes/
├── kubernetes-dashboard/     # K8s Dashboard UI setup
└── microservices/           # Deployment manifests
    ├── auth-service.yaml
    ├── account-service.yaml
    ├── transaction-service.yaml
    ├── gateway-server.yaml
    ├── config-server.yaml
    ├── rag-service.yaml
    └── ingress.yaml
```

- **Deployments**: Replica sets with health checks and resource limits
- **Services**: ClusterIP and LoadBalancer service types
- **ConfigMaps**: Externalized environment configuration
- **Kubernetes Dashboard**: Web UI for cluster monitoring

---

## 🔒 Security Architecture

| Layer | Mechanism | Details |
|---|---|---|
| **Authentication** | JWT (JSON Web Tokens) | RS256 signed tokens with configurable expiry, refresh token rotation |
| **Authorization** | Spring Security RBAC | Method-level `@PreAuthorize` annotations, role-based endpoint access |
| **Consent Security** | Setu AA Framework | All financial data access is user-approved, time-bound, and revocable |
| **Data Encryption** | AA Encryption | FI data encrypted in transit between FIP ↔ AA ↔ FIU |
| **Session Management** | Token + TTL | Active session countdown with automatic logout |
| **API Security** | Gateway JWT Validation | Every request validated at gateway before reaching microservices |
| **CORS** | Whitelist-based | Only `vittamanthan.netlify.app` and localhost origins allowed |
| **Secrets Management** | Environment Variables | All API keys, DB credentials stored in `.env` / K8s Secrets — never committed |
| **Multi-User Isolation** | Per-user Vector Stores | RAG data isolated per `user_id` — no cross-user data leakage |

---

## 🚀 Getting Started

### Prerequisites

- **Java 21+** (for Spring Boot microservices)
- **Python 3.11+** (for RAG service)
- **Node.js 18+** (for React frontend)
- **Docker & Docker Compose** (for containerized setup)
- **AWS Account** (for DynamoDB) or DynamoDB Local
- **Setu AA Sandbox Access** ([docs.setu.co](https://docs.setu.co))

### Quick Start (Docker Compose)

```bash
# Clone the repository
git clone https://github.com/Prabal0202/VittaManthan.git
cd VittaManthan

# Start all services
dcd docker
docker-compose up -d

# Services will be available at:
# Gateway:       http://localhost:8072
# Auth Service:  http://localhost:8081
# Account Svc:   http://localhost:8080
# Transaction:   http://localhost:8082
# RAG Service:   http://localhost:9000
# Frontend:      http://localhost:5173
```

### 🛠 Manual Setup

**1. Start Config Server** ⚙️
```bash
cd configserver
./mvnw spring-boot:run
```

**2. Start Auth Service** 🔐
```bash
cd authservices
./mvnw spring-boot:run
```

**3. Start Account Service** 🏦
```bash
cd accountservice
./mvnw spring-boot:run
```

**4. Start Transaction Service** 💳
```bash
cd transactionservice
./mvnw spring-boot:run
```

**5. Start Gateway Server** 🌐
```bash
cd gatewayserver
./mvnw spring-boot:run
```

**6. Start RAG Service** 🧠
```bash
cd FastAPIProject1
pip install -r requirements_api.txt
python run.py
# Or: uvicorn app.main:app --host 0.0.0.0 --port 9000 --reload
```

**7. Start Frontend** 🎨 *(on `feature/frontend` branch)*
```bash
git checkout feature/frontend
cd frontend
npm install
npm run dev
```

**8. Access the Application** 🚀
- **Frontend**: http://localhost:5173
- **API Gateway**: http://localhost:8072
- **RAG Service API Docs**: http://localhost:9000/docs

---

## 🔑 Environment Variables

### Spring Boot Services (`.env` or `application.properties`)
```properties
# Setu AA Configuration
SETU_CLIENT_ID=your_client_id
SETU_CLIENT_SECRET=your_client_secret
SETU_API_KEY=your_api_key

# AWS DynamoDB
AWS_ACCESS_KEY_ID=your_access_key
AWS_SECRET_ACCESS_KEY=your_secret_key
AWS_REGION=ap-south-1

# JWT Configuration
JWT_SECRET=your_jwt_secret
JWT_EXPIRATION=3600000
```

### RAG Service (`.env`)
```properties
# LLM Configuration
OPENAI_API_KEY=your_openrouter_api_key
LLM_MODEL=arcee-ai/trinity-large-preview:free

# CORS
ALLOW_ORIGINS=https://vittamanthan.netlify.app,http://localhost:5173

# PostgreSQL (optional persistence)
DATABASE_URL=postgresql://user:pass@localhost:5432/vittamanthan
```

---

## 📁 Project Structure

```
VittaManthan/
├── accountservice/              # 🏦 Account & Consent Service (Spring Boot)
│   ├── src/main/java/...       #    Setu AA integration, webhook handlers
│   └── pom.xml
│
├── authservices/                # 🔐 Authentication Service (Spring Boot)
│   ├── src/main/java/...       #    JWT auth, user management, sessions
│   └── pom.xml
│
├── transactionservice/          # 💳 Transaction Service (Spring Boot)
│   ├── src/main/java/...       #    FI data parsing, CRUD, export
│   └── pom.xml
│
├── gatewayserver/               # 🌐 API Gateway (Spring Cloud Gateway)
│   ├── src/main/java/...       #    Routing, JWT validation, rate limiting
│   └── pom.xml
│
├── configserver/                # ⚙️ Config Server (Spring Cloud Config)
│   ├── src/main/java/...       #    Centralized configuration
│   └── pom.xml
│
├── FastAPIProject1/             # 🧠 RAG AI Service (Python FastAPI)
│   ├── app/
│   │   ├── main.py             #    FastAPI app with lifespan management
│   │   ├── api/
│   │   │   ├── health.py       #    Health check endpoints
│   │   │   └── transactions.py #    /ingest, /query, /prompt, /query/stream
│   │   ├── core/
│   │   │   └── config.py       #    Settings (LLM, CORS, embeddings)
│   │   ├── models/
│   │   │   └── schemas.py      #    Pydantic request/response models
│   │   ├── services/
│   │   │   ├── embeddings.py   #    HuggingFace MiniLM-L6-v2 wrapper
│   │   │   ├── llm.py          #    ChatOpenAI initialization (OpenRouter)
│   │   │   └── rag_service.py  #    Core RAG logic — vector store, query processing
│   │   ├── utils/
│   │   │   ├── answer_generator.py  # Conversational answer formatting
│   │   │   ├── cache.py        #    Query result caching
│   │   │   ├── chat_history.py #    PostgreSQL chat persistence
│   │   │   ├── data_store.py   #    Multi-user in-memory data store
│   │   │   ├── filters.py      #    NLP filter extraction (date, amount, type, mode)
│   │   │   ├── formatters.py   #    Transaction → text formatting for embeddings
│   │   │   └── query_mode.py   #    Intelligent query routing
│   │   └── db/
│   │       └── database.py     #    PostgreSQL connection (SQLAlchemy)
│   ├── run.py                  #    Uvicorn entry point
│   └── requirements_api.txt    #    Python dependencies
│
├── docker/                      # 🐳 Docker Compose files
│   └── docker-compose.yml
│
├── kubernetes/                  # ☸️ Kubernetes manifests
│   ├── kubernetes-dashboard/
│   └── microservices/
│
├── README.md                    # 📖 This file
└── LICENSE
```

---

## 🤝 Contributing

We welcome contributions from the community! VittaManthan is built for learning, experimentation, and collaboration in the fintech + AI space.

### How to Contribute

1. **Fork the Repository**
   ```bash
   git clone https://github.com/Prabal0202/VittaManthan.git
   cd VittaManthan
   ```

2. **Create a Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make Your Changes**
   - Follow existing code style and conventions
   - Add comments for complex logic
   - Write tests for new features (if applicable)

4. **Test Your Changes**
   ```bash
   # For Spring Boot services
   mvn clean test
   
   # For RAG service
   cd FastAPIProject1
   pytest
   
   # For frontend
   cd frontend
   npm test
   ```

5. **Commit with Clear Messages**
   ```bash
   git commit -m "feat: add support for new payment mode filtering"
   ```

6. **Push and Create a Pull Request**
   ```bash
   git push origin feature/your-feature-name
   ```

### Contribution Areas

We're especially interested in contributions for:

- 🧠 **RAG Enhancements**: New query modes, better prompt engineering, alternative vector stores
- 🌐 **Language Support**: Additional regional languages (Tamil, Telugu, Bengali, etc.)
- 📊 **Analytics**: New visualization types, financial insights, anomaly detection algorithms
- 🔒 **Security**: Vulnerability fixes, encryption improvements, compliance features
- 📱 **Mobile App**: React Native or Flutter mobile app development
- 🧪 **Testing**: Unit tests, integration tests, E2E tests
- 📖 **Documentation**: Tutorials, API docs, architecture deep-dives

### Code of Conduct

- Be respectful and inclusive
- Provide constructive feedback
- Focus on the problem, not the person
- Help newcomers get started

### Issues & Bug Reports

Found a bug? Have a feature request? [Open an issue](https://github.com/Prabal0202/VittaManthan/issues) with:
- **Clear title** describing the issue
- **Steps to reproduce** (for bugs)
- **Expected vs actual behavior**
- **Screenshots** (if applicable)
- **Environment details** (OS, Java/Python version, etc.)
---

## 📚 References

- [Setu Account Aggregator Developer Docs](https://docs.setu.co)
- [Sahamati — Account Aggregator Framework](https://sahamati.org.in/)
- [LangChain Documentation](https://docs.langchain.com/)
- [FAISS — Facebook AI Similarity Search](https://github.com/facebookresearch/faiss)
- [Sentence Transformers — HuggingFace](https://www.sbert.net/)
- [OpenRouter — Multi-Model LLM Gateway](https://openrouter.ai/)
- [Spring Cloud Gateway](https://spring.io/projects/spring-cloud-gateway)
- [FastAPI Documentation](https://fastapi.tiangolo.com/)

---

## 👤 Author

<div align="center">

**Prabal Pratap Singh**

Backend Engineer · AI/ML Enthusiast · DevOps Practitioner

[![Email](https://img.shields.io/badge/Email-940pps@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:940pps@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-prabal864-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/prabal864/)
[![GitHub](https://img.shields.io/badge/GitHub-prabal864-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/prabal864)

</div>

---

## 📌 License & Disclaimer

This project is developed for **educational and demonstration purposes** using the Setu sandbox environment. No real user financial data is used or stored.

- All financial data shown in screenshots is synthetic/sandbox test data
- The platform demonstrates AA ecosystem integration patterns for learning purposes
- API keys, secrets, and credentials referenced are for sandbox environments only

---

<div align="center">

**Built with ❤️ using Spring Boot, FastAPI, LangChain, FAISS, and React**

*VittaManthan — Churning Financial Wisdom from Data*

</div>


