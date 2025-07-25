# Agentic AI (PoC)

> 🚀 Proof-of-concept for Step S1 — Secure Usage Data Collection — from the NVIDIA paper:  
> [Small Language Models are the Future of Agentic AI](https://arxiv.org/pdf/2506.02153)

---

## 🧠 Context

Modern multi-agent systems increasingly depend on continuous instrumentation — not just for observability, but to support downstream adaptation. Usage logs are the **foundation for training specialized Small Language Models (SLMs)** that power agent capabilities like reasoning, extraction, and summarization.

This project focuses on **Step S1** from the NVIDIA pipeline: collecting and securing high-quality logs of agent interactions, tool usage, and outputs.

> 🔐 Logging is essential to enable fine-tuning SLMs via task clustering, selection, and specialization (Steps S2–S5).

📌 Architecture reference (via [Mistral.ai](https://mistral.ai/news/agents-api)):

<img src="https://github.com/mistralai/cookbook/raw/main/mistral/agents/agents_api/travel_assistant/assets/architecture.png" width="900" alt="Agentic Architecture">

---

## 🎯 Goal: Step S1 — Secure Usage Data Collection

Based on the NVIDIA paper, Step S1 includes:

- Logging of:
  - Agent prompts (non-HCI only)
  - Output completions/responses
  - Tool call inputs and outputs
  - Optional latency or timing metadata
- Storage in a secure, encrypted pipeline
- Anonymization of user or org-specific content (PII, PHI)

---

## 📦 Planned Tech Stack

| Layer             | Tools/Options                                          |
| ----------------- | ------------------------------------------------------ |
| **Language**      | Python 3.11+                                           |
| **Logging**       | `structlog` or `loguru`                                |
| **Anonymization** | `spaCy`, `Presidio`, or rule-based masking             |
| **Storage**       | JSONL, SQLite (encrypted), or S3 later                 |
| **App Layer**     | FastAPI or LLM framework (for future multi-agent demo) |

---

## 🚧 Roadmap

- [ ] Define core logging decorator
- [ ] Add anonymization middleware (rule-based or NLP)
- [ ] Secure encrypted local storage backend
- [ ] Instrument toy multi-agent app (e.g., chat + tool use)
- [ ] Collect dataset for task clustering (→ Step S3)

---

## 📚 References

- NVIDIA (2024): [Small Language Models are the Future of Agentic AI](https://arxiv.org/pdf/2506.02153)
- Mistral.ai: [Agents API Blog Post](https://mistral.ai/news/agents-api/)
