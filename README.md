## 🧑‍💻Multi-Agent Conversational System with RAG & Tools

This project implements a multi-agent conversational system using LangChain and EuriAI.
It combines specialized agents (Researcher & Teacher) with a Router Agent that dynamically decides which agent should respond.

### The system is enhanced with tools like:

📄 Summarizer (summarizes long text)

🌐 Wikipedia (fetches knowledge from Wikipedia)

📚 RAG (Retrieval-Augmented Generation) (answers questions from local documents)

🌍 Translator (translates text between languages)

🚀 Features

Two Specialized Agents:

🧪 Researcher → factual, data-driven answers (uses RAG & Wikipedia).

🎓 Teacher → explains concepts and helps with learning.

Router Agent: Automatically routes queries to the right agent.

Custom Embeddings: Uses EuriAI embedding API instead of OpenAI.

RetrievalQA: Queries a local knowledge base (founder.txt).

🛠️ Installation & Setup

1. Clone the repository

```bash
git clone https://github.com/SachdevaVansh/Founders_Story_RAG_with_Tools-Agents.git
cd Founders_Story_RAG_with_Tools-Agents
```

3. Create a virtual environment

```bash
conda create -n multiagent python=3.10 -y
conda activate multiagent
```

Or with venv:

```bash
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
```

3. Install dependencies

```bash
pip install -r requirements.txt
```

If you don’t have a requirements.txt yet, here are the essentials:

- langchain
- langchain-community
- langchain-huggingface
- faiss-cpu
- numpy
- requests
- wikipedia
- python-dotenv
- euriai

🔑 Environment Variables

Create a .env file in the project root and add your LLM API Key:

LLM_API_KEY=your_api_key_here

📂 Project Structure
.
├── data/
│   └── founder.txt        # Local knowledge base for RAG
├── main.py                # Main script (multi-agent system)
├── requirements.txt
└── README.md

▶️ Running the Project

After setup, run:

python main.py


You’ll see:

Connected multi-Agent Chat (type 'exit' to quit):

Agents: Researcher, Teacher (chosen automatically by the router) 


Now type queries:

You: Summarize the founder's journey
[Router -> Researcher
  The founder's story summary is... ]

You: Explain backpropagation
[Router -> Teacher
  Backpropagation is a method used to... ]

🧩 How It Works

User enters a query.

The Router Agent decides whether it should go to:

Researcher Agent (fact-based, RAG/Wiki queries)

Teacher Agent (concept explanations).

Agents can call tools to retrieve or process data.

The response is printed with agent attribution.

📝 Example Tools Usage

Summarizer → "Summarize this paragraph..."

Wikipedia → "Who is Elon Musk?"

RAG → "What is mentioned in the founder’s story about funding?"

Translate → "Hello world || French"

🧑‍🔧 Next Steps / Improvements

Add more specialized agents (e.g., Financial Advisor, Project Manager).

Extend RAG to multiple documents (multi-file knowledge base).

Deploy via FastAPI/Streamlit for a web UI.
