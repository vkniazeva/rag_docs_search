# Multi-Agent RAG for RFP Automation

An experimental system for processing Requests for Proposals (RFPs). It will extract requirements from RFP documents, find relevant evidence in a knowledge base of historical contracts, and draft traceable responses.

The project is being built incrementally. The first milestone is document ingestion and retrieval; the full multi-agent workflow comes later.

## Project goals

- Parse PDF, DOCX, and XLSX documents into structured data.
- Build a searchable knowledge base from synthetic historical contracts.
- Retrieve relevant evidence using metadata filters and hybrid search (vector search plus BM25).
- Preserve references from retrieved evidence to its source document.
- Measure retrieval quality before expanding the system with answer generation and agent orchestration.

## Planned components

1. **Document ingestion** — parse documents, create structured contract summaries and metadata, and retain source references.
2. **Knowledge retrieval** — combine metadata filtering, vector search, BM25, and later reranking.
3. **RFP processing** — extract and classify requirements into structured data.
4. **Response generation** — draft evidence-based answers, identify gaps, assign confidence, and populate templates.
5. **Multi-agent workflow** — coordinate the parser, retrieval, and response-generation components.

## Initial technology choices

- Python
- Docling for document parsing
- PostgreSQL with pgvector for storage and vector search
- Ollama for running local language and embedding models without a hosted API
- FastAPI for a later service interface
- LangGraph for orchestration when the individual components are ready

These are starting choices and may change as experiments reveal practical constraints.

## Cost constraint

The project is designed to run without paid APIs or hosted database services. Models should run locally, and the license for each selected model must be checked before use. Local inference still uses the computer's storage and processing capacity.

## Development roadmap

- [ ] Set up the Python environment and dependencies.
- [ ] Create a small synthetic contract collection with source documents and metadata.
- [ ] Implement document ingestion and inspect the extracted structure.
- [ ] Add PostgreSQL storage and vector search.
- [ ] Add BM25 and evaluate hybrid retrieval against a small query set.
- [ ] Add reranking and compare retrieval results.
- [ ] Parse RFP requirements and generate traceable draft responses.
- [ ] Orchestrate the components with LangGraph and expose the workflow through FastAPI.

## Project notes

TBD
