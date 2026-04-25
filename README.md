# 🔍 Semantic Similarity System (KeaBuilder ML Task)

## 📌 Overview

This project implements a **semantic similarity system** to match user inputs (such as leads, prompts, or queries) with the most relevant existing entries.

Unlike keyword-based approaches, this system uses **sentence embeddings** to capture the *meaning* of text, enabling more accurate and context-aware matching.

---

## 🎯 Problem Statement

In platforms like **KeaBuilder**, users generate leads and inputs through forms and automation workflows.

To improve:

* Lead matching
* Recommendation systems
* Automation workflows

We need a system that can:

> Identify the most similar input based on semantic meaning.

---

## ⚙️ Approach

### 1. Embedding Generation

* Used **Sentence Transformers (`all-MiniLM-L6-v2`)**
* Converts text into dense vector representations

### 2. Similarity Computation

* Used **Cosine Similarity**
* Measures closeness between query and input vectors

### 3. Retrieval

* Returns:

  * Best match (Top-1)
  * Top-K matches (optional)

---

## 🚀 Features

* ✅ Semantic similarity (context-aware matching)
* ✅ Top-K matching for recommendations
* ✅ Batch query processing
* ✅ Cached embeddings for performance optimization
* ✅ API-ready design for backend integration

---

## 🧠 Example

**Input Query:**

```text
"I want more leads for my business"
```

**Output:**

```text
"I need help generating leads"
```

---

## 📸 Demo

> Below are real outputs from the system demonstrating similarity matching and scalability features.

### 🔍 Best Match Output

![Best Match]([assets/demo.png](https://github.com/Dhruvsharma132/kea-ml-similarity-system/blob/main/demo.png?raw=true))

---

### ⭐ Top-K Matching

![Top K Results](assets/topk.png)

---

### 🚀 Batch Processing

![Batch Results](assets/batch.png)

---

### ⚡ Optimized (Cached Embeddings)

![Optimized Output](assets/optimized.png)

---

## 🏗️ System Architecture

```text
Frontend (KeaBuilder UI)
        ↓
Node.js Backend
        ↓
ML Service (Python - FastAPI)
        ↓
Embedding Model (Sentence Transformer)
        ↓
Similarity Computation
        ↓
Best Match Response
```

---

## 🛠️ Tech Stack

* **Python**
* **Sentence Transformers**
* **Scikit-learn**
* **NumPy**

---

## ▶️ How to Run

### 1. Clone Repository

```bash
git clone https://github.com/Dhruvsharma132/kea-ml-similarity-system.git
cd kea-ml-similarity-system
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Run Notebook

```bash
jupyter notebook
```

---

## 📦 Core Function

```python
def similarity_search(query, inputs, cached_embeddings=None):
    query_embedding = model.encode([query])
    scores = cosine_similarity(query_embedding, cached_embeddings)[0]

    best_index = np.argmax(scores)

    return {
        "query": query,
        "best_match": inputs[best_index],
        "score": float(scores[best_index])
    }
```

---

## ⚡ Performance Optimization

* Precomputed embeddings reduce repeated computation
* Improves response latency
* Enables efficient real-time matching

---

## ⚠️ Challenges & Considerations

* Latency of embedding generation
* Scaling similarity search for large datasets
* Handling noisy or incomplete inputs
* Need for vector search systems

---

## 📊 Evaluation

* Cosine similarity used for ranking
* Manual validation confirms semantic accuracy
* Can be extended with:

  * Similarity thresholds
  * Precision/Recall metrics

---

## 🚀 Production Integration

This system is designed to be **API-ready** and can be integrated into KeaBuilder as:

* A **Python microservice (FastAPI)**
* Called by **Node.js backend via REST API**

Use cases:

* Lead matching
* Prompt similarity
* Template recommendations

---

## 🔮 Future Improvements

* 🔹 Vector database integration (**FAISS / Pinecone**)
* 🔹 FastAPI deployment
* 🔹 Redis caching
* 🔹 Real-time similarity search
* 🔹 Multilingual support
* 🔹 Domain-specific fine-tuning

---

## 👨‍💻 Author

**Dhruv Sharma**
AI / ML Engineer | Data Scientist

---
