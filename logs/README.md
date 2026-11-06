# Session logs

One file per member (`logs/<name>.md`, lowercase). Each Claude session ends with a short entry, so teammates (and their Claude) can see what changed without reading whole chats.

## How to log a session

At the end of a session, tell Claude "wrap up". It writes an entry in the format below.

- Claude Code: it adds the entry to the top of your file, just under the heading.
- claude.ai: it prints the entry; paste it at the top of your file, then commit and push.

If a decision was made, also add one line to the Decision log in `CLAUDE.md`. If something in your own area changed, Claude also updates your brain in `brain/` (see `brain/README.md`).

## Entry format

```
## YYYY-MM-DD | Short topic
Did: what was done, in one or two lines
Decided: decisions made (also copied to the CLAUDE.md Decision log), or "none"
Next: what comes next
Files: files changed, or "none"
```

Keep entries to five lines. Once a file gets long, ask Claude to roll entries older than a month into a short dated summary at the bottom.

## Wrap-up prompt (if "wrap up" alone does not work)

> Write a session log entry for this conversation in the format from logs/README.md. Five lines maximum. List only what actually happened in this session, and mark anything still undecided as "Next".

## Starting a member's file

```
# Session log: <Name>

Newest entries first.
```
