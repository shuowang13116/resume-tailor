# Architecture Learned From Reference

> This file records architecture lessons borrowed from reference projects.
> It should guide Resume Tailor's workflow without copying another project's content or scale.
> Last updated: 2026-06-07

---

## Reference: Li Xiaolai / no-one-did-it

Source:

- `REFERENCES.md`
- https://github.com/xiaolai/no-one-did-it
- https://github.com/xiaolai/no-one-did-it/blob/main/AGENTS.md

What matters:

`no-one-did-it` is useful because it shows a solo owner coordinating multiple AI agents through shared rules, role boundaries, evidence discipline, handoffs, and review loops. Resume Tailor should learn the operating system, not copy the book-writing content.

---

## Transferable Architecture Lessons

| Lesson from reference | Resume Tailor translation | Adopt now? |
|---|---|---|
| One shared source of truth for agents | Use `AGENTS.md`, `AI_CREW.md`, and `PROJECT_PLAN.md` as required reading | Yes |
| Explicit role boundaries | Keep Fred, Yonghao, Charlie, and Ray responsibilities non-overlapping | Yes |
| Evidence before elegance | Resume facts must be traceable to source material before wording is polished | Yes |
| Clean handoff between agents | Agent outputs should include assumptions, risks, and next owner | Yes |
| Research before writing | STAR library and JD analysis must happen before resume generation | Yes |
| Red-team review | Ray reviews high-risk decisions, especially fabrication and overfitting | Yes |
| Source ledger | Track which original resume line, user answer, or document supports each STAR entry | Soon |
| Validation tools | Add tests/schema checks once data structures exist | Soon |
| Multi-agent scale | Do not create 10+ agents before the four-agent workflow is stable | Not yet |
| Publishing pipeline | Export polish belongs after Phase 1 core logic works | Not yet |

---

## Resume Tailor Over-Rules

These are adapted from the reference project's rule-heavy workflow, but shaped for a resume product.

1. Fidelity before fluency.
   - A polished bullet is bad if it cannot be traced to real candidate material.

2. Source before rewrite.
   - Do not generate tailored resume wording until the supporting STAR source is known.

3. Handoff cleanly.
   - Every agent output should say what it assumes, what is uncertain, what risks exist, and who should act next.

4. Small pipeline before big product.
   - Validate the local core workflow before building UI, deployment, accounts, or agent automation.

5. Review before acceptance.
   - Important product, resume, or architecture decisions should pass through the agent best suited to critique them.

---

## Required Handoff Format

For non-trivial agent work, use this handoff format:

```text
Output:
1. Main recommendation
2. Evidence or source used
3. Assumptions
4. Risks
5. Open questions
6. Suggested next owner
```

This keeps agent work portable between threads and easier for Fred to integrate.

---

## Xiaolai - Workflow Reviewer

Resume Tailor may use a dedicated agent named Xiaolai to review workflow decisions against `no-one-did-it`.

This agent is not Li Xiaolai and must not impersonate him. The agent's job is narrow:

- Use public repository evidence.
- Separate facts from inference.
- Review, critique, compare, and recommend workflow changes based on the reference project's patterns.
- Recommend small improvements to source-of-truth files, role boundaries, evidence discipline, handoff, and review gates.
- Warn when we are copying too much or scaling too early.
- Never directly edit project files, stage changes, or commit. File changes are owned by Fred after owner approval.

Use this reviewer when:

- Creating or changing agents.
- Changing the handoff format.
- Adding project-memory documents.
- Expanding the crew.
- Reviewing whether Fred is applying lessons from the reference project correctly.

Do not use this reviewer for:

- Product imagination.
- Resume-quality judgment.
- Code implementation.
- Direct project file edits.
- Git staging or commits.
- Personal imitation of Li Xiaolai.

---

## Architecture Decisions Adopted

| Date | Decision | Reason |
|---|---|---|
| 2026-06-07 | Add `PROJECT_PLAN.md` as current progress source of truth | Avoids repeating current phase and task state in prompts |
| 2026-06-07 | Add this reference-learning file | Makes Fred proactively compare this project to successful reference workflows |
| 2026-06-07 | Require clean handoff format for important agent outputs | Reduces confusion when moving work between agent threads |
| 2026-06-07 | Add Xiaolai - Workflow Reviewer | Lets a dedicated agent critique workflow using `no-one-did-it` without impersonating Li Xiaolai or editing files directly |

---

## What Not To Copy

Do not copy these from the reference project yet:

- A large 10+ agent team.
- Book-specific writing pipeline.
- Heavy research card system before Resume Tailor has STAR data structures.
- Complex validators before there is code or data schema.
- Legal/publishing workflows that do not apply to Phase 1.

The right move is to adapt the discipline first, then add machinery only when the project needs it.
