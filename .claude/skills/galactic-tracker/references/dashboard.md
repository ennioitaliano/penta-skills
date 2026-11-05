# Dashboard template and data schema

The [HTML template](../assets/dashboard.html) renders application data in a self-contained page.
The page is read-only and works offline.

The template expects the JSON below between `<script id="gjs-data" type="application/json">` and its
`</script>`. Keep the rest of the template byte-identical. In the serialized JSON, escape `<` as
`\u003c`, `>` as `\u003e` and `&` as `\u0026` to keep data from breaking out of the script tag.

## JSON schema

```json
{
  "generated": "2026-09-25",
  "lang": "it",
  "applications": [
    {
      "id": "2026-09-25-acme-backend-engineer",
      "company": "Acme",
      "role": "Senior Backend Engineer",
      "status": "saved",
      "reached": "saved",
      "updated": "2026-09-25",
      "saved_on": "2026-09-25",
      "applied_on": null,
      "source": "LinkedIn",
      "source_url": "https://…",
      "referral": null,
      "location": "Milan, IT",
      "work_mode": "remote",
      "salary_range": "55–70k EUR",
      "contacts": [{ "name": "…", "role": "…" }],
      "next_step": "Decide whether to apply",
      "next_step_date": "2026-09-29",
      "tags": ["go", "fintech"],
      "fit": {
        "score": 72,
        "decision": "Call",
        "summary": "One or two lines of Markdown.",
        "strengths": ["…"],
        "gaps": ["…"]
      },
      "briefing": "Markdown briefing",
      "questions": [{ "for": "Recruiter", "text": "…", "answer": null }],
      "log": [{ "date": "2026-09-25", "text": "Saved. Fit 72/100 (Call)." }],
      "trackzilla": {
        "company_name": "Acme",
        "role_description": "Senior Backend Engineer",
        "job_description": "Location: Milan (hybrid)\nNext: technical interview on 2026-10-02\n---\n<short summary of the posting>",
        "application_date": "2026-09-26",
        "salary": "55-70k",
        "work_mode": "ibrido",
        "status": "colloquio-tecnico",
        "tags": ["go", "fintech"]
      }
    }
  ]
}
```

Field sources and rules:
- `id` uniquely identifies the application.
- `status`, `saved_on`, `applied_on`, `source`, `source_url`, `referral`, `location`, `work_mode`, `salary_range`,
  `contacts`, `next_step`, `next_step_date` and `tags` come from the application data.
- `lang`: `"it"` or `"en"`, whichever matches the language of the conversation. Anything else falls back to English.
  Write `next_step`, `summary`, `briefing` and the log texts in that same language when you write them fresh.
- `reached`: the furthest stage the application got to, one of `saved | applied | screening | interviewing | offer | accepted`.
  For open applications it equals `status`. For `rejected`, `withdrawn` and `ghosted` ones, read it from the log
  (e.g. rejected after the technical interview → `interviewing`). The funnel is computed from it.
- `updated`: the date of the last log line.
- `fit`: the score (0–100) and decision from rubric Block A, with short entries for strengths and gaps.
  Omit `fit` when no assessment is available.
- `briefing`: the pre-call briefing, in Markdown. The renderer supports `#` headings, `-` lists,
  `**bold**`, `_italic_`, `` `code` `` and `[text](https://…)` links, and nothing else. Keep it to one screen.
- `questions`: the chosen questions in order, with the interviewer type in `for` and the
  answer heard, if any, in `answer`.
- `log`: every dated line of the application's log.
- `trackzilla`: the application's row for the **Export for TrackZilla** button, already converted with the mapping in
  [the TrackZilla reference](trackzilla-format.md) (TrackZilla status and work-mode values, `application_date` = `applied_on`,
  the `job_description` layout from section D, query strings stripped from any URL). Set it to `null` for `saved`
  applications, which are left out. **Never** put contacts or log lines in it. The page builds the CSV locally,
  in the browser, when the user clicks the button.
- Omit fields you don't have, or set them to `null`. Never invent values to fill the page.

## Privacy
The template carries a Content-Security-Policy that allows only its own script (pinned by SHA-256 hash) and
blocks every network request, so even an escaping mistake can't send data anywhere. If you **edit the
template's main script** (contributors only), recompute the hash of the exact text between its `<script>` tags
(base64 of the SHA-256) and update the `sha256-…` value in the CSP meta tag. Inserting data doesn't change it.
Contacts are third-party names: they're shown only in the local page, never exported.

The page makes no network requests. External links open when clicked. Keep the candidate's current
compensation and walk-away figure out of the dashboard.
