---
name: interview-prep
description: Complete job interview preparation. Use this skill whenever the user mentions an interview, a job opening, a job posting, a LinkedIn Jobs link, asks "am I a fit for this role?", wants to research a company or an interviewer, or asks for a preparation dossier. Also when they say "prepare me for the interview with X" or paste a job posting URL. Produces company and interviewer research, a fit analysis against the CV, a dossier as an artifact, recommendations, and study resources.
---

# Interview Prep

Prepares the user for a job interview end to end: inputs → research → fit → dossier → recommendations → resources. The central deliverable is a **dossier published as an artifact** that the user can review on their phone right before the interview.

Work in the user's language. Be honest in the fit analysis: an inflated verdict sets the user up to fail in the real interview. Flag gaps as clearly as strengths — the value of this skill is actionable candor.

## Step 1 — Gather inputs and read the job posting

- **Current resume:** look for it in the working directory (PDF/DOCX). Ignore files marked "OLD VERSION" or similar. If several current versions exist (different languages), use the most complete one. If there is no resume, ask for it before the fit analysis (the research steps don't need it).
- **Job posting:** if the user provides a URL, read it with WebFetch. For LinkedIn, normalize the URL to `https://www.linkedin.com/jobs/view/<jobId>` (extract the `currentJobId` if it comes in a search URL). Extract: title, company, location, seniority, responsibilities, required and desired qualifications, language requirements.
- **Missing data:** ask for the interviewer's name and the interview date if not mentioned. Don't block the flow waiting: continue and mark those sections as "pending".

## Step 2 — Research the company

Run WebSearch queries (in parallel where possible) and follow up with WebFetch on the richest sources:

1. **General profile:** founding, founders, size, offices, business model, clients, partners.
2. **Recent strategic narrative** (last 12 months): repositionings, announcements, funding, acquisitions, leadership quotes. This provides material for smart questions and for connecting the user's experience to the company's thesis.
3. **Hiring process:** Glassdoor and Indeed (`glassdoor.com/Interview/<company>`, `indeed.com/cmp/<company>/interviews`) — stages, duration, difficulty, tests (psychometric, language, technical), candidate experiences.

Log every URL consulted: they go in the dossier's sources section.

## Step 3 — Research the interviewer

- **With a name:** search their public professional profile (LinkedIn, articles, talks, GitHub). Summarize career path, current role, interests, and possible connection points with the user. Do not compile private information; public, professional sources only.
- **Without a name:** state who typically interviews at each stage based on the research (recruiter → hiring manager → leadership) and leave the dossier section as "pending — share the name and I'll update it".

## Step 4 — Fit analysis against the CV

Build a requirement-by-requirement table: each posting requirement → status (✓ meets/exceeds · ◐ partial · ✗ gap) → concrete CV evidence (project, metric, certification). From that:

- **Overall verdict:** approximate percentage and a one-line synthesis (e.g., "strong fit, with a gap in X").
- **Golden connection:** the CV story that most resonates with the company's current strategy — the story the user should open with in every conversation.
- **Gaps and how to close them:** for each ◐/✗, say how to reframe existing experience in the requirement's language, or what to prepare/study. Never suggest fabricating experience.

## Step 5 — Build the dossier as an artifact

Load the `artifact-design` skill before writing the page. Publish as a private artifact (stable favicon, e.g. 🎯; keep it across updates). Proven structure:

1. **Header:** role, company, visible fit verdict (badge), main gap, date.
2. **Company at a glance:** hard-facts grid.
3. **Strategic narrative** with a leadership quote + the "golden connection" callout.
4. **Fit map:** the step-4 table + a callout on closing the main gap.
5. **Selection process:** numbered steps (numbering reflects the real sequence) with per-stage preparation notes.
6. **Likely questions with anchors:** grouped (domain-technical, role craft, behavioral); each question states **which CV story to answer with**.
7. **Smart questions to ask:** 3–5 that demonstrate research (recent announcements, metrics, how the team works).
8. **Interviewer section** (or pending note).
9. **Linked sources.**

If the user asks to update an existing dossier (e.g., the interviewer's name arrived), edit and republish at the same URL — don't create a new artifact.

## Step 6 — Close with recommendations

In the chat (not only in the dossier), close with concrete, prioritized actions:

- Targeted CV adjustments for this posting (reorder sections, mirror the posting's vocabulary, declared language level).
- What to practice: a 2-minute pitch (in the interview's language), STAR answers for the highest-risk questions.
- Logistics: tests to reserve time for (psychometric, language), expected process duration.
- Offer the natural next steps: full STAR answers, a tuned CV variant, the interviewer profile once the name arrives.

## Step 7 — Study resources

Only resources **tied to the step-4 gaps** — nothing generic. For each gap: 1–2 free resources first (documentation, guides, videos), then certifications only if they add real signal for the role. State the why for each ("the posting asks for hands-on RAG; this guide gives you the vocabulary for the technical interview"). If the interview is a few days away, prioritize what can be absorbed in that time and say so.
