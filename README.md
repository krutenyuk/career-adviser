# Career Adviser 🧭

Career Adviser turns an AI assistant into a thoughtful career partner.

It can help you understand where to grow next, check whether a vacancy fits you, improve your CV, and remember the useful things you discover along the way.

You do not need to be a developer. You do not need to know how “agents” work. If your AI assistant can open a folder and read files, you are ready.

## Install in one command

If you have [Node.js](https://nodejs.org/) installed, run:

```bash
npx skills add krutenyuk/career-adviser -g
```

The installer finds the skill, detects supported AI agents on your computer, and lets you choose where to install it. The `-g` flag makes Career Adviser available in all your projects.

To install non-interactively for one specific agent:

```bash
# Codex
npx skills add krutenyuk/career-adviser --skill career-adviser -g -a codex -y

# Claude Code
npx skills add krutenyuk/career-adviser --skill career-adviser -g -a claude-code -y

# VS Code with GitHub Copilot
npx skills add krutenyuk/career-adviser --skill career-adviser -g -a github-copilot -y
```

Then invoke it with `$career-adviser` in Codex or `/career-adviser` in Claude Code and VS Code. You can also ask a matching career question normally and let the agent load the skill automatically.

To update it later:

```bash
npx skills update career-adviser -g
```

<details>
<summary>Manual installation without Node.js</summary>

Download this repository and copy the complete `career-adviser` folder to the personal skills directory used by your agent:

- **Codex:** `~/.agents/skills/career-adviser/`
- **Claude Code:** `~/.claude/skills/career-adviser/`
- **VS Code with GitHub Copilot:** `~/.agents/skills/career-adviser/` or `~/.copilot/skills/career-adviser/`

Restart or reload the agent if the skill does not appear immediately.

</details>

Installing the skill does not upload your CV or career data. After installation, make a private copy of `assets/workspace-template`, add your CV or describe your experience in chat, and begin with a normal career question.

## The short version

1. Download this project.
2. Make your own private copy of the `workspace-template` folder.
3. Put your CV there and ask your AI assistant a career question.

For example:

> Read the Career Adviser instructions and help me understand what role I should target next.

That is enough to begin.

## What is this, exactly?

Career Adviser is not a separate app. There is no new account, dashboard, or subscription.

It is a set of instructions for an AI assistant, plus a simple folder where you keep your career information. Think of it as two things working together:

- **the adviser** — `SKILL.md` tells the AI how to help you;
- **the notebook** — your private career folder holds your CV, vacancies, notes, and results.

The AI reads the notebook before answering. This means you do not have to explain your whole career again every time you start a new conversation.

## What can it help with?

You can talk to it normally. You do not need to choose a special mode or remember a command.

### “I do not know what I want next”

Career Adviser runs a **Career Compass** conversation. It asks about work that gives or takes away energy, projects you are proud of, your strengths, constraints, location, languages, and plans.

Then it suggests two to four realistic directions. For each one, it explains why it may fit, what you already have, what is missing, and one useful action you can take now.

Try saying:

> I feel stuck in my current role and do not know where to grow next.

### “I found a job. Do I fit?”

Add the vacancy to the `jobs` folder or paste it into the chat. Career Adviser compares the job with your real experience.

It shows:

- where you are a strong match;
- where the evidence is weak or missing;
- which gaps actually matter;
- how realistic the opportunity looks;
- what to improve first;
- what to change in your CV.

Try saying:

> I added a vacancy to the jobs folder. How well do I fit, and what are the biggest gaps?

### “Can you make my CV better?”

Career Adviser reviews your CV for a role, country, or region. It looks at positioning, clarity, seniority, evidence, results, keywords, and language.

It does not invent achievements or silently rewrite your original file.

Try saying:

> Review my CV for senior product strategy roles in Germany. Tell me which changes would have the biggest impact.

### “I had an interview. What should I learn from it?”

Put the transcript or notes into the `transcripts` folder.

Career Adviser finds useful stories, facts, metrics, better wording, and things to improve before the next interview. It shows you what it found and asks what may be added to your profile. Nothing from a transcript goes into `profile.md` without your approval.

Try saying:

> I added a new interview transcript. What did you learn about me, and what should I do better next time?

## Start in five minutes

### Step 1: Download Career Adviser

On GitHub, click the green **Code** button, choose **Download ZIP**, and unzip the downloaded file.

If you already use Git, you can clone it instead:

```bash
git clone https://github.com/<owner>/career-adviser.git
```

You should now have a folder called `career-adviser`.

### Step 2: Make your private career folder

Open:

```text
career-adviser/assets/workspace-template
```

Duplicate the whole `workspace-template` folder and rename the copy. For example:

```text
my-career
```

Move this new folder somewhere private. Your Documents folder is fine.

Do not put your real CV or interview notes into the original `workspace-template`. That folder is only a clean blank copy for new users.

If you prefer the command line, the same action looks like this:

```bash
cp -R career-adviser/assets/workspace-template my-career
```

### Step 3: Add your CV — or just start talking

Put your current CV into:

```text
my-career/cv/
```

PDF, Markdown, and plain text are all good choices if your AI assistant can read them.

No CV yet? That is okay. Tell the adviser about:

- the roles you have had;
- the kind of work you did;
- the tools or methods you used;
- two or three results you are proud of.

The adviser can build your profile from the conversation. It should not keep pushing you to upload a file if you prefer to work in chat.

### Step 4: Let your AI assistant see both folders

Your assistant needs access to:

1. the `career-adviser` folder, which contains its instructions;
2. your private `my-career` folder, which contains your information.

Then say something like:

> Read `career-adviser/SKILL.md` and use it as your instructions. My private career files are in `my-career`. Help me decide what to do next.

Some AI tools can remember the skill after you install it. Others need to be reminded to read `SKILL.md` when you start a new project or chat. Both ways are fine.

## What are all these folders for?

Imagine your career folder as a small filing cabinet:

- **`cv/`** — your current CV and any versions you want to compare;
- **`jobs/`** — vacancies you are considering;
- **`transcripts/`** — notes or transcripts from interviews, recruiter calls, and career consultations;
- **`support/`** — useful articles, wording examples, industry notes, or leadership descriptions;
- **`outcomes/`** — longer reports created by the adviser;
- **`profile.md`** — the reliable facts the adviser knows about you;
- **`summary.md`** — a short “where we are now” note for the next session.

When this guide says `/cv/` or `/jobs/`, it means the folder inside **your private career folder**. It does not mean the top level of your computer.

You do not need to fill everything in. Start with a CV or a short description of your experience. The other folders become useful over time.

## Where will the answers go?

Short answers appear in the chat. Longer analysis is saved in `outcomes`:

```text
outcomes/YYYY-MM-DD_compass.md
outcomes/YYYY-MM-DD_vacancy-<company>-<role>.md
outcomes/YYYY-MM-DD_cv-review.md
```

`profile.md` keeps confirmed facts about your experience, goals, preferences, languages, location, and constraints.

`summary.md` keeps the latest conclusions, active applications, open questions, and next actions. This helps a future conversation start from where you stopped.

## How to connect it to your AI tool

Different AI tools use different words: skills, rules, instructions, context, knowledge, or project files. Do not worry about the label. The important part is that the assistant can read `SKILL.md` and your private career folder.

### The simple way: point the assistant to the file

Open both folders in your AI workspace and say:

> Please read `career-adviser/SKILL.md` before helping me with the files in `my-career`.

This is the easiest option for many AI editors and file-aware assistants.

### If your tool has a place for instructions

Add `SKILL.md` to the tool's project instructions, rules, knowledge, or custom prompt. You can upload the file, link to it, or paste its contents — whichever your tool supports.

### If your tool supports installable skills

Copy the complete `career-adviser` folder into that tool's skills folder. Keep the folder name unchanged.

Current personal skill locations are:

- **Codex:** `~/.agents/skills/career-adviser/`
- **Claude Code:** `~/.claude/skills/career-adviser/`
- **VS Code with GitHub Copilot:** `~/.agents/skills/career-adviser/` or `~/.copilot/skills/career-adviser/`

You can then ask normally or invoke the skill explicitly with `$career-adviser` in Codex and `/career-adviser` in Claude Code or VS Code. If a tool does not notice the new skill immediately, restart or reload it.

### If your assistant only works in chat

Upload `SKILL.md`, your CV, and any other relevant files to the chat. Ask the assistant to return updated Markdown files for you to download.

This still works, but the assistant may not remember previous sessions automatically. Keep the latest `profile.md` and `summary.md`, then upload them next time.

## A few useful habits

- Keep using the same private career folder. That is how the adviser builds context over time.
- Save the full text of a vacancy, not only the link. Job pages can disappear or require a login.
- Add numbers and concrete examples when you can. “Reduced reporting time by 30%” is more useful than “improved reporting.”
- Correct the adviser when something is wrong. Your confirmed information matters more than an AI guess.
- Tell it the target country or region when reviewing a CV. Expectations differ between markets.
- You can edit `profile.md` yourself at any time. It is your file.

## Please keep your information private

Your career folder may contain your name, contact details, salary expectations, visa status, employment history, and interview conversations.

Do not upload your filled `my-career` folder to a public GitHub repository. Keep it outside the public `career-adviser` project, or make sure it is excluded from Git.

The downloadable `workspace-template` is blank on purpose.

## Updating Career Adviser

Download the newest version and replace the installed `career-adviser` folder. If you edited `SKILL.md`, save your copy first.

Do not replace `my-career`. Your private career folder is separate from the skill and should stay with you.

## Removing it

Delete the installed `career-adviser` folder from your AI tool's skills or instructions location.

This does not delete your private career folder. You can keep that notebook, move it, or remove it separately.

## One last thing

The quality of the result depends on what your AI assistant can do. The best experience comes from an assistant that can read files, write Markdown, open PDFs, and search the web when current market information is needed.

But you do not need a perfect setup to start. A CV, a folder, and one honest question are enough.
