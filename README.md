# 🤖 PearlsPartner - AI-Powered Supply Account Manager

Memory-driven AI assistant for marketplace operations with intelligent seller interaction tracking and context-aware recommendations.

![Python](https://img.shields.io/badge/Python-3.12+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-Latest-green.svg)
![LangChain](https://img.shields.io/badge/LangChain-Enabled-orange.svg)
![Hackathon](https://img.shields.io/badge/Hackathon-MemHack-purple.svg)

## 🏆 Hackathon Project

**Event:** MemHack - Experiential Learning Lab (ELL)  
**Institution:** Pace University  
**Category:** AI & Memory Systems

---

## 📌 Overview

PearlsPartner is an AI-powered Supply Account Manager (SAM) assistant designed to streamline marketplace operations (Amazon-style) by:
- Remembering past seller interactions and escalations
- Providing context-aware insights and recommendations
- Reducing repetitive manual tracking
- Enhancing agent workflows with continuous learning

**Unlike traditional CRMs**, PearlsPartner leverages episodic memory and profile management to deliver actionable intelligence for better decision-making.

---

## ✨ Key Features

### 🧠 **Memory-Powered AI**
- **Short-term context** for ongoing conversations
- **Long-term memory** via MemMachine (episodic + profile storage)
- Continuous learning from past interactions

### 👤 **Profile Management**
- Track seller information, risk tier, and preferences
- Preferred communication channels
- Historical performance metrics

### 📝 **Episodic Memory**
- Logs all interactions: tickets, emails, chat notes
- Searchable interaction history
- Pattern recognition for recurring issues

### 💡 **Context-Aware Recommendations**
- Suggests next steps for escalations
- Account health monitoring
- Proactive risk identification

### 📚 **Knowledge Integration**
- Retrieve SOPs and KB articles
- Access relevant metrics for decision support
- RAG (Retrieval-Augmented Generation) pipelines

### 🔧 **LangChain Orchestration**
- Manages agent workflow and tool calls
- Coordinates memory retrieval and LLM interactions
- Seamless integration between components

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | React + Vite |
| **Backend** | FastAPI (Python) |
| **Memory Layer** | MemMachine (episodic + profile) |
| **Databases** | Neo4j (episodic), PostgreSQL (profile) |
| **AI/LLM** | OpenAI GPT-4 |
| **Orchestration** | LangChain + LangGraph |
| **Containerization** | Docker Compose |
| **Tools** | Ticket/CRM fetch, Knowledge search, Metrics |

---

## 🏗️ System Architecture

```
┌─────────────────────┐
│   SAM User (Agent)  │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────────────────┐
│  LangChain Agent Orchestrator   │
└──────────┬──────────────────────┘
           │
     ┌─────┴─────┬──────────┬─────────────┐
     │           │          │             │
     ▼           ▼          ▼             ▼
┌─────────┐ ┌────────┐ ┌────────┐ ┌──────────────┐
│MemMachine│ │  LLM   │ │ Neo4j  │ │ Data         │
│ Memory   │ │ GPT-4  │ │ + PG   │ │ Connectors   │
│ Layer    │ │        │ │        │ │ (CRM/KB)     │
└─────────┘ └────────┘ └────────┘ └──────────────┘
```

### **Workflow:**
1. **User Query** → LangChain Agent Orchestrator
2. **Memory Retrieval** → MemMachine fetches relevant context
3. **LLM Processing** → GPT-4 generates recommendations
4. **Tool Execution** → Fetch tickets, KB articles, metrics
5. **Response** → Context-aware actionable insights

---

## 🚀 Setup Instructions

### **Prerequisites**

- Python 3.12+
- Docker & Docker Compose
- OpenAI API Key (or alternative LLM provider)
- Neo4j Database
- PostgreSQL Database

### **Installation**

#### **1. Clone Repository**
```bash
git clone https://github.com/yourusername/pearlspartner.git
cd pearlspartner
```

#### **2. Environment Setup**
```bash
# Create .env file
cp .env.example .env

# Add your API keys
OPENAI_API_KEY=your_openai_key_here
NEO4J_URI=bolt://localhost:7687
NEO4J_USER=neo4j
NEO4J_PASSWORD=your_password
POSTGRES_URI=postgresql://user:password@localhost:5432/pearlspartner
```

#### **3. Docker Setup**
```bash
# Start all services
docker-compose up -d

# Check status
docker-compose ps
```

#### **4. Backend Setup**
```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload
```

#### **5. Frontend Setup**
```bash
cd frontend
npm install
npm run dev
```

### **Access the Application**
- **Frontend:** http://localhost:5173
- **Backend API:** http://localhost:8000
- **API Docs:** http://localhost:8000/docs

---

## 🎯 Use Cases

### **For Supply Account Managers:**
- Quick access to seller interaction history
- AI-generated summaries of past escalations
- Proactive alerts for high-risk accounts
- Contextual recommendations for next steps

### **For Operations Teams:**
- Automated knowledge retrieval
- Consistent handling of recurring issues
- Data-driven insights for policy updates
- Reduced training time for new agents

---

## 📊 Key Capabilities

✅ **Seller Profile Tracking** - Risk tier, preferences, communication history  
✅ **Episodic Memory** - Complete interaction logs with searchability  
✅ **Smart Recommendations** - AI-driven next steps and escalation guidance  
✅ **Knowledge Retrieval** - Instant access to SOPs and KB articles  
✅ **Metrics Integration** - Performance data for informed decisions  
✅ **Conversation Context** - Maintains thread across multiple interactions  

---

## 🔧 API Endpoints

### **Memory Operations**
- `POST /api/memory/add` - Store new interaction
- `GET /api/memory/search` - Query past interactions
- `GET /api/memory/profile/{seller_id}` - Get seller profile

### **Agent Operations**
- `POST /api/agent/query` - Ask SAM assistant
- `GET /api/agent/recommendations` - Get next steps
- `POST /api/agent/escalate` - Create escalation

### **Knowledge Base**
- `GET /api/kb/search` - Search SOPs and articles
- `GET /api/kb/metrics/{seller_id}` - Get seller metrics

---

## 📁 Project Structure

```
pearlspartner/
├── backend/
│   ├── main.py                 # FastAPI app
│   ├── agents/                 # LangChain agents
│   ├── memory/                 # MemMachine integration
│   ├── tools/                  # CRM, KB, metrics tools
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── components/         # React components
│   │   ├── pages/             # Application pages
│   │   └── api/               # API client
│   ├── package.json
│   └── vite.config.js
├── docker-compose.yml
├── .env.example
└── README.md
```

---

## 🧪 Testing

```bash
# Backend tests
cd backend
pytest tests/

# Frontend tests
cd frontend
npm test
```

---

## 🔮 Future Enhancements

- [ ] Multi-language support
- [ ] Voice interface integration
- [ ] Advanced analytics dashboard
- [ ] Slack/Teams integration
- [ ] Custom LLM fine-tuning
- [ ] Mobile application
- [ ] Real-time collaboration features
- [ ] Automated workflow triggers

---

## 👥 Team

**Palak Shah**  
MS in Computer Science (AI/ML) | Pace University


---

## 🙏 Acknowledgments

- **MemHack Hackathon** - Pace University ELL
- **MemMachine** - Memory layer technology
- **LangChain Community** - Agent orchestration framework
- **OpenAI** - GPT-4 LLM capabilities

---

## 📄 License

MIT License - See [LICENSE](LICENSE) file for details

---

## 📚 Documentation

- [MemMachine Docs](https://memmachine.ai/docs)
- [LangChain Guide](https://python.langchain.com/docs/)
- [FastAPI Documentation](https://fastapi.tiangolo.com/)

---

⭐ **Star this repo if you found it useful!**

**Tags:** `langchain` `artificial-intelligence` `hackathon` `memhack` `ai-assistant` `crm` `neo4j` `fastapi` `react` `postgresql` `gpt-4`
