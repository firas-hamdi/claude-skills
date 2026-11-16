# Claude skills

Personal skills for Claude Code. This repository is the source of truth; the copy in `~/.claude/skills` on each machine is a clone of it.

## What is in here

| Skill | Start it with | What it does |
|---|---|---|
| [fable-playbook](fable-playbook/SKILL.md) | `/fable-playbook` | Working method for multi-step work: plan, break into steps, verify, report. |

Each skill is a folder holding one `SKILL.md`. The file starts with a short header (`name`, `description`) followed by the instructions in Markdown. The `name` matches the folder name.

## Install on a new machine

Clone the repository into the personal skills folder:

```bash
git clone git@github.com:firas-hamdi/claude-skills.git ~/.claude/skills
```

If `~/.claude/skills` already exists, clone somewhere else and copy the skill folders in.

Start a new Claude Code session afterwards; skills are loaded when a session starts.

## Use a skill

- Type `/fable-playbook` in the message box, optionally followed by the request.
- Claude also loads a skill by itself when a task matches the skill's `description`.

## Change a skill

1. Edit the `SKILL.md` in `~/.claude/skills/<skill-name>/`.
2. Start a new session to try it; a running session keeps the version it loaded.
3. Commit and push:

```bash
cd ~/.claude/skills && git add -A && git commit -m "Describe the change" && git push
```

Edit in one place only and push from there, so copies on other machines do not drift apart.

## Add a skill

Create a new folder with its own `SKILL.md`, add a row to the table above, then commit and push.

## What is not in here

- `synced/` is managed by the Claude desktop app and is ignored by Git.
- Nothing secret belongs in a skill: no passwords, keys or client names.

## History of fable-playbook

- **Revised version (2026-11-16):** narrower trigger description; keep working while waiting for an answer; record constraints in the task list; new section on handling material and helper agents; cleanup step; shorter mistakes list; example report.
- **Original version:** the first commit in this repository.
