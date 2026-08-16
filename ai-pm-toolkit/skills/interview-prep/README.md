# 🎯 interview-prep

**End-to-end job interview preparation, as a reusable AI skill for Claude Code.**

Paste a job posting URL and get back, in one run:

1. 📋 The posting parsed — title, requirements, seniority, language expectations
2. 🏢 Company research — profile, strategic narrative from the last 12 months, real hiring process (Glassdoor/Indeed)
3. 👤 Interviewer research — public professional profile and connection points (or a "pending" section that updates later)
4. ⚖️ An **honest** fit analysis — requirement by requirement (✓ / ◐ / ✗) with evidence from your CV, an overall verdict, and the "golden connection": the story you should open with
5. 📱 A visual **dossier** published as a private artifact — reviewable on your phone right before walking in
6. ✅ Prioritized recommendations — what to tweak, what to practice, what to expect
7. 📚 Gap-driven study resources — free first, certifications only if they add real signal

## Install

Copy this folder into your Claude Code skills directory:

```
~/.claude/skills/interview-prep/        # personal — available in all projects
<project>/.claude/skills/interview-prep/  # or per project
```

## Use

Start a session where your resume PDF/DOCX is in the working directory, then:

```
Prepare me for this interview: https://www.linkedin.com/jobs/view/1234567890
```

or invoke it explicitly with `/interview-prep`.

## Design decisions worth stealing

- **Honesty is a rule, not a vibe.** The skill explicitly forbids inflating the fit verdict or inventing experience. An AI agent amplifies whatever standards you give it — give it good ones.
- **Research never blocks on logistics.** Missing interviewer name? The section is marked "pending" and the pipeline keeps moving.
- **Resources trace to gaps.** No generic course lists — every suggested resource maps to a specific ✗ or ◐ in the fit table.
- **Old files are respected.** Resumes renamed "OLD VERSION" are automatically ignored, so you control what the skill reads by renaming, not deleting.

## Requirements

- Claude Code with web search/fetch enabled
- Your resume (PDF or DOCX) in the working directory
