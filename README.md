# Graph-RAG for Medical Emergency Triage

**Master's Thesis — University of Stavanger (Jan 2025 – June 2025)**  
**In collaboration with Laerdal Medical, Norway**

> Presented at the *"Enabling Technologies in Birth & Time-Critical Emergencies"* international conference.

## Overview

This project benchmarks **RAG vs. Graph-RAG** on proprietary Norwegian emergency medical protocols (NIMN) to reduce hallucinations in clinical AI decision support. A property knowledge graph was built with LLM-based entity extraction and integrated into a multi-stage retrieval and validation pipeline.

**Graph-RAG outperformed standard RAG by 43%** on complex clinical queries (overall score: 4.3 vs. 3.0), with **75% retrieval precision** vs. 48% for vector-only RAG.

## Key Results

| Method | Retrieval Precision | Overall Score | 
|--------|-------------------|---------------|
| Vector-only RAG | 48% | 3.0 |
| **Graph-RAG (Ours)** | **75%** | **4.3** |
| Improvement | +56% | **+43%** |

Outputs validated through a **multi-stage QA pipeline** using query rewriting and LLM-as-Judge scoring across accuracy, safety, clarity, and completeness.

## System Architecture

The pipeline integrates:
- **Property Knowledge Graph** built from Norwegian emergency medical protocols (NIMN)
- **LLM-based entity and relation extraction**
- **Graph-RAG retrieval** combining structured graph traversal with vector search
- **LLM-as-Judge evaluation** for multi-dimensional output scoring

## Tech Stack

- Python
- LlamaIndex (graph store, property graph)
- LLM pipelines (OpenAI / local models)
- Knowledge Graph construction and querying
- Jupyter Notebooks

## Repository Structure

- `Stand_alone_queries.ipynb` — standalone query testing against the knowledge graph
- `experimental/` — early experiments, graph construction iterations, and ablation studies
- `kgstore/` — property graph knowledge store

## Requirements

- Python 3.10+
- [Poetry](https://python-poetry.org/docs/) (for dependency management)
- Jupyter Notebook

## Installation

```bash
# Clone the repository
git clone https://github.com/HasanIftekhar/Medical-emergency-agent.git
cd Medical-emergency-agent

# Install dependencies
poetry install

# Activate virtual environment
poetry shell
```

## Usage

Run the notebooks directly:

1. **`Stand_alone_queries.ipynb`** — query the knowledge graph with clinical questions
2. **`experimental/`** — explore early graph construction and RAG comparison experiments

Open your browser and navigate to `localhost:[port]` to interact with the agent UI.

## Research Context

This work was conducted as part of an M.Sc. thesis at the University of Stavanger in partnership with Laerdal Medical. The dataset used (NIMN — Norwegian Index for Medical Emergency) is proprietary and not included in this repository.

*Original codebase co-developed with [@cyeedmaroof](https://github.com/cyeedmaroof).*
