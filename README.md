# 🚀 langgraph-ai-crm-hcp
### Round 1 – Technical Assignment (60-Hour Challenge)

An AI-powered Customer Relationship Management (CRM) module designed for the **Life Sciences industry**, enabling field representatives to log Healthcare Professional (HCP) interactions using:

- 📝 Structured Form  
- 💬 Conversational AI Assistant  

This project demonstrates an **AI-to-UI bridge** using LangGraph, where natural language input is automatically converted into structured CRM data and reflected instantly in the UI.

---

## 🏥 Problem Statement

Field representatives in the Life Sciences domain often manually log HCP interactions, which results in:

- Time-consuming data entry  
- Inconsistent documentation  
- Missed follow-ups  
- Reduced productivity  

This system automates and enhances the interaction logging process using AI.

---

## 🧠 Core Innovation – AI-to-UI Bridge

1. User enters interaction summary via chat
2. FastAPI backend processes the request
3. LangGraph agent selects the appropriate tool
4. LLM extracts structured data
5. JSON response updates Redux store
6. React form auto-populates automatically

This eliminates manual form filling while preserving structured CRM integrity.

---

## 🛠 Tech Stack

### Frontend
- React.js (v18+)
- Redux Toolkit (State Management)
- Axios
- Google Inter Font
- CSS Flexbox

### Backend
- Python 3.10+
- FastAPI
- LangGraph (Stateful Agent Orchestration)
- Groq LLM (gemma2-9b-it / llama-3.3-70b-versatile)
- Pydantic
- python-dotenv

### Database (Conceptual Design)
- MySQL / PostgreSQL

---

## 🧩 LangGraph Agent & Tools

The LangGraph agent orchestrates sales-related activities through 5 structured tools.

### 1️⃣ Log Interaction (Required)
- Extracts:
  - HCP Name
  - Date
  - Topics Discussed
  - Sentiment
  - Materials Shared
- Uses LLM for summarization & entity extraction
- Returns structured JSON response

---

### 2️⃣ Edit Interaction (Required)
- Modifies specific fields only
- Preserves existing form state
- Ensures controlled updates

---

### 3️⃣ Search HCP
- Simulates database validation
- Verifies HCP identity

---

### 4️⃣ Add Material
- Appends brochures, PDFs, safety documents
- Dynamically updates material list

---

### 5️⃣ Suggest Follow-up
- Analyzes interaction summary
- Recommends next-best actions

---

## 🏗 System Architecture

```
User (Chat Input)
        ↓
FastAPI Backend
        ↓
LangGraph Agent
        ↓
Tool Execution
        ↓
Structured JSON Output
        ↓
Redux Store
        ↓
React UI Auto-Update
```

---

## 📂 Project Structure

```
AI_CRM_Project/
│
├── backend/
│   ├── main.py
│   ├── tools.py
│   ├── agent.py
│   └── .env
│
├── frontend/
│   ├── src/
│   │   ├── store.js
│   │   ├── App.js
│   │   ├── components/
│   │   └── index.js
│   └── package.json
│
└── README.md
```

---

## ⚙️ Setup & Installation

### Backend Setup

```bash
cd backend
pip install fastapi uvicorn langgraph langchain-groq pydantic python-dotenv
```

Create `.env` file:

```
GROQ_API_KEY=your_api_key
```

Run backend:

```bash
uvicorn main:app --reload
```

Backend runs on:
```
http://127.0.0.1:8000
```

---

### Frontend Setup

```bash
cd frontend
npm install
npm start
```

Frontend runs on:
```
http://localhost:3000
```

---

## 🎯 Test Scenarios

### Scenario 1 – Initial Logging
Input:
```
Met Dr. Smith today. Discussed Product X efficacy.
Sentiment was positive and shared clinical brochure.
```

Tool Triggered: `log_interaction`  
Result: Form fields auto-populated.

---

### Scenario 2 – Field Correction
Input:
```
Correction: Doctor was Dr. John Doe and sentiment was neutral.
```

Tool Triggered: `edit_interaction`  
Result: Only specific fields updated.

---

### Scenario 3 – Add Material
Input:
```
Add Safety Guidelines PDF to materials shared.
```

Tool Triggered: `add_material`  
Result: Material list updates dynamically.

---

## 🔐 Security Considerations

- API keys stored securely in environment variables
- No hardcoded credentials
- Pydantic schema validation for structured responses
- Designed for pharma-compliant data handling
- Extendable for audit logs & role-based access

---

## 📈 Key Highlights

- Conversational AI integrated with enterprise UI
- Real-world LangGraph orchestration
- Redux-based single source of truth
- Structured data integrity with natural language input
- Life Sciences CRM domain focus

---

## 🎥 Submission Deliverables

- GitHub Repository
- Technical Documentation PDF
- 10–15 Minute Demo Video

---

## 👨‍💻 Author

Tushar  
AI/ML & Full Stack Developer  
Focused on AI-first system architecture

---

