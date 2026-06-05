# Reference Projects

This file documents external projects worth studying for inspiration and lessons learned.
When a conversation references one of these projects by name, fetch and read the relevant links before responding.

---

## Li Xiaolai (李笑来) — "no-one-did-it"

**What it is:** A solo author used a team of ~10+ AI agents to research a topic deeply and write a complete book within one week.

**Why it matters to this project:** It demonstrates that a single non-technical person, working with well-orchestrated AI agents, can produce serious long-form output at speed. The workflow — deep research first, then structured writing — is directly analogous to what Resume Tailor aims to do: gather and structure raw material first (STAR library), then generate polished output (tailored resume).

**Links:**
- Repo: https://github.com/xiaolai/no-one-did-it
- AGENTS.md (how he instructs his agents): https://github.com/xiaolai/no-one-did-it/blob/main/AGENTS.md

**Open questions worth investigating:**
- How did he divide labor across agents? (researcher / writer / editor / fact-checker?)
- How did agents share context and hand off work to each other?
- How did he prevent agents from contradicting each other or going off-track?
- What does the "deep research" phase look like in practice?

**Relevance to Resume Tailor's phases:**
- His "deep research" phase → our STAR extraction + JD analysis phase
- His "structured writing" phase → our resume generation phase
- His agent orchestration approach → our future LangChain Agent architecture (Phase 3)

---

*Add more reference projects below as needed.*
