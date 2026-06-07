# Resume Tailor — Project Context

> This file is the persistent memory for this project.
> At the start of every new conversation, read this file before doing anything else.
> Last updated: 2026-06-07

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

## Human + AI Crew Workflow

The project owner is the CEO / final decision maker. Codex acts as Fred, the Chief Architect.

Default collaboration flow:

1. Discuss first when the owner is exploring ideas.
2. Only write project files when the owner agrees that an idea should enter the project.
3. After each file change, Fred reports which files were added or modified.
4. Important working-session outputs should be committed to Git after owner approval.
5. Git commits are the backup checkpoints; GitHub pushes are the remote backup checkpoints.

The manual + semi-automated agent team is defined in `AI_CREW.md`.

Current objectives, task breakdown, and decision status are tracked in `PROJECT_PLAN.md`.

Architecture lessons adapted from reference projects are tracked in `ARCHITECTURE_LEARNED_FROM_REFERENCE.md`.

---

## Tech Stack & Roadmap

### Phase 1 — Current: Validate core workflow locally with lightweight UI
- Language: Python
- Goal: validate the core workflow end-to-end through a lightweight local Streamlit UI: resume intake → STAR evidence cards → missing-information prompts → JD evidence map → traceable rewrite suggestions
- The UI is for workflow validation, not polish, deployment, or production-grade design
- Learn basic Git along the way; push all code to GitHub from day one

### Phase 2 — Polish and deploy the Streamlit UI
- Improve the Streamlit interface after the Phase 1 workflow is validated
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
- [x] Manual + semi-automated AI crew workflow defined in `AI_CREW.md`
- [x] Phase 1 direction updated to lightweight local Streamlit UI-first
- [ ] Phase 1: lightweight UI validates the core workflow

---

## Open Questions / Next Steps

1. Ask Charlie to define minimum STAR evidence-card standards and evidence states
2. Ask Ray to review the lightweight UI workflow for false confidence and overclaiming risk
3. Fred translates the approved workflow into Kent-ready engineering tasks
4. Kent builds the Streamlit project skeleton from Fred's bounded task brief

---

## Notes for AI Assistants

- Read this file at the start of every new conversation, then pick up from current status
- For current goals and tasks, read `PROJECT_PLAN.md` after this file
- For workflow, architecture, handoff, or agent-design questions, read `ARCHITECTURE_LEARNED_FROM_REFERENCE.md`
- After each working session, remind the user to update **Current Status** and **Open Questions / Next Steps**
- The owner is a beginner with GitHub but has basic Python scripting experience — keep explanations clear and practical
- Code examples in Python; keep them simple and readable
- Primary working language with the owner is **Chinese**; this file is in English for public visibility
- A `REFERENCES.md` file exists in this repo with external projects worth studying. Fetch and read it when the user refers to any of those projects by name (e.g. "Li Xiaolai's project", "李笑来", "no-one-did-it").
