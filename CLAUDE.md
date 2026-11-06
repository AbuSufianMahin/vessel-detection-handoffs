# Team Brain: <Short thesis name>

Shared memory for every team member's Claude. Claude Code reads this file automatically when it opens the repo. In claude.ai, it reaches each member's Project through the GitHub integration (click "Sync now" before a session).

## Rules for editing this file

- Pull before you edit. Push right after, in the same sitting.
- Core: change only after the team agrees, then add a line to the Decision log.
- Decision log: add new lines at the bottom with the date and your initials. Never rewrite an old line. If a decision changes, add a new line that replaces it.
- Member notes: edit only your own subsection.
- If git reports a conflict here, keep both versions and ask Claude to merge them.
- Nothing about participants ever goes in this repo: no names, phone numbers, transcripts, recordings or survey responses.

## Instructions for Claude

1. At the start of a thesis session, read `faculty/faculty_instructions.md`, the latest entries in `logs/`, and the current member's brain in `brain/<Name>_Brain.md` (ask which member if it is not clear). The supervisor's instructions override everything else in this repo when they conflict. On shared facts, this file overrides a brain; point out any mismatch (see `brain/README.md`).
2. For any text meant for the thesis report or its LaTeX source, follow the `thesis-writing` skill in `.claude/skills/thesis-writing/`. The official template in `report/university-template/` is the reference for the report's structure; read it, never edit or build it.
3. If a Decision log line contradicts the Core section, the newest dated line wins. Point out the mismatch so the team can update Core.
4. When the user says "wrap up", write a session log entry in the format from `logs/README.md`. In Claude Code, add it to the top of `logs/<member>.md`. In claude.ai, output it for the user to paste. Then ask whether the member's brain needs an update, and make or output the update if so.
5. Never describe planned work as done. Check Current status before saying anything has happened.
6. Facts below come from the team's own reports. Numbers marked with a source still need that source cited in the thesis text.

---

## Core (team agreement required to change)

### Thesis

- Title: "<Full thesis title>"
- Degree: <Degree, department, university>. <Current phase and report date>.
- Supervisor: <Name, position>. <Co-supervisor or coordinator, if any>.
- Field: <Field>.

### Team

| Member | ID | Role |
|---|---|---|
| <Name> | <ID> | <Area of responsibility> |
| <Name> | <ID> | <Area of responsibility> |

### Title rules

- <Words or phrases the title must keep>
- <Words the title must avoid>
- <Key terms and how to use them consistently>

### Research chain

<One or two sentences: the causal or logical chain the thesis follows, and the proposed solution.>

### Novelty (keep claims this narrow)

- <The exact gap, stated as narrowly as the evidence allows>
- <Closest prior work that must be acknowledged, so no chat claims the area is unstudied>

### Research questions

- RQ1. <...>
- RQ2. <...>

### Objectives

- O1. <"To" + action verb, with numbers and a deadline>. Answers RQ<n>.
- O2. <...>

### Method summary

- Design: <approach>.
- Phase 1: <...> (mark "done" only when it is).
- Phase 2: <...>
- Analysis: <...>

### Proposed system (if any)

- <Initial requirements, marked as to be refined>

### Ethics commitments

- <Approval needed before contacting participants>
- <What is never collected>
- <Consent procedure>
- <Wording rules, privacy, storage>

### Key figures (cite the source each time)

- <Figure> (<source>)

### Writing constraints (details in the thesis-writing skill)

- <Voice: for example third person or passive>
- <No contractions, no em-dashes, or your own rules>
- <Citation style>
- <Spelling variety>

---

## Current status

- <Phase>: <status>.
- Data collected: <none / what>.
- Ethics approval: <status>.
- LaTeX: <where the source is and whether it builds>.

## Open items

- [ ] <Item>

## Decision log (add new lines at the bottom)

- <YYYY-MM-DD> [<initials>] <Decision>

## Member notes

Each member edits only their own subsection: current focus, chapter you are editing, anything your teammates' Claude should know.

### <Name>

### <Name>
