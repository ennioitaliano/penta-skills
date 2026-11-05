---
name: galactic-tracker
description: Guidance for application records, pipeline reviews, follow-ups, dashboard summaries and TrackZilla exports. Use when the user asks about tracking applications or interpreting a status change.
---

# Galactic Tracker

## Application records

A useful [application record](references/application-record.md) identifies the company, role and status,
and includes dates, source, work mode and posted pay when known. Distinguish a role saved for consideration
from an application actually sent.

For a status change, identify the role, the new stage, the next step and any date. A dated history entry
preserves the candidate's own assessment and prior history. Use ISO dates for structured entries.

Statuses: `saved → applied → screening → interviewing → offer → accepted`, with the exits
`rejected`, `withdrawn` and `ghosted`. Only mark `ghosted` when the user says so, or suggest it after a long
silence and let them decide.

## Pipeline review
- **Needs attention**: overdue `next_step_date`, and processes in `applied`/`screening`/`interviewing` with no
  log entry for 10+ days. Suggest a polite follow-up; this threshold is general practice, not from the guides.
- **Active** table: company · role · status · last update · next step · date, sorted by next date
  (statuses `applied` to `offer`).
- **Saved, not applied yet**: a separate short list, since these are decisions still pending.
- **Closed** table: company · role · final status · closed on.
- **Funnel**: counts per status, and applied→screening→interview→offer conversion. Only show conversion
  with ≥ 5 applications, and say that small numbers are noisy.

## Dashboard template

For a requested dashboard, [the example and data schema](references/dashboard.md) cover pipeline stages,
upcoming dates, funnel counts and per-application details. The included HTML template works offline.

## Rejections

When discussing a rejection, acknowledge it briefly. Help the candidate identify lessons or phrase a
feedback request. Watch for patterns across rejections, for example
always failing at the same stage, and point them out gently with a concrete suggestion.

## Export format

- **Generic CSV**: one row per application, with the record fields as columns. Call out any sensitive fields.
- **TrackZilla**: use the [CSV format and status mapping](references/trackzilla-format.md). Exclude contacts
  and private logs, and explain which data TrackZilla receives if the user imports it. The reference also
  covers interpreting exports from TrackZilla.
