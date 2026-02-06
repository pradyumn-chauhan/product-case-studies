# AI-powered Compliance Checker using RAG (FDCPA & Reg F)

## Overview
In highly regulated domains like debt collections, ensuring that product ideas, communication flows, and operational changes comply with **FDCPA** and **Regulation F** is critical — but often slow, manual, and dependent on legal reviews.

This project demonstrates how a **Retrieval-Augmented Generation (RAG)** system can be used to make compliance guidance **accessible, explainable, and fast**, without replacing legal judgment.

The system allows users to check whether a proposed idea or communication aligns with regulatory requirements by grounding AI responses directly in official compliance documents.

---

## Problem Statement
Compliance validation in collections typically suffers from:
- Manual interpretation of lengthy regulatory documents
- High dependency on legal teams for early-stage ideas
- Slow feedback loops for product and operations teams
- Risk of non-compliant messaging or workflows reaching customers

Teams needed a way to:
- Quickly sanity-check ideas for compliance
- Understand *why* something may be non-compliant
- Reference the exact regulatory clauses involved

---

## Solution
Built a **RAG-based compliance assistant** that:
- Ingests official **FDCPA** and **Reg F** documentation
- Indexes content using embeddings
- Retrieves relevant regulatory passages
- Uses an LLM to generate responses **strictly grounded in retrieved sources**

The system does **not** hallucinate compliance advice and always cites the source sections used for reasoning.

---

## High-level Architecture
1. **Document ingestion**
   - FDCPA text
   - CFPB Regulation F guidance
   - Interpretive FAQs and official commentary

2. **Chunking & embeddings**
   - Documents split into semantically meaningful chunks
   - Embeddings generated using OpenAI models

3. **Vector database**
   - Embedded chunks stored in a vector store
   - Enables semantic retrieval based on user queries

4. **RAG pipeline**
   - User inputs an idea or question
   - Relevant regulatory chunks are retrieved
   - LLM generates a response using *only* retrieved content

---

## Example Use Cases
- “Is this SMS reminder compliant if sent after 9 PM?”
- “Can we include payment incentives in a collection email?”
- “Does this workflow violate any Reg F communication frequency rules?”
- “Which FDCPA sections apply to this proposed product change?”

---

## Key Design Decisions
- **Retrieval-first approach** to prevent hallucinations
- Clear separation between:
  - regulatory text
  - AI reasoning layer
- Responses include:
  - compliance status (likely compliant / risk / needs review)
  - referenced regulation sections
- Positioned as a **decision-support tool**, not a legal replacement

---

## Impact & Value
- Faster compliance feedback during ideation
- Reduced back-and-forth with legal teams for early drafts
- Improved compliance awareness across product & operations
- Lower risk of non-compliant changes reaching production

---

## Limitations & Guardrails
- Not a substitute for legal review
- Accuracy depends on document completeness
- Designed for guidance, not final approval
- Regular updates required as regulations evolve

---

## Why this project matters
This project demonstrates how **AI + retrieval systems** can be responsibly applied in **regulated environments**, balancing speed, accuracy, and governance — a critical requirement for enterprise AI products.

---

## My Role
- Defined the product problem and compliance use cases
- Designed RAG architecture and guardrails
- Structured document ingestion and retrieval strategy
- Framed AI output to support explainability and trust