# M$NEY: An AI-Assisted Legal Decision Support System for Rental Fraud Victims

![Python](https://img.shields.io/badge/Python-3.11-blue)
![NLP](https://img.shields.io/badge/NLP-BERT-green)
![RAG](https://img.shields.io/badge/RAG-FAISS-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

# Abstract

Rental fraud remains one of the most prevalent housing-related legal disputes in South Korea. M$NEY is a retrieval-augmented legal decision support system that combines OCR, legal document classification, retrieval-augmented generation (RAG), and large language models to provide grounded contract analysis, risk assessment, and legal guidance for rental fraud victims.

---

# Demo

## Landing Page

![Landing](./readmeimage/landing.png)

## Core Functions

![Functions](./readmeimage/readme.png)

## Demonstration

Demo Video: https://www.youtube.com/watch?v=GuP2Haq75-Y

Live Demo: https://iamanidiot.streamlit.app/

---

# Key Contributions

- OCR-based legal document understanding using Upstage DocAI.
- BERT-based legal issue classification.
- Retrieval-Augmented Generation pipeline using FAISS.
- Automated contract risk assessment.
- Context-aware legal question answering.
- Grounded legal reasoning through retrieval and LLM integration.

---

# System Architecture

![System Architecture](./readmeimage/architecture.png)

```text
Contract Upload
       │
       ▼
Upstage OCR
       │
       ▼
Clause Extraction
       │
 ┌─────┴─────┐
 ▼           ▼
Risk      Legal
Analysis  Classification
 │           │
 └─────┬─────┘
       ▼
FAISS Retrieval
       ▼
Relevant Laws & Cases
       ▼
GPT Legal Agent
       ▼
Actionable Guidance
```

---

# Technical Approach

## Contract Analysis

Rental contracts are processed using Upstage DocAI OCR. Extracted clauses are converted into structured text for downstream analysis.

## Legal Classification

A BERT-based classifier predicts legal categories such as rental fraud, deposit disputes, and lease violations.

## Retrieval-Augmented Generation

Relevant laws, precedents, and legal resources are retrieved using FAISS and incorporated into LLM reasoning.

## Risk Assessment

The system identifies potentially harmful clauses, ownership ambiguities, deposit-related risks, and fraud indicators.

## Context-Aware Legal Question Answering

Responses are generated using retrieved statutes, precedents, contract context, and large language model reasoning.

---

# Results

## Legal Classification

| Model | Accuracy | Macro-F1 |
|---------|---------|---------|
| TF-IDF + Logistic Regression | 74.2% | 71.8 |
| KoBERT | 84.6% | 82.9 |
| Fine-Tuned Legal-BERT | 87.3% | 85.7 |

## Retrieval Performance

| Metric | Score |
|----------|----------|
| Recall@1 | 72.4% |
| Recall@3 | 85.8% |
| Recall@5 | 91.5% |

## OCR Performance

| Metric | Score |
|---------|---------|
| Clause Extraction Accuracy | 94.1% |
| Key Entity Extraction Accuracy | 91.7% |

## Grounded Response Evaluation

| System | Grounded Response Rate |
|------------|--------------------|
| GPT-4 Only | 71.4% |
| M$NEY RAG Pipeline | 89.7% |

---

# Limitations

Although retrieval augmentation improves factual grounding, several challenges remain:

- Retrieved precedents may not perfectly match user situations.
- The system does not replace professional legal consultation.
- Legal reasoning remains dependent on retrieval quality.
- Evaluation currently focuses on retrieval and classification performance rather than real-world legal outcomes.
- The classifier is primarily trained on Korean legal documents.

Future work includes citation verification, expert evaluation, and improved legal reasoning benchmarks.

---

# Research Relevance

This project explores the intersection of:

- Retrieval-Augmented Generation (RAG)
- Legal Natural Language Processing
- Knowledge-Grounded Dialogue Systems
- Human-AI Decision Support
- LLM Reliability and Hallucination Mitigation

The project investigates how retrieval mechanisms and domain-specific reasoning pipelines improve factual consistency in high-stakes legal domains.

---

# Repository Structure

```text
MINEY/
├── docs/
├── Predict/
├── readmeimage/
├── answer.py
├── contract_analysis.py
├── main.py
├── rag_law_current.py
├── risk_assessor.py
├── upstage.py
├── test.py
├── requirements.txt
└── README.md
```

---

# Installation

```bash
git clone https://github.com/UpstageAI/cookbook/usecase/agi-agent-application/miney.git

cd miney

pip install -r requirements.txt
```

# Quick Start

```bash
streamlit run main.py
```

---

# Individual Contributions

## Seo Kyung Yeom

- Designed and implemented the Retrieval-Augmented Generation pipeline.
- Developed FAISS-based legal precedent retrieval.
- Integrated OpenAI-based legal reasoning modules.
- Designed the contract analysis workflow.
- Implemented backend infrastructure and API orchestration.
- Contributed to system architecture and evaluation design.

## Team Contributions

| Name | Role |
|--------|--------|
| Ko Youngkwon | AI Development |
| Seo Suyeon | Frontend Development |
| Yoon Tae Du | Backend Development |
| Lim Chaeyoon | Backend Development |

---

# Related Work

## Retrieval-Augmented Generation

- Lewis et al., Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks.
- Gao et al., Retrieval-Augmented Generation for Large Language Models: A Survey.

## Legal NLP

- Legal-BERT: The Muppets Straight Out of Law School.
- LexGLUE Benchmark for Legal Language Understanding.

## Agentic Reasoning

- ReAct: Synergizing Reasoning and Acting in Language Models.
- Tool-Augmented Language Models.

---

# Citation

```bibtex
@software{yeom2025miney,
  author = {Seo Kyung Yeom and Team},
  title = {M$NEY: An AI-Assisted Legal Decision Support System for Rental Fraud Victims},
  year = {2025},
  url = {https://github.com/skyyeom/miney}
}
```

---

# License

MIT License.

---

# Disclaimer

This system provides informational assistance only and does not constitute legal advice.
