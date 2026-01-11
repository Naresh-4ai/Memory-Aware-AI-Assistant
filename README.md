---

# 🧠 Memory-Aware AI Assistant

A **memory-aware conversational AI** that persistently remembers user interactions using **vector + graph memory**, enabling context-rich, personalized conversations over time.

This project integrates **OpenAI LLMs**, **Mem0**, **Qdrant**, and **Neo4j**, and is fully containerized using **Docker + VS Code Dev Containers** for a reproducible, production-grade development environment.

---

## 🚀 What This Project Does

* Accepts continuous user input via CLI
* Retrieves **relevant past memories** before responding
* Injects memory context into the system prompt
* Generates contextual responses using OpenAI
* Stores both **user messages and AI replies** back into memory
* Builds a **long-term conversational memory loop**

This creates an assistant that **does not forget**.

---

## 🧩 Architecture Overview

```
User Input
   ↓
Memory Search (Qdrant + Neo4j)
   ↓
Context Injection (System Prompt)
   ↓
OpenAI LLM Response
   ↓
Memory Storage (Vector + Graph)
```

---

## 🛠️ Tech Stack

* **Python**
* **OpenAI API**
* **Mem0** (memory orchestration)
* **Qdrant** (vector database)
* **Neo4j** (graph memory)
* **Docker & Docker Compose**
* **VS Code Dev Containers**

---

## 📂 Project Structure

```
.
├── main.py                # Core memory-aware chat loop
├── requirements.txt       # Python dependencies
├── Dockerfile             # App container
├── docker-compose.yaml    # App + Qdrant + Neo4j services
├── devcontainer.json      # VS Code Dev Container config
├── .env                   # Environment variables (not committed)
```

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository

```bash
git clone <your-repo-url>
cd <your-repo-name>
```

---

### 2️⃣ Create `.env` File

Create a `.env` file in the project root:

```env
OPENAI_API_KEY=your_openai_api_key_here
```

> ⚠️ Never commit `.env` to GitHub

This key is required to initialize the OpenAI client.

---

## 🐳 Run with Docker (Recommended)

This project is designed to run as a **multi-service system**.

### Start All Services

```bash
docker compose up --build
```

This will start:

* Python application container
* Qdrant vector database
* Neo4j graph database

---

## 🧩 Best Practice: Run Inside VS Code Dev Container ⭐

For the **cleanest and most reliable experience**, it is **strongly recommended** to run this project inside a **VS Code Dev Container**.

### Why Dev Containers?

* Zero local setup issues
* Correct Python & system dependencies
* Automatic startup of Qdrant & Neo4j
* Identical environment for every developer
* Ideal for serious AI + research projects

### How to Use Dev Container

1. Install:

   * **Docker Desktop**
   * **VS Code**
   * **Dev Containers extension** (Microsoft)

2. Open the project folder in VS Code

3. When prompted, click:

```
Reopen in Container
```

OR manually:

```
Ctrl + Shift + P → Dev Containers: Reopen in Container
```

VS Code will:

* Build containers using `docker-compose.yaml`
* Start all required services
* Attach the editor to the running app container

Once the container is ready, run:

```bash
python main.py
```

✅ **This is the recommended way to run and develop this project.**

---

## 🧪 Run Locally (Without Docker)

> Use this only if Docker is unavailable.

### 1️⃣ Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # Linux / macOS
venv\Scripts\activate     # Windows
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Run the App

```bash
python main.py
```

---

## 💬 How It Works (Internal Flow)

* Loads environment variables
* Initializes:

  * OpenAI client
  * Mem0 memory engine
* For every user message:

  1. Searches relevant memories
  2. Injects memory into system prompt
  3. Generates response via OpenAI
  4. Stores conversation back into memory

This creates **persistent, evolving intelligence**.

---

## 🔐 Memory Design

* **Vector Memory (Qdrant)** → semantic recall
* **Graph Memory (Neo4j)** → relational understanding
* **Hybrid retrieval** → higher contextual accuracy

---

## 🧠 Why This Project Matters

This project explores **next-generation AI agent design**, including:

* Self-updating memory systems
* Context-aware reasoning
* Long-term personalization
* Clear separation of recall, reasoning, and generation

It forms a strong foundation for:

* Autonomous AI agents
* Research-grade memory pipelines
* Reliable long-term assistants
* Personalized AI products

---

## 🔮 Future Improvements

* Multi-user memory isolation
* Memory summarization & pruning
* Role-aware memory weighting
* Web / API interface
* LangGraph-based reasoning loops


