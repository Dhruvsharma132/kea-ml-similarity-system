# kea-ml-similarity-system
Semantic similarity system using sentence embeddings for lead matching

# 🔍 KeaBuilder ML Task 1: Semantic Similarity System

## 📌 Overview
This project implements a semantic similarity system to match user inputs (e.g., leads, prompts) with the most relevant existing entries.

## ⚙️ Approach
- Used Sentence Transformers (`all-MiniLM-L6-v2`) to generate embeddings
- Computed cosine similarity between query and inputs
- Returned the most similar match

## 🚀 Features
- Semantic similarity (better than keyword matching)
- Top-K matching support
- Scalable design (can integrate with FAISS/Pinecone)

## 🧠 Use Case
- Matching similar leads
- Suggesting relevant templates
- Improving automation workflows

## 🛠️ Tech Stack
- Python
- Sentence Transformers
- Scikit-learn

## ▶️ How to Run

1. Install dependencies:
```bash
pip install sentence-transformers scikit-learn
