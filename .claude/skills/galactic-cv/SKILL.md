---
name: galactic-cv
description: Reviews, rewrites and tailors a CV with Guido Penta's Galactic CV guide, and scores it against a job posting like a screener would. Use when the user shares a CV or asks to fix, tailor or rewrite it.
---

# Galactic CV

Knowledge:
- `references/cv-guide.md`: rules from [galactic-CV-guide-for-developers](https://github.com/GuidoPenta/galactic-CV-guide-for-developers).
- `references/recruiter-rubric.md`: how a screener scores a CV against a posting, adapted from
  [cv-review](https://github.com/matteobaccan/cv-review) by Matteo Baccan.
- `references/rewrite-guide.md`: how to rewrite.
- `references/ats.md`: how ATSs really work, myths vs evidence, LinkedIn Easy Apply vs company site.

## Source labels
Every rule in the references is tagged: **[Guido]** (his guide, with §), **[cv-review]** (Matteo Baccan's
screener rubric), **[Di Fresco]** (typography guidelines), **[pack]** (this pack's own / general practice).
- Say "your guide / Guido's guide says…" **only** for [Guido] items.
- Present [cv-review] items as "a structured screener (cv-review) may look for…", and [pack] items as general advice.
- When [Guido] and [cv-review] conflict, [Guido] wins and [cv-review] items are never forced (e.g. never force
  a numeric result into a bullet: Guido's own sample bullets describe duties).

## Review context
- Use the target role and market to put the CV in context. A rendered CV allows layout and typography
  assessment (Block C). A screenshot can show the layout but cannot establish whether links work.
- **No residence on the CV**: never suggest adding the city of residence/domicile or a home address; the guide
  doesn't ask for it. Mention location only when it describes availability, such as for remote work or relocation.
- **ATS questions** ("what is an ATS?", "will my CV pass the ATS?", "LinkedIn or company site?"): answer from
  `references/ats.md`, which is sourced and tagged; keep its "documented / varies / anecdotal" nuance and quote
  Guido's take where relevant. Otherwise say only what `references/cv-guide.md` says (recruiters read every CV, the ATS is a filtering
  tool, stars and progress bars may not be recognised, keywords matter). Don't add myths about what ATSs can't
  read, such as images, PDFs or columns, or promise an "ATS-proof" CV.

## Modes

### 1. General review (no posting)
Apply every checklist in `references/cv-guide.md`, plus Blocks B (content) and C (typography) of the
rubric. Block A needs a posting, so mark it "N/A — no posting" (don't invent requirements from the target
role). Use the rubric's report structure:
- **Top 3 fixes** that would change the outcome most, first.
- A checklist result per section: ok / fix / missing, with the guide rule and link, the quoted CV text,
  and the proposed rewrite.
- Protected data found: for the photo, Guido's guide leaves it to the user (§2, free choice); for the rest
  (age, date of birth, marital status, nationality…) say only that a structured screener (cv-review) ignores
  them. Keeping any of it is the user's call.

### 2. Targeted review (with a posting)
Run the rubric's Block A against the relevant posting.
Show the score and decision **as the screener would see them**, the evidence state per requirement, and exactly
what to change so that real experience becomes visible. Build on any existing fit assessment.

### 3. Rewrite
Apply [the rewrite guide](references/rewrite-guide.md) in the requested format. If the CV is in a
structured source format such as Typst, retain its structure and conventions while tailoring the content.

- **Targeted CV**: ready to send. An Italian posting allows an Italian or English CV. An English
  posting calls for an English CV.
- **Master CV**: keep the complete account of the candidate's experience. Put unresolved factual
  questions in a separate section.

Explain the important changes and the evidence behind them separately from the CV.

### 3b. Second-language version
Guido's guide recommends having two versions of the CV, Italian and English [Guido §1]. On request, produce the
other-language version as a **rewrite, not a word-for-word translation**:
natural phrasing for that market, job titles as they're used there, the same facts and dates, nothing added.
Keep the data-processing sentence only in the Italian version, and remind the user which version to send: English posting
→ English CV; Italian posting → either.

### 4. Build the master CV
When the CV is thin, interview the user one role at a time: what they built, for whom, the scale, the results
and numbers, the stack. Use those details to build a complete, evidence-based master CV.

## Hard rules
- **Never invent** experience, metrics, titles or dates. When a bullet lacks a result, ask:
  "do you have a number for this? users, latency, revenue, time saved…". If there is none, write an honest
  bullet without one.
- Quote the CV when criticising it, so every judgement is traceable.
- Evidence edge cases: a required skill missing from a long, detailed CV is `Unverifiable` (ask the user) rather
  than `Absent`, unless the CV contradicts it. A vague certification (no issuer, no year) counts as `Inferred`
  at best (undated, so not `Verified`); ask for issuer and year — the answer makes it `Declared`.
- Judge the document, not the person. Blocks B and C score the CV as a document; Block A scores fit for one
  posting, and a low fit is not a verdict on the person's worth.
- After a rewrite, suggest aligning LinkedIn (`galactic-linkedin`).
