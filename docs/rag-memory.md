# Hybrid RAG and Semantic Memory

Learnora combines lexical retrieval and vector retrieval, then fuses and reranks the candidates before sending evidence to the model.

```text
Question
  ↓
Lexical Retrieval + Vector Retrieval
  ↓
Candidate Fusion
  ↓
Reranking
  ↓
Evidence Context
  ↓
Grounded AI Answer
```

Conversation memory keeps recent chat context. Semantic memory stores reusable non-sensitive context such as preferences, goals, and learning context.

The system can degrade to lexical retrieval when vector search is unavailable.