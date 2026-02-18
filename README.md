# Cybersecurity-Incident-Response-Assistant-Chatbot
This is an implementation of the project on Enterprise Cybersecurity Incident Response Assistant Chatbot.

## Objective: A Hybrid Search RAG-based Cyber Threat Investigation Assistant that retrieves relevant security documents and generates grounded responses.

## Architecture:

User Query
   ↓
Data Preprocessing(Semantic Chunking via segmenting main, affected and description sections, text cleaning such as normalizing white spaces)
   ↓
Hybrid Retrieval Layer
   ├── BM25 (Lexical Search)
   ├── Dense Vector Search (Embeddings)
   └── Score Fusion (Reciprocal Rank Fusion)
   ↓
Top-K Relevant Context(Generated via combination of exact ID matching and hybrid search mechanism)
   ↓
RAG Generator (HuggingFace LLM)
   ↓
Grounded Response (Generated Answer)

## Evaluation:
1. Retrieval Evaulation: Precision@k, Recall@k and Hit@top_k.
2. Faithfulness Metric: Context Overlap Score (Via Embedding matching between context and Generated Answer)

## Scope of Improvements:
1. A more sophisiticated embedding model can be used that will help to capture the semantics of the text much more efficiently.
2. Caching can be used to cache repeated queries.
3. To save memory, techniques like quantization and gradient accumulation can be used.


