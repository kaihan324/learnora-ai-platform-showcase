# Architecture

```mermaid
flowchart LR
  U[Telegram User] --> B[Learnora Bot]
  B --> R[AI Router]
  R --> OR[OpenRouter]
  R --> GR[Groq]
  B --> W[Web Intelligence]
  B --> D[Document RAG]
  B --> M[Semantic Memory]
  B --> MM[Voice / OCR / Vision]
  B --> Q[Durable Jobs]
  D --> DB[(PostgreSQL + pgvector)]
  M --> DB
  Q --> DB
  B --> O[Telemetry]
  O --> P[Prometheus]
  P --> G[Grafana]
```

## Design goals

1. Keep user-facing UX simple.
2. Keep provider failure from causing excessive tail latency.
3. Preserve lexical retrieval if vector infrastructure is unavailable.
4. Separate short-term conversation context from long-term semantic memory.
5. Keep long-running work outside the critical request path when possible.
6. Make production health observable.