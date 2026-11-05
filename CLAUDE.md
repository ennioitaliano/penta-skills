# CLAUDE.md

This folder is **The Candidate's Guide to the Galaxy**: a set of Claude Code skills that coach a person through a job search,
from CV to signed offer. The person who opened it is a job seeker, not (necessarily) a developer of this repo.

- Start from `galactic-job-search` for an overview or invoke a specific `galactic-*` skill.
  Use the guides and rubrics to shape the requested job-search advice.
- Reply in the user's language. The skills are written in English, but the conversation doesn't have to be.
- Never fabricate experience, numbers or facts. Cite sources and dates for anything about companies and markets.

See the [privacy guidance](.claude/skills/galactic-job-search/references/privacy.md) for research and drafts.

## If you are contributing to the repo

- Skills: `.claude/skills/galactic-*/SKILL.md`. Knowledge lives in each skill's `references/`, as operational
  summaries of the source guides, with a link back to them. Keep references faithful to the source (the Italian
  text of Guido's guides is canonical), and tag every rule with its origin: [Guido], [cv-review], [Di Fresco],
  [Dataskew] or [pack]. Don't harden "can" into "must", and don't turn an example into a rule.
- Zero dependencies: no scripts, and no install step beyond cloning.
- English for everything committed, except the user-facing `README.md`, which is Italian. `README.en.md` is its
  English twin, and the two must stay in sync.
- **Examples in references use fictional data only** (Acme, Jane Doe). Before any commit or PR, check the staged
  diff and the PR text for anything from `workspace/`: names, companies applied to, figures, log lines. Never
  `git add -f` anything under `workspace/`. Keep your own job search in a separate clone from the one you contribute from.
- The dashboard template (`galactic-tracker/assets/dashboard.html`) has a Content-Security-Policy with the SHA-256
  hash of its main inline script. If you change that script, recompute the hash (see `references/dashboard.md`).
