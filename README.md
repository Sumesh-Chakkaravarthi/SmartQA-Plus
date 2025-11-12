#  README — SmartQA+: Natural Language Question Answering API

##  Project Overview
SmartQA+ is a semantic question-answering system that answers natural-language questions based on real-world member messages retrieved from a public API.

It uses:
- **FastAPI** for building the web API.
- **SentenceTransformer (all-MiniLM-L6-v2)** for semantic similarity search.
- **RoBERTa (deepset/roberta-base-squad2)** for extracting precise answers from text.

---

##  Architecture
1. Fetch all messages via REST API (`GET /messages`).  
2. Convert each message and the user question into embeddings.  
3. Use cosine similarity to select top 3 relevant messages.  
4. Pass the combined message context to the QA model to extract the final answer.  
5. Return the answer as a JSON response.

---

##  Example Output
```json
{
  "question": "When is Layla planning her trip to London?",
  "answer": "Friday",
  "confidence": 0.87
}
