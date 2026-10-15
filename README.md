# CIVIX — AI-Assisted Permit Review Platform

### Hybrid RAG | Agentic AI | Evidence-Grounded Reasoning | AI Evaluation

**An applied AI engineering portfolio project demonstrating the architecture and implementation of an evidence-grounded, multi-agent platform for construction permit pre-review.**

**Live Demo:** https://civix-collin-county-demo.vercel.app

**Developer:** Daniel Jeong, Ph.D.  
**Organization:** Covenant AI Solutions LLC  
**Role:** AI Solution Architect & Lead Developer

---

## 1. Project Overview

CIVIX is an AI-assisted construction permit pre-review platform designed to help identify missing documentation, retrieve relevant regulatory evidence, and support preliminary compliance analysis.

Construction permit review involves complex technical drawings, jurisdiction-specific requirements, application documents, and building codes.

Traditional manual review can be time-consuming and difficult to standardize.

CIVIX explores how Hybrid Retrieval-Augmented Generation (RAG), specialized AI agents, and evidence validation can support more consistent and traceable pre-submission reviews.

The platform assists human reviewers rather than replacing licensed design professionals or government permitting authorities.

## 2. System Architecture

CIVIX combines a full-stack web application with retrieval and agent-based AI services.

**Technology Stack**

| Layer | Technologies |
|---|---|
| Frontend | Next.js, React, TypeScript |
| Backend | Python, FastAPI |
| Database | PostgreSQL, Supabase |
| Vector Retrieval | pgvector |
| Keyword Retrieval | BM25 |
| AI Architecture | Hybrid RAG, Specialized AI Agents |
| Evaluation | Groundedness Checks, Evidence Validation, Quality Gates |
| Deployment | Vercel, Cloud-Hosted Backend Services |

**High-Level Processing Flow**

1. User uploads permit-related project documents.
2. The system extracts and organizes relevant document content.
3. Hybrid RAG retrieves supporting project and jurisdiction information.
4. Specialized agents perform evidence retrieval, preliminary compliance analysis, and design-change assessment.
5. Validation logic checks evidence support and report quality.
6. The application presents traceable findings and recommended follow-up actions.

## 3. Hybrid RAG Implementation

CIVIX uses a combination of semantic vector retrieval and keyword-based retrieval.

**Why Hybrid RAG?**

Vector similarity is useful for finding semantically related information, but exact terminology, regulatory references, drawing identifiers, and numerical requirements may require lexical matching.

CIVIX combines:

- **Semantic Search:** Retrieves conceptually relevant document passages using vector embeddings.
- **BM25 Keyword Search:** Supports retrieval of exact technical terminology and references.
- **Evidence Retrieval:** Identifies supporting document excerpts for downstream analysis.
- **Context Grounding:** Connects generated findings to available source evidence.

This architecture is designed to improve retrieval reliability for technical and regulatory documents.

## 4. Agentic AI Workflows

CIVIX separates responsibilities across specialized AI components.

### Evidence Agent

Identifies relevant supporting information from uploaded documents and jurisdiction reference materials.

Responsibilities include evidence retrieval, source association, and identification of missing supporting information.

### Compliance Agent

Evaluates available evidence against selected regulatory requirements within the supported review scope.

The agent can return an `INSUFFICIENT_EVIDENCE` status when supporting information is incomplete.

This avoids treating missing information as proof of compliance.

### Design Change Agent

Supports analysis of potential impacts associated with documented design changes.

It can use retrieved evidence and drawing references to identify areas requiring additional review.

### Quality Validation

The workflow incorporates evidence and output validation before findings are presented.

Agent outputs are subject to defined quality checks rather than being treated as automatically authoritative.

## 5. AI Evaluation and Hallucination Mitigation

A central engineering concern in CIVIX is ensuring that generated conclusions remain traceable to supporting evidence.

The platform incorporates:

- Evidence-grounded response validation
- Source-reference checking
- Groundedness evaluation
- Report-format validation
- Explicit handling of insufficient evidence
- Separation of evidence quality from regulatory conclusions

**Important distinction:**

A `Quality PASS` indicates that the output has satisfied the applicable evidence and formatting checks.

It does not mean that the construction project complies with all building codes or that a permit will be approved.

## 6. Applied Use Case — Lake Dallas Commercial Renovation

CIVIX has been exercised using commercial renovation documentation associated with a Lake Dallas, Texas, project.

The demonstration includes:

- Project document ingestion
- Building permit application evidence review
- Retrieval of jurisdiction reference documents
- Preliminary compliance findings
- Drawing-reference-based design-change analysis
- Evidence-grounded reporting

The implementation demonstrates how agentic workflows can assist with document-intensive, regulation-sensitive business processes.

## 7. Engineering Challenges and Design Decisions

**Challenge 1: Semantic Similarity vs. Exact Technical References**

Technical permitting documents contain identifiers and terminology that may not be reliably retrieved through semantic search alone.

**Approach:** Combine BM25 keyword retrieval with vector similarity search.

**Challenge 2: Unsupported AI Conclusions**

Generative models can produce plausible statements without sufficient underlying evidence.

**Approach:** Introduce evidence validation, groundedness checks, and explicit insufficient-evidence outcomes.

**Challenge 3: Multi-Step Review Complexity**

A single LLM request is not an ideal architecture for managing distinct evidence, compliance, and design-change responsibilities.

**Approach:** Organize the review into specialized agent workflows with defined responsibilities.

**Challenge 4: Responsible AI in Regulatory Applications**

AI-generated findings must not be confused with official regulatory decisions.

**Approach:** Clearly separate technical evidence review, AI output quality, and authoritative permit approval.

## 8. Live Demonstration

**CIVIX Demo:**  
https://civix-collin-county-demo.vercel.app

The demonstration provides an example of AI-assisted pre-permit document review workflows.

Demo functionality and supported review scope may evolve as the platform develops.

## 9. Key AI Engineering Competencies Demonstrated

This project showcases applied experience in:

- Generative AI application architecture
- Retrieval-Augmented Generation (RAG)
- Hybrid semantic and keyword retrieval
- Multi-agent workflow design
- Python backend and REST API integration
- Full-stack AI application development
- Evidence-grounded LLM reasoning
- AI output evaluation and quality gates
- Technical document intelligence
- Human-in-the-loop decision support

## 10. Source Code and Intellectual Property

CIVIX is an independently developed commercial AI platform associated with Covenant AI Solutions LLC.

The production repository is maintained privately to protect proprietary implementation details, configurations, and commercial intellectual property.

This public repository is provided for professional portfolio review and technical discussion.

It documents the system's architecture, engineering decisions, and demonstrated capabilities without exposing proprietary production source code.

---

**Daniel Jeong, Ph.D.**  
AI / Machine Learning Engineer | Generative AI | Agentic AI | RAG Systems

**LinkedIn:** https://www.linkedin.com/in/daniel-jeong-ph-d-51b13714/
