# Resume Tailor Product Vision

> Drafted from Yonghao product discovery with the owner.
> This document records product direction, not final implementation scope.
> Last updated: 2026-06-07

---

## Product Soul

Resume Tailor is not a tool that invents a better-looking candidate.

It helps users rediscover under-recognized strengths from their real experience, structure those experiences as STAR evidence, and match them honestly to target opportunities.

The killer experience is not simply generating a resume. The killer experience is the moment when the user realizes:

> I have real evidence. I have done valuable things. I may actually be qualified for this opportunity.

---

## Product Identity

Resume Tailor should feel more like a career coach than a resume factory.

It should help users:

- discover real strengths from messy career material;
- build confidence from evidence;
- understand how one experience can support different ability angles;
- tailor expression to a JD without changing facts;
- balance personal style, hiring-manager expectations, and ATS / AI keyword coverage.

---

## Core Experience Hypothesis

The first magical experience should happen after the user uploads an existing resume.

Instead of immediately generating a new resume, the product should analyze the original resume and reveal hidden STAR fragments:

- which parts contain Situation;
- which parts contain Task;
- which parts contain Action;
- which parts contain Result;
- which parts are vague or unsupported;
- which experiences may contain underused strengths.

A future UI could visually mark these directly on the original resume using color, annotation, or animation. The user can click into a marked section and continue a focused conversation with Tailor to fill missing details.

---

## STAR Evidence Cards

The product should gradually convert raw career material into STAR-based evidence cards.

Each card should include:

- a highlight title: what strength this experience proves;
- STAR structure;
- source material reference;
- missing information;
- ability angles when supported by evidence;
- possible JD keywords or role expectations it can support.

The card should not force every experience into many ability labels. Some stories may support one strong angle; others may support several.

The core principle is:

> Same facts, different honest angles.

---

## Tailoring Principle

Resume tailoring should not mean changing who the candidate is.

It should mean selecting and emphasizing the most relevant true evidence for a target opportunity.

The product should balance:

- the user's personal style;
- hiring manager expectations;
- ATS / AI keyword coverage;
- fidelity to the source experience.

Keywords should be covered only when connected to real STAR evidence. Unsupported keywords should be marked as missing evidence rather than inserted into the resume.

---

## Human + AI Division

AI should do the first-pass extraction and pattern recognition.

The user should confirm, correct, and supplement:

- facts;
- personal contribution;
- scope;
- measurable result;
- missing context;
- whether a proposed angle feels true.

Follow-up questions should be asked one at a time, focusing on the most important vague or underdeveloped part of the current evidence.

---

## Agent Boundaries

Yonghao owns:

- product imagination;
- user experience;
- product storytelling;
- scope discipline;
- confidence-building experience design.

Charlie owns:

- whether evidence truly supports a claim;
- STAR completeness;
- JD fit;
- resume credibility;
- whether the candidate can reasonably present a strength.

Ray owns:

- overclaiming risk;
- false confidence risk;
- fabrication and exaggeration checks;
- overfitting to JD.

Fred owns:

- deciding where product vision belongs;
- translating approved ideas into project structure, requirements, code, and tests.

---

## Open Product Questions

1. What should the first STAR evidence card look like?
2. What initial ability dimensions should be used before Charlie helps refine the taxonomy?
3. How should visual STAR annotation work in a future UI?
4. How should the system distinguish verified evidence, reasonable inference, missing evidence, and unsupported claim?
5. How should keyword coverage be scored without encouraging keyword stuffing?

---

## Implementation Boundary

This vision does not change the current Phase 1 constraint: validate the core logic locally before building polished UI, accounts, deployment, or agent-framework automation.

