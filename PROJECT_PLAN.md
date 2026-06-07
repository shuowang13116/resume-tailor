# Resume Tailor Project Plan

> This file is the project progress source of truth.
> Agents should read this file after `AGENTS.md` and `AI_CREW.md` when they need current goals, scope, tasks, or priorities.
> For product direction, read `PRODUCT_VISION.md`.
> For workflow and architecture lessons from reference projects, read `ARCHITECTURE_LEARNED_FROM_REFERENCE.md`.
> Last updated: 2026-06-07

---

## Current Phase

Phase 1: Validate the core logic locally.

The project is not building a polished product yet. The goal is to validate the core workflow locally through a lightweight Streamlit UI before adding accounts, deployment, persistent database, export polish, or agent frameworks.

---

## Current Objective

Define and validate the Phase 1 lightweight UI MVP:

1. Intake resume material through paste or simple upload.
2. Extract or organize that material into STAR evidence cards.
3. Mark missing information and evidence status.
4. Intake a target job description.
5. Map JD keywords or requirements to real STAR evidence.
6. Generate traceable resume bullet suggestions that improve relevance without inventing facts.
7. Let the user confirm, edit, or supplement the evidence.

Long-term product direction is recorded in `PRODUCT_VISION.md`. It should guide product judgment without expanding Phase 1 implementation scope.

---

## Current Success Criteria

Phase 1 is successful when the project can demonstrate this local workflow:

1. Input resume material in a lightweight Streamlit UI.
2. Show STAR evidence cards with source fragments, STAR fields, missing fields, ability angles when supported, and evidence status.
3. Let the user confirm, edit, or supplement evidence details.
4. Input a target JD.
5. Show a JD evidence map: supported, partially supported, missing evidence, or should not use.
6. Produce a small set of rewritten resume bullets.
7. Show each bullet's source STAR card, JD requirement, fidelity note, relevance note, and warning when evidence is weak.

---

## Current Non-Goals

Do not build these yet:

- Full web app.
- User accounts.
- Database-backed persistence.
- PDF or Word export polish.
- LangChain or other agent framework automation.
- Complex prompt chains before the MVP workflow is clear.
- Any feature that encourages fabricated resume facts.
- Polished visual resume annotation, graph views, animation, or production-grade design.

---

## Immediate Workstream

Before writing code, review the Phase 1 lightweight UI MVP with Charlie and Ray, then let Fred translate the approved workflow into Kent-ready engineering tasks.

Current task:

1. Ask Charlie to define minimum STAR evidence-card standards and evidence states.
2. Ask Ray to review the lightweight UI workflow for false confidence, unsupported claims, and overclaiming risk.
3. Bring Charlie and Ray outputs back to Fred.
4. Fred translates the approved MVP into engineering tasks.
5. Kent starts the Streamlit project skeleton only after Fred provides a bounded task brief.

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
| Done | Capture early product vision | Owner + Yonghao + Fred | Recorded in `PRODUCT_VISION.md` |
| Done | Add Kent - Implementation Engineer | Owner + Yonghao + Xiaolai + Fred | Directly added because manual agent cost is low and boundaries are clear |
| Done | Establish Kent working mode | Owner + Kent + Fred | Kent waits for Fred task briefs and does not own product, architecture, memory, risk, or Git |
| Done | Define Yonghao / Fred / Kent collaboration boundary | Owner + Yonghao + Fred | Product intent flows through Fred before Kent implementation |
| Done | Define Phase 1 lightweight UI MVP workflow | Owner + Yonghao + Fred | Streamlit local UI is required to validate the core workflow |
| Pending | Define evidence-card standards | Charlie | Minimum evidence, ability dimensions, evidence states |
| Pending | Review lightweight UI MVP risks | Ray | False confidence, unsupported claims, keyword stuffing, UI authority risk |
| Pending | Translate MVP into engineering tasks | Fred | Create implementation plan |
| Pending | Build Streamlit project skeleton | Kent | Only after Fred provides bounded engineering task brief |

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
| 2026-06-07 | Create `PRODUCT_VISION.md` for product direction | Keeps product soul and long-term experience hypotheses separate from current task planning |
| 2026-06-07 | Add Kent directly as Implementation Engineer | Owner decided manual agents are cheap enough to add when boundaries are clear; Kent owns implementation from Fred briefs, not product, architecture, memory, risk, or Git ownership |
| 2026-06-07 | Define product-to-implementation chain | Yonghao owns product architecture, Fred owns system architecture and source-of-truth, Kent implements from Fred's bounded engineering briefs |
| 2026-06-07 | Make Phase 1 lightweight UI-first with Streamlit | Resume tailoring is structured, networked, multi-turn, traceable, and decision-heavy; a lightweight UI is required to validate the workflow, not polish |

---

## Agent Reading Order

For recurring project work, agents should read:

1. `AGENTS.md` for stable project memory and principles.
2. `AI_CREW.md` for role definitions and collaboration workflow.
3. `PROJECT_PLAN.md` for current objective, tasks, and decisions.
4. `PRODUCT_VISION.md` when the task involves product direction, user experience, product story, or long-term scope.
5. `ARCHITECTURE_LEARNED_FROM_REFERENCE.md` when the task involves workflow, architecture, handoff, or agent design.

---

## Prompt Rule

Do not repeat the entire project background in every prompt.

Instead, ask agents to read the three core files above, then provide only:

1. The role they should play.
2. The current task.
3. The expected output format.
4. The boundaries or non-goals.
