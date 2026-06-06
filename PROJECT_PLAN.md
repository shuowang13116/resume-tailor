# Resume Tailor Project Plan

> This file is the project progress source of truth.
> Agents should read this file after `AGENTS.md` and `AI_CREW.md` when they need current goals, scope, tasks, or priorities.
> For workflow and architecture lessons from reference projects, read `ARCHITECTURE_LEARNED_FROM_REFERENCE.md`.
> Last updated: 2026-06-07

---

## Current Phase

Phase 1: Validate the core logic locally.

The project is not building a polished product yet. The goal is to prove the core pipeline with simple local scripts before adding UI, accounts, deployment, or agent frameworks.

---

## Current Objective

Define and validate the Phase 1 MVP:

1. Understand the user's real resume material.
2. Extract or organize that material into STAR-style entries.
3. Analyze a target job description.
4. Match relevant STAR entries to that JD.
5. Generate resume wording that improves relevance without inventing facts.

---

## Current Success Criteria

Phase 1 is successful when the project can demonstrate this local workflow:

1. Input candidate material.
2. Input a target JD.
3. Produce structured STAR entries or STAR fragments.
4. Identify missing information and follow-up questions.
5. Rank STAR entries for JD relevance.
6. Produce a small set of rewritten resume bullets.
7. Show why each rewrite is faithful to the source material.

---

## Current Non-Goals

Do not build these yet:

- Full web app.
- Streamlit UI.
- User accounts.
- Database-backed persistence.
- PDF or Word export polish.
- LangChain or other agent framework automation.
- Complex prompt chains before the MVP workflow is clear.
- Any feature that encourages fabricated resume facts.

---

## Immediate Workstream

Before writing code, define the Phase 1 MVP with the product manager agent Yonghao.

Current task:

1. Recruit / establish Yonghao's working mode.
2. Ask Yonghao to define the Phase 1 MVP user workflow.
3. Bring Yonghao's output back to Fred.
4. Fred translates the approved MVP into engineering tasks.
5. Ray reviews high-risk workflow decisions.
6. Fred starts the Python project skeleton only after the MVP shape is approved.

---

## Task Board

| Status | Task | Owner Agent | Notes |
|---|---|---|---|
| Done | Define project concept and roadmap | Fred | Recorded in `AGENTS.md` |
| Done | Create manual AI crew workflow | Fred | Recorded in `AI_CREW.md` |
| Done | Add Brooks-inspired Fred working mode | Fred | Recorded in `AI_CREW.md` |
| Done | Add project plan source of truth | Fred | Recorded in `PROJECT_PLAN.md` |
| Done | Add reference architecture learning file | Fred | Recorded in `ARCHITECTURE_LEARNED_FROM_REFERENCE.md` |
| Done | Establish Yonghao working mode | Owner + Yonghao + Fred | Recorded in `AI_CREW.md` |
| Done | Establish Charlie working mode | Owner + Charlie + Fred | Recorded in `AI_CREW.md` |
| Done | Establish Ray working mode | Owner + Ray + Fred | Recorded in `AI_CREW.md` |
| Done | Establish Xiaolai - Workflow Reviewer boundary | Owner + Xiaolai + Fred | Xiaolai reviews and recommends; Fred owns file edits |
| Pending | Define Phase 1 MVP workflow | Yonghao | Product output returns to Fred |
| Pending | Review MVP risks | Ray | Especially fabrication and scope creep |
| Pending | Translate MVP into engineering tasks | Fred | Create implementation plan |
| Pending | Build Python project skeleton | Fred | Only after MVP approval |

---

## Decision Log

| Date | Decision | Reason |
|---|---|---|
| 2026-06-07 | Start with manual + semi-automated agent orchestration | Easier for a beginner than API/framework automation; teaches the core coordination pattern first |
| 2026-06-07 | Codex thread Fred acts as Chief Architect | Codex can read files, write code, run commands, and maintain project context |
| 2026-06-07 | Use dedicated agent threads for product, resume expertise, and review | Keeps roles focused and reduces prompt confusion |
| 2026-06-07 | Define product MVP before building Python skeleton | Avoids implementing the wrong workflow too early |
| 2026-06-07 | Create `PROJECT_PLAN.md` as the current progress source of truth | Avoids repeating current phase, goals, and tasks in every prompt |
| 2026-06-07 | Create `ARCHITECTURE_LEARNED_FROM_REFERENCE.md` | Makes reference-project learning explicit and reusable |
| 2026-06-07 | Define Xiaolai as Workflow Reviewer, not file editor | Keeps reviewer critique separate from Fred's integration and Git ownership |

---

## Agent Reading Order

For recurring project work, agents should read:

1. `AGENTS.md` for stable project memory and principles.
2. `AI_CREW.md` for role definitions and collaboration workflow.
3. `PROJECT_PLAN.md` for current objective, tasks, and decisions.
4. `ARCHITECTURE_LEARNED_FROM_REFERENCE.md` when the task involves workflow, architecture, handoff, or agent design.

---

## Prompt Rule

Do not repeat the entire project background in every prompt.

Instead, ask agents to read the three core files above, then provide only:

1. The role they should play.
2. The current task.
3. The expected output format.
4. The boundaries or non-goals.
