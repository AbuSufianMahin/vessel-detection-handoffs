# Brains

One brain per team member. A brain is that member's working memory for the thesis: their role, their tasks, what their own Claude chats have worked out, and their individual items. `CLAUDE.md` holds the facts the whole team shares.

| Member | File |
|---|---|
| <Name> | `<Name>_Brain.md` |
| <Name> | `<Name>_Brain.md` |

Start each brain from `_TEMPLATE_Brain.md`.

## Rules

- Edit only your own brain, the same rule as Member notes in `CLAUDE.md`.
- `CLAUDE.md` wins on shared facts (title, RQs, objectives, method, decisions, status). If a brain disagrees with it, Claude points out the mismatch and updates the brain, or proposes a Decision log line if the brain holds a newer team decision.
- Nothing about participants ever goes in a brain: no names, phone numbers, transcripts, recordings or survey responses.
- Keep the file name `<Name>_Brain.md` so every member's Claude can find it.

## Flow

1. **First version (before the repo launches):** one member writes the first full brain as the model. The others get that model and a handoff (`templates/handoff-template.md`, filled in). In their own claude.ai thesis chat, they paste the prompt from `templates/brain-prompt.md`, and send the resulting brain to the repo owner.
2. **Integration (once, by the repo owner, before launch):** place each brain in this folder. Claude checks it against `CLAUDE.md`. Shared facts that disagree are corrected in the brain. New team-level information (a decision, a supervisor remark, an open item) moves into `CLAUDE.md` and stays in the brain only as a pointer.
3. **After launch:** each member updates their own brain when something in their own area changes. Team-level changes still go into `CLAUDE.md`. At "wrap up", Claude asks whether the brain needs an update.
4. **claude.ai Projects:** select `CLAUDE.md` and your own brain in the Project's GitHub knowledge, and click "Sync now" before each session. Remove any brain or handoff uploaded by hand.
