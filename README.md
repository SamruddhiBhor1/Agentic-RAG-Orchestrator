# 🤖 Agentic RAG Orchestrator

[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![LangChain](https://img.shields.io/badge/Framework-LangChain-green.svg)](https://github.com/langchain-ai/langchain)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An advanced multi-agent system designed for autonomous research, intelligent knowledge retrieval, and synthesized response generation. This project leverages state-of-the-art LLMs and agentic workflows to solve complex information retrieval tasks that standard RAG pipelines struggle with.

## 🌟 Key Features

- **Multi-Agent Architecture**: Uses specialized agents (Researcher, Critic, and Writer) to ensure high-quality, verified outputs.
- **Self-Correcting Retrieval**: Implements iterative search and verification to minimize hallucinations.
- **Dynamic Context Management**: Efficiently handles large context windows with intelligent chunking and relevance ranking.
- **Plug-and-Play Vector Stores**: Supports ChromaDB, Pinecone, and FAISS.
- **Enterprise Ready**: Built with modularity, logging, and comprehensive error handling.

## 🏗️ Architecture

`mermaid
graph TD
    User([User Query]) --> Orchestrator{Agent Orchestrator}
    Orchestrator --> Researcher[Researcher Agent]
    Researcher --> VectorDB[(Vector Database)]
    Researcher --> SearchEngine[Web Search Engine]
    Researcher --> Critic[Critic Agent]
    Critic -- Verification Failed --> Researcher
    Critic -- Verified --> Writer[Writer Agent]
    Writer --> FinalResponse([Final Synthesized Response])
`

## 🚀 Quick Start

### Prerequisites
- Python 3.9 or higher
- OpenAI API Key (or other supported LLM provider)

### Installation
`ash
git clone https://github.com/SamruddhiBhor1/Agentic-RAG-Orchestrator.git
cd Agentic-RAG-Orchestrator
pip install -r requirements.txt
`

### Usage
`python
from orchestrator import AgenticRAG

# Initialize the system
rag_system = AgenticRAG(api_key="your_api_key")

# Run a complex query
query = "Compare the impact of transformer architectures on NLP vs Computer Vision from 2017 to 2024."
result = rag_system.execute(query)

print(result)
`

## 🛠️ Tech Stack
- **Orchestration**: LangGraph / LangChain
- **LLMs**: GPT-4o, Claude 3.5 Sonnet
- **Vector DB**: ChromaDB
- **Embeddings**: OpenAI text-embedding-3-small

---
Developed by **Samruddhi Bhor** - Generative AI Engineer