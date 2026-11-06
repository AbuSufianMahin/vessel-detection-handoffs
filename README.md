# Thesis workspace template

A starter kit for a team thesis written with Claude (Claude Code in VS Code, plus claude.ai Projects). It gives every team member's Claude the same picture of the project, keeps each member's personal context, and lets the supervisor leave instructions that override everything else.

Read `HOW_IT_WORKS.md` first for the idea, then `SETUP.md` to install it. Every `<placeholder>` in angle brackets is something to fill in for your own thesis.

## What's where

```
HOW_IT_WORKS.md            The idea behind this workspace (start here)
CLAUDE.md                  Team brain: shared facts, status, decisions. Claude Code reads it automatically.
brain/                     One personal brain per member (<Name>_Brain.md); see brain/README.md
faculty/
  faculty_summary.md       Overview for the supervisor (team updates it)
  faculty_instructions.md  Supervisor's rubrics and feedback (only the supervisor edits it)
logs/                      One session log per member
guidelines/                Your department's thesis guidelines
literature/                Paper notes, one file per paper
report/                    LaTeX source (see report/README.md); PDF builds go to report/build/
  university-template/     The official template from your university (reference only, never edited)
  reviews/                 Review reports on the draft (Claude or human)
  snapshots/               Draft PDFs shared with the supervisor
archive/                   Old notes, submitted PDFs, retired drafts
templates/                 Handoff and prompt templates for bringing chats up to date
.claude/skills/
  thesis-writing/          Your thesis writing rules as a Claude skill
.vscode/                   Shared VS Code and LaTeX Workshop settings
```

## Every session

1. `git pull`
2. Work in Claude Code (VS Code) or claude.ai. In claude.ai, click "Sync now" in the Project's GitHub knowledge first. In Claude Code, say who you are ("I'm <Name>").
3. Tell Claude "wrap up" and save the log entry to `logs/<you>.md`. If something in your own area changed, update `brain/<You>_Brain.md` too.
4. If anything was decided for the team, add a line to the Decision log in `CLAUDE.md`.
5. `git add -A`, `git commit -m "short message"`, `git push`

Push the same day you pull. Long gaps between pull and push are where conflicts come from.

## House rules

- Edit `CLAUDE.md` by the rules at the top of that file: Core changes need team agreement, the Decision log is add-only, and you edit only your own Member notes.
- Edit only your own brain in `brain/`. Shared facts live in `CLAUDE.md`, which wins if the two disagree.
- Only the supervisor edits `faculty/faculty_instructions.md`. Everyone else reads it.
- Read `faculty/faculty_summary.md` before pushing changes to it. The supervisor takes it at face value.
- Never commit participant data: no names, phone numbers, recordings, transcripts or survey responses.
- Files inside `report/`: lowercase names, no spaces (Linux and LaTeX care about case; Windows and Mac do not).
- Set the repo to "Watch" so you see when the supervisor adds instructions.
