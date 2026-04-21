# Repo Intelligence Agent

An AI-powered agent built with Claude Code that reads any GitHub repository
or AI concept and explains it in plain English — tailored to who's asking.

Built as part of Hamza Farooq's Claude Code in Practice cohort (Module 2).

---

## What it does

This project contains three custom Claude Code skills and commands:

**`/explain-me-a-repo`**
Give it any GitHub URL. It browses the repo live using Playwright MCP
and returns a structured 10-section breakdown — what it does, how it works,
architecture, key technologies, how to run it, and what's missing.

**`/explain-ai-concept`**
Give it any research paper, article, YouTube link, or technical term.
It reads it live, asks who you are (job seeker, career returner, student,
IT or non-IT professional), and explains it in plain English with a
relatable analogy, open problems, and an implementation brief.

**`/update-memory`**
Updates the project memory file with latest context, decisions, and learnings.
Run every 10 conversations to keep Claude's context fresh.

---

## Why I built it

Most AI tools explain things the same way to everyone.
This one asks who you are first — then adjusts the depth,
the analogies, and the framing to match your background.

Inspired by research showing that knowledge workers learn AI skills
in isolation with no shared playbook. This is the tool I wished existed.

---

## Project structure

.claude/
├── commands/
│ ├── explain-me-a-repo.md
│ ├── explain-ai-concept.md
│ └── update-memory.md
├── skills/
│ ├── repo-explainer/SKILL.md
│ ├── explain-ai-concept/SKILL.md
│ └── youtube-researcher/SKILL.md
└── memory.md
docs/
├── repo-summary.md
├── prd-template.md
├── persona.md
├── decision.md
└── roadmap.md

## MCP servers required

- Playwright MCP — for reading articles and GitHub repos live
- Brave MCP — for YouTube and open web browsing

Install both:

```bash
npm install -g @playwright/mcp
npm install -g @browsermcp/mcp
claude mcp add playwright npx @playwright/mcp
claude mcp add brave npx @browsermcp/mcp
```

## How to run

```bash
git clone https://github.com/Nityaa2396/repo-intelligence-agent.git
cd repo-intelligence-agent
claude
```

Then type any slash command to get started.

---

Built by Nitya.
