---
name: galactic-application
description: Analyses job postings, researches employers, assesses candidate fit and prepares pre-call briefings. Use when the user asks about a role, a company or whether to apply.
---

# Galactic Application

Use available evidence about the candidate when assessing fit. If evidence is missing, analyse the posting
and the company and explain what a fit assessment would need. Follow the
[privacy guidance](../galactic-job-search/references/privacy.md) for research.

## 1. Capture the posting
- Use the posting's original wording. Some web tools summarise or translate pages, which can blur
  requirements. If the original is unavailable, ask for the posting text.
- Quote the original when citing requirements. Include the posting URL and date when available.

## 2. Decode the posting
- Role, seniority, team, location/work mode, contract, salary range (or "not disclosed").
- **Must-have** vs **nice-to-have** requirements. Separate them explicitly, because postings mix them.
- Map it to a real role **by its duties, not its title**, using `references/job-roles.md`, and flag it if
  title and content don't match (the guide: "DevOps is a methodology, not a job title"). For roles the
  reference doesn't describe, reason from the duties.
- Questions raised by the posting (see `references/job-hunt-strategy.md` §5.3); any red flags are general
  practice, labelled as such.
- Keywords the screener or ATS will look for.

## 3. Research the company
Use web search and fetch. Every fact gets its source URL and the date. Cover:
- What they do, business model, customers, and how the money is made. Size, locations, funding or ownership.
- Product: use it or read the docs if public. What would the user work on?
- Tech: engineering blog, GitHub org, talks, stack signals from other postings.
- Recent news (last 12 months): launches, funding, layoffs, acquisitions, leadership changes.
- Culture and working conditions: reviews (Glassdoor, Indeed, etc.) read as signals, not truth. Note the
  remote policy and hiring process if reported.
- Other open roles: they tell you where the company is investing.
- Interviewers: only if the user names them. Search "name + company + role" and keep only their role and public
  work links.
Don't pad: if something isn't findable, write "not found" and move on.

## 4. Fit analysis
Apply the screener rubric in `../galactic-cv/references/recruiter-rubric.md` (Block A: gates +
weighted criteria → score and decision), quoting the CV as evidence for each requirement with its evidence
state. Then:
- **Strengths to lead with**: the 3 things that make this user a match.
- **Gaps**, classified as: real gap (be honest about it) / present but not visible on the CV (fix with
  `galactic-cv`) / learnable before the interview (plan with `galactic-interview-prep`).
- **Go / no-go advice**: explain whether it's worth applying and where the role conflicts with the
  candidate's must-haves or deal-breakers. The user decides.

## 5. Pre-call briefing
Use `galactic-reverse-interview` to choose questions, then write the briefing. It's one page the user
can read 10 minutes before a call: the company in 3 lines, why the role exists, what they'll probably probe,
the user's 3 strengths for this role, 2 gaps and how to address them, and the top 3 questions. Use the
sourced facts from the company research.

## 6. Application channels
When the user is about to apply, say which channel the posting offers and, if both exist, give the advice from
`../galactic-cv/references/ats.md` §5 (Guido's take): with an ATS the channel matters little;
without one, the company site is usually where the screener looks; and the site confirms the role is still open.
