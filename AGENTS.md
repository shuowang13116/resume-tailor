# Resume Tailor — Project Context

> This file is the persistent memory for this project.
> At the start of every new conversation, read this file before doing anything else.
> Last updated: 2026-06-05

---

## What This Project Does

An AI-powered tool that helps users craft a tailored resume for each job application.
The core idea: build a personal library of STAR stories first, then intelligently select and rewrite content to match a given JD — never fabricate.

---

## Target Users

Job seekers. Initially built for personal use, with the goal of turning it into a product for others.

---

## Feature Modules

### Layer 1 — STAR Story Library

All user experiences are stored as structured STAR entries (Situation / Task / Action / Result).

**Intake method 1: Import existing resume**
- User uploads a resume (PDF or Word)
- AI extracts STAR fragments and structures them
- Incomplete entries are flagged (e.g. missing quantified Result) and the user is prompted to fill them in

**Intake method 2: Conversational extraction**
- AI asks targeted follow-up questions to surface more experiences
- e.g. "How large was your team?" / "Is there a number that captures the outcome?"
- Answers are automatically organized into STAR entries and saved to the library

**Library management**
- Each STAR entry supports tags, categories, and relevance scores
- Full CRUD — add, edit, delete, search at any time

---

### Layer 2 — JD Analysis

Given a job description:
- Extract core competencies, must-haves vs. nice-to-haves, and cultural keywords
- Score each STAR entry in the library for relevance to this JD
- Return a ranked list of recommended entries

---

### Layer 3 — Resume Generation

- Select the highest-scoring STAR entries for the target role
- Rewrite phrasing to align with JD language — facts stay unchanged
- User can diff before/after, roll back, or edit manually
- Export to PDF or Word

---

## Core Design Principle: Avoiding Overfitting

This is the central challenge. Every design decision should account for it.

- Rewrites must be grounded in what actually happened — no fabrication, no exaggeration
- Matching a JD means choosing the right stories and adjusting emphasis, not inventing new ones
- Generated output shows two scores: **Fidelity** (how true to the original) and **Relevance** (how well it fits the JD) — the user decides the trade-off
- A "base resume" is always preserved as a reference so the user can see exactly what changed

---

## Tech Stack & Roadmap

### Phase 1 — Current: Validate core logic locally
- Language: Python
- Goal: get the pipeline working end-to-end: upload resume → extract STAR entries → rewrite based on JD
- No UI needed yet; command line is fine
- Learn basic Git along the way; push all code to GitHub from day one

### Phase 2 — Add a Streamlit UI
- Wrap the scripts in a Streamlit web interface
- Deploy to Streamlit Cloud (free, connects directly to GitHub; auto-deploys on push)
- Produces a shareable URL

### Phase 3 — Introduce an Agent framework
- Refactor single-step scripts into a multi-step LangChain Agent
- Agent autonomously decides: is this STAR entry complete? → ask follow-up? → run multi-turn dialogue → generate resume

### Phase 4 — Productize
- Replace Streamlit with React frontend + FastAPI backend
- Add user accounts, persistent STAR library storage, etc.

### Stack reference

| Layer | Tech | Notes |
|---|---|---|
| Agent framework | LangChain | Multi-step LLM orchestration |
| UI (early stage) | Streamlit | Web UI in pure Python |
| LLM | Claude API or OpenAI | The agent's brain |
| Resume parsing | python-docx / pdfplumber | Read uploaded files |
| Storage (early stage) | JSON or SQLite | STAR library persistence |
| Code hosting | GitHub | Version control + deploy trigger |
| Deployment | Streamlit Cloud | Free, GitHub-connected |

---

## Current Status

- [x] Project concept defined
- [x] Tech stack and phased roadmap decided
- [x] AGENTS.md created and pushed to GitHub
- [x] GitHub repo created
- [ ] Phase 1: local script validates the core pipeline

---

## Open Questions / Next Steps

1. Create the GitHub repo (`resume-tailor`) and push this file
2. Set up the Python project skeleton
3. Build the first feature: parse an uploaded resume and extract STAR entries

---

## Notes for AI Assistants

- Read this file at the start of every new conversation, then pick up from current status
- After each working session, remind the user to update **Current Status** and **Open Questions / Next Steps**
- The owner is a beginner with GitHub but has basic Python scripting experience — keep explanations clear and practical
- Code examples in Python; keep them simple and readable
- Primary working language with the owner is **Chinese**; this file is in English for public visibility
- A `REFERENCES.md` file exists in this repo with external projects worth studying. Fetch and read it when the user refers to any of those projects by name (e.g. "Li Xiaolai's project", "李笑来", "no-one-did-it").
