# Career Adviser 🧭

Career Adviser is an installable AI skill for evidence-based career planning, vacancy analysis, CV improvement and interview learning.

It keeps career context in a private workspace so the assistant can continue from prior work without relying on chat memory.

## Install

```bash
npx skills add krutenyuk/career-adviser -g
```

For a specific agent:

```bash
# Codex
npx skills add krutenyuk/career-adviser --skill career-adviser -g -a codex -y

# Claude Code
npx skills add krutenyuk/career-adviser --skill career-adviser -g -a claude-code -y

# VS Code with GitHub Copilot
npx skills add krutenyuk/career-adviser --skill career-adviser -g -a github-copilot -y
```

Update later with:

```bash
npx skills update career-adviser -g
```

## Architecture

The root `SKILL.md` is deliberately small. It understands the user's goal and combines specialised capabilities when needed:

- `career-compass` — career direction and growth;
- `vacancy-fit` — role fit and gap analysis;
- `cv-review` — CV positioning and tailoring;
- `interview-review` — learning from interviews and recruiter calls.

Shared rules live in `references/`, especially evidence discipline and workspace behaviour.

This means a request such as "assess this vacancy and tailor my CV" can use both Vacancy Fit and CV Review instead of being forced into one mode.

## Private workspace

Copy `assets/workspace-template/` somewhere private.

Typical structure:

```text
my-career/
├── cv/
├── jobs/
├── transcripts/
├── support/
├── outcomes/
├── profile.md
└── summary.md
```

### What the files mean

- `profile.md` — durable, confirmed career facts and preferences;
- `summary.md` — short working memory: active applications, recent conclusions and next actions;
- `outcomes/` — detailed dated analyses;
- `jobs/` — saved vacancies and application material;
- `transcripts/` — recruiter/interview/coaching notes;
- `support/` — useful market or domain material;
- `cv/` — source and tailored CV versions.

The skill should read only the material relevant to the current decision rather than loading the entire workspace every time.

## Evidence discipline

The adviser separates:
- confirmed facts;
- inferences;
- missing evidence;
- real gaps;
- third-party opinions.

It must not invent metrics, seniority, scope, tools, team size or outcomes. Plausible experience is not treated as confirmed experience.

## How to use it

You can ask naturally:

> I feel stuck. What realistic directions do I have from here?

> Here is a vacancy. How well do I fit?

> Assess this role and tailor my CV for it.

> I added notes from an interview. What should I learn from it?

The assistant decides which capabilities to combine.

## New workspace

If the workspace has too little evidence for a substantive conclusion, add a CV to `cv/` or describe the relevant experience in chat. The adviser should ask only for information that could materially change the decision, not run a fixed intake questionnaire.

## Updating profile and summary

Confirmed durable information belongs in `profile.md`.

Current applications, recent conclusions, open questions and immediate next actions belong in `summary.md`.

Detailed analyses belong in `outcomes/`.

This keeps long-term memory, working memory and history separate.

## Evaluation

`evals/` contains lightweight regression cases for checking future prompt and model changes. They cover strong and weak vacancy fit, mixed vacancy/CV requests, insufficient context, conflicting evidence and interview feedback.

## Privacy

Do not put a filled private career workspace into this public repository. Keep personal CVs, interview notes, salary information and application history outside the public skill repository.

## Manual installation

Copy the complete `career-adviser` folder into the skills directory used by your agent.

Common locations:

- Codex: `~/.agents/skills/career-adviser/`
- Claude Code: `~/.claude/skills/career-adviser/`
- VS Code / GitHub Copilot: `~/.agents/skills/career-adviser/` or `~/.copilot/skills/career-adviser/`

The exact integration may evolve by agent, but the skill itself remains portable because its behaviour and workspace are plain files.
