![download](https://github.com/user-attachments/assets/2d396860-6e9d-456a-86b2-2afc611c8b81)  
![Screenshot 2025-04-20 170746](https://github.com/user-attachments/assets/dbc20496-67be-47b8-9a24-06a9871a01e5)

![images](https://github.com/user-attachments/assets/53eb4059-f148-4be0-8cc0-6f6626c9f0bf)
![d0b0bc88-fd53-41b8-a9a6-cff84b24c942](https://github.com/user-attachments/assets/e5f084de-4b76-4197-8cdd-73d528f98f4d)
📚 About DataStax AstraDB and Apache Cassandra
🚀 What is DataStax AstraDB?
AstraDB is a serverless database-as-a-service (DBaaS) built on top of Apache Cassandra.

It removes the complexity of managing Cassandra clusters.

You can store structured and vector data (embeddings) for AI applications.

AstraDB is highly scalable, secure, and globally distributed.

⚡ What is Apache Cassandra?
Cassandra is a highly scalable NoSQL database.

It is designed for high availability, fault tolerance, and massive data handling.

Big companies like Instagram, Netflix, and Uber use Cassandra for critical systems.

🛠️ Why use AstraDB + Cassandra?

Feature	AstraDB + Cassandra
Scalability	Grows automatically as your data grows
Vector Search	Supports AI/ML use-cases (RAG apps)
Serverless	No need to manage infrastructure
Global Distribution	Deploy close to users worldwide
Easy Integration	API, SDKs, and tools like CassIO available
🎯 Key Benefits
Free-tier available (great for small projects).

Integrates easily with Ollama, LangChain, LlamaIndex, and more.

Perfect for RAG (Retrieval-Augmented Generation) and AI search.

Works with CQL (Cassandra Query Language).

✨ AstraDB in this Project
Used as the vector database to store embeddings.

Fast semantic search and retrieval for AI apps.

Connected using cassio Python SDK.

![AstraDB](https://img.shields.io/badge/Powered%20By-DataStax%20Astra-blue)
![Cassandra](https://img.shields.io/badge/Database-Cassandra-orange)

🛠 1. Create AstraDB Database
Sign up / Log in to DataStax Astra.

Click "Create Database" ➔ Choose "Vector" or "Cassandra" database.

Fill:

Database Name (Example: ragdb)

Keyspace Name (Example: ragkeyspace)

Choose free tier if you want!

Click Launch Database → Wait for it to be ready.

🔐 2. Get Your Connection Details
Go to your database → Connect → Select "Secure Connect".

Download the Secure Connect Bundle (a zip file).

You will get:

ASTRA_DB_ID

ASTRA_DB_REGION

ASTRA_DB_APPLICATION_TOKEN

🐍 3. Install Python SDK (cassio)
Open Colab / VSCode Terminal / Jupyter and install:

bash
Copy
Edit
pip install cassio
🔗 4. Connect to AstraDB from Code
python
Copy
Edit
import cassio

cassio.init(
    token="your_astra_application_token",
    database_id="your_astra_db_id",
)
✅ Now your Python app is connected to AstraDB!

📥 5. Example: Insert and Retrieve Data
Insert some data:


cassio.table_create(
    table="music_recommend",
    primary_key="song_id",
    columns={
        "song_id": "text",
        "embedding": "vector<float, 1024>",
        "song_name": "text",
    }
)

cassio.table_insert(
    table="music_recommend",
    data={
        "song_id": "song123",
        "embedding": [0.1, 0.2, ..., 0.5],  # 1024 floats
        "song_name": "My Song",
    }
)
Query similar songs:
cassio.table_query(
    table="music_recommend",
    vector_column="embedding",
    query_vector=[0.1, 0.2, ..., 0.5],
    top_k=3
)
Ollama + AstraDB RAG System
Build a Retrieval-Augmented Generation (RAG) system using Ollama embeddings and DataStax AstraDB (Apache Cassandra).

<br>
🧩 Project Structure
Copy
Edit
ollama_astra_rag/
├── app.py
├── requirements.txt
└── README.md
<br>
🚀 How It Works
✅ Generate text embeddings using Ollama (local LLM).

✅ Store embeddings into AstraDB (serverless Cassandra database).

✅ Perform semantic search: find similar texts using vector similarity.


🛠️ Setup Instructions
Clone the repository


git clone https://github.com/your-username/ollama_astra_rag.git
cd ollama_astra_rag

Install dependencies


pip install -r requirements.txt

Configure AstraDB

Create a free database at DataStax AstraDB.

Get your Application Token and Database ID.

Update these in app.py:


ASTRA_DB_APPLICATION_TOKEN = "your_astra_token",

ASTRA_DB_ID = "your_astra_db_id",

OLLAMA_KEY="OLLAMA_API"

![Screenshot 2025-04-20 170752](https://github.com/user-attachments/assets/830b5224-8dfd-4cd0-a839-560be82aefd9)


# AI Document Search with AstraDB Vector Store and RAG (with ngrok)

## 🧠 Project Overview

This project builds a **document search system** using **Retrieval-Augmented Generation (RAG)** with **AstraDB** as the vector database. The system embeds documents into vectors, stores them in AstraDB, and retrieves relevant information to answer user queries with the help of a large language model (LLM). Ngrok is used to expose the local app for external access.

## 🚀 Features

- Upload documents (PDFs, text, etc.) to build a vector database  
- Vector similarity search using AstraDB  
- Query answering via LLM using retrieved document context  
- Local deployment with public URL via ngrok

## 🛠️ Tech Stack

- Python 3.11+  
- AstraDB vector database  
- LangChain / OpenAI API / or your LLM backend  
- Ngrok for tunneling  
- FAISS or similar vector embedding libraries (if used)

## 📦 Installation

1. Clone this repository:

```bash
git clone https://github.com/BVISHNU78/AI-Document-Search-with-AstraDB-Vector-Store-and-RAG--with-ngrok--
cd AI-Document-Search-with-AstraDB-Vector-Store-and-RAG--with-ngrok--
