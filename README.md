# 🍽️ Restaurant Finder — Upstate NY

> **IST 488/688 Final Project** · Syracuse University · Spring 2026

A multi-agent Streamlit application that discovers, scrapes, enriches, and recommends restaurants across Syracuse, Rochester, and Albany using a coordinated AI pipeline.

## 🚀 Live App

**[https://ist488final.streamlit.app/](https://ist488final.streamlit.app/)**

## 📖 Overview

This project implements a full-stack, multi-agent system for restaurant discovery and recommendation. Each agent in the pipeline handles a distinct responsibility—from discovering restaurants via the Google Places API, to scraping website content, enriching data with GPT-4o, storing embeddings in ChromaDB, and answering user queries with built-in ethical evaluation and self-reflection.

## 🏗️ Architecture

```
User Query
    │
    ▼
┌──────────────────┐
│  Discovery Agent  │  ← Google Places API / Mock Data
│    (Lauren)       │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Restaurant Scraper│  ← Trafilatura + BeautifulSoup
│     (Ryan)        │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Enrichment Agent  │  ← GPT-4o structured extraction
│   (Leytisha)      │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  ChromaDB Store   │  ← Cosine-similarity vector search
│     (Toby)        │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Query Agent +    │  ← Conversational recommendations
│  Ethics/Reflection│     with ethical scoring & self-critique
└──────────────────┘
```

## ✨ Key Features

- **Live Restaurant Discovery** — Searches the Google Places API across three upstate NY cities
- **Intelligent Web Scraping** — Extracts menus and content from restaurant websites (HTML + PDF)
- **AI-Powered Enrichment** — Uses GPT-4o to extract cuisine types, menu items, and pricing from scraped content
- **Vector Search** — ChromaDB-backed semantic search with cosine similarity and custom re-ranking
- **Conversational Recommendations** — Multi-turn chat interface powered by GPT-4o-mini
- **Ethical Evaluation** — Automated scoring across five dimensions: geographic fairness, price diversity, cuisine respect, transparency, and faithfulness
- **Self-Reflection** — Critique agent reviews responses and triggers revisions when quality issues are detected
- **Built-in Test Suite** — End-to-end tests for every pipeline stage

## 👥 Team

| Member     | Role                                        |
|------------|---------------------------------------------|
| **Lauren** | Discovery Agent — Google Places API integration |
| **Ryan**   | Restaurant Scraper — Web content extraction     |
| **Leytisha** | Enrichment, Query, Ethics & Reflection Agents |
| **Toby**   | ChromaDB Storage Layer — Vector embeddings      |

## 📂 Project Structure

```
IST488Final/
├── streamlit_app.py        # Main Streamlit application (all agents integrated)
├── discovery_agent.ipynb   # Lauren's discovery agent notebook
├── restaurant_scraper.ipynb# Ryan's scraper notebook
├── agents.ipynb            # Leytisha's agent notebooks
├── chromadb_store.ipynb    # Toby's ChromaDB notebook
├── test_suite.ipynb        # End-to-end test notebook
├── test_fixtures.json      # Test fixture data
└── README.md
```

## ⚙️ Setup & Running Locally

### Prerequisites

- Python 3.10+
- An OpenAI API key (required for AI-powered features)
- A Google Places API key (optional — mock data is used as fallback)

### Installation

```bash
pip install streamlit openai chromadb requests beautifulsoup4 trafilatura pdfplumber lxml
```

### Run

```bash
streamlit run streamlit_app.py
```

Enter your API keys in the sidebar to enable live discovery and AI-powered enrichment/querying.

## 📝 License

This project was created for academic purposes as part of IST 488/688 at Syracuse University.