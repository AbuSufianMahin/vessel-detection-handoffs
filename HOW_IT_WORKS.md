# How this workspace works

## The problem it solves

In a team thesis, every member talks to their own Claude: in Claude Code, in claude.ai chats, on the phone. Each chat slowly builds its own version of the project. Titles drift, old methods come back, one chat thinks data was collected when it was not, and the supervisor's feedback reaches only the person who read the email.

This workspace keeps one shared picture in a private GitHub repo that every Claude reads, while still letting each member keep their own context.

## The layers, from strongest to weakest

| Layer | File | Who edits it | What it holds |
|---|---|---|---|
| 1. Supervisor | `faculty/faculty_instructions.md` | Supervisor only | Rubrics, deadlines, feedback. Overrides everything below. |
| 2. Writing rules | `.claude/skills/thesis-writing/` | Team, rarely | How thesis text must be written (voice, tense, citations, section recipes, LaTeX rules). |
| 3. Team brain | `CLAUDE.md` | Everyone, by its rules | Shared facts (title, RQs, objectives, method), status, open items, Decision log, short member notes. |
| 4. Personal brains | `brain/<Name>_Brain.md` | Each member, own file only | That member's role, tasks, focus and what their chats have worked out. Loses to `CLAUDE.md` on shared facts. |
| 5. Session logs | `logs/<name>.md` | Each member, own file only | Five-line record of every session, newest first. |

When two layers disagree, the stronger one wins and Claude says so in one line.

## The flows

**Start of a session.** Claude reads the supervisor file, the latest logs, `CLAUDE.md` and the current member's brain. In claude.ai, the Project syncs these from GitHub ("Sync now").

**End of a session ("wrap up").** Claude writes a five-line log entry (Did, Decided, Next, Files), asks whether the member's brain needs an update, and reminds you to add a Decision log line if the team decided something.

**Decisions.** The Decision log is add-only: a changed decision gets a new dated line that replaces the old one, so the history stays readable. Before the repo is shared with the team, the owner may still rewrite it freely.

**Brains.**
1. One member writes the first brain (a good model for the others).
2. They write a handoff (`templates/handoff-template.md`): the current project state, plus a list of older ideas that are now replaced.
3. Every other member gives the handoff and the model brain to their own claude.ai chat with the prompt in `templates/brain-prompt.md`. The chat updates its picture of the project and writes that member's brain.
4. The repo owner integrates all brains once before launch: shared facts that disagree are corrected; new team-level information moves into `CLAUDE.md`.
5. After launch, each member keeps their own brain current.

**The report.**
- The official university template sits in `report/university-template/` as a reference that nobody edits or builds.
- Each submitted phase (for example a pre-thesis report) is frozen: its PDF goes into `archive/`, and its source becomes the starting point for the next phase. A git tag (for example `p1-submitted`) marks the exact submitted source.
- Reviews are report-only Markdown files in `report/reviews/`. They feed the next draft; they never edit the source.

## Lessons that are easy to miss

- **Install LaTeX per user.** A system-wide (all users) MiKTeX install needs admin rights for every package repair, and a half-finished admin install breaks every build. "Install only for me" avoids both.
- **Skills must sit in folders.** Claude Code only loads `.claude/skills/<name>/SKILL.md`. A loose `.md` file in `.claude/skills/` is ignored.
- **Read community skills before committing them.** Check whether they run scripts, install packages or use the network, and rank them below your own writing-rules skill.
- **Keep names boring.** Lowercase, no spaces, no brackets in `report/`. Brackets and spaces break LaTeX paths and tools.
- **Never let a chat say planned work is done.** `CLAUDE.md` has a Current status section for exactly this; Claude checks it before claiming anything happened.
- **Participant data never enters the repo or a chat.** Not in logs, not in brains, not in reviews.
