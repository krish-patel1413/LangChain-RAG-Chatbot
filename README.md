# Local PDF Document RAG Chatbot with Conversational Memory

A production-ready Retrieval-Augmented Generation (RAG) system built in Python utilizing **LangChain** and **OpenRouter** API proxy architectures. This interactive tool ingests unstructured local PDF files (e.g., academic research papers), converts document segments into vector embeddings via HuggingFace transformers, saves them inside a FAISS vectorstore, and enables continuous conversational Q&A threads with reliable chat history memory formatting.

---

# Key Features

*   **Contextual Accuracy Parsing:** Optimized system prompt architectures that prevent the LLM from pulling metadata definitions exclusively from references and citations.
*   **Persistent Conversational Memory:** Uses structured placeholder arrays (`chat_history`) ensuring previous message nodes track back flawlessly into subsequent queries.
*   **Custom API Proxy Translation Gateways:** Custom OpenRouter abstraction scripts built over raw `openai` clients to sidestep legacy LangChain serialization (`model_dump`) interface validation errors.
*   **Local Embedding Pipelines:** No-cost vector extraction running completely on-device using HuggingFace's `all-MiniLM-L6-v2` transformer model.

---

# Tech Stack & Requirements

*   **Framework Core:** `langchain`, `langchain-community`, `langchain-openai`
*   **Vector Engine:** `faiss-cpu`
*   **Local Transformers:** `sentence-transformers`
*   **Inference Provider:** OpenRouter (routing `openai/gpt-4o-mini`)
*   **Document Parsers:** `pypdf`

---

# Step-by-Step Installation Setup

### 1. Clone the project files locally
```bash
git clone https://github.com
cd YOUR_REPOSITORY_NAME
```

### 2. Set up a virtual environment and dependencies
```bash
python -m venv venv
# On Windows use: venv\Scripts\activate 
# On Mac/Linux use: source venv/bin/activate

pip install langchain langchain-openai langchain-community faiss-cpu sentence-transformers pypdf openai ipython
```

### 3. Add your target data document
Drop your desired target PDF documents directly into the base directory of the folder (e.g., `Attention is all you need.pdf`).

---

# Execution Instructions

1. Fire up your environment instance by executing your Jupyter Notebook server or launching your workspace loop cells inside a `.ipynb` interface.
2. Provide your active credentials file access points securely inside the target cell structure:
```python
client = openai.OpenAI(
    base_url="https://openrouter.ai",
    api_key="YOUR_OPENROUTER_SECRET_KEY_HERE"  # Keep this key hidden before pushing code!
)
```
3. Run through the initialization lines to load the database index strings, compile the retrieval chains, and establish the user query input text terminal box loop.
4. Interact using human phrases. Type `exit` or `quit` to cleanly break out of active console operations.

---

