# Workspace model

Use the workspace as external memory, not as a prompt dump.

## Durable memory

`profile.md` contains relatively stable, confirmed information:
- roles, dates and domains;
- skills and methods;
- scope and leadership;
- achievements and evidence;
- target roles and seniority;
- languages, location and work authorisation;
- durable preferences and constraints.

Do not store speculation as fact.

## Working memory

`summary.md` contains the current state:
- current positioning;
- active applications;
- recent conclusions;
- open questions;
- immediate next actions;
- last update date.

Keep it short.

## History

`outcomes/` contains detailed dated analyses and reviews.

`transcripts/` contains recruiter calls, interviews and coaching notes.

`support/` contains useful reference material.

## Jobs

Prefer a folder per active role when several artefacts accumulate:

```
jobs/
  company-role/
    vacancy.md
    analysis.md
    notes.md
```

A single dated Markdown file remains acceptable for simple cases.

Preserve the vacancy source URL and the full or faithfully captured job description whenever possible.

## CV

Keep source CVs in `cv/`. Never overwrite the original unless the user explicitly asks. Create clearly named tailored versions.

## Reading strategy

Do not preload the whole workspace. Inspect what exists and read only the evidence relevant to the current decision.
