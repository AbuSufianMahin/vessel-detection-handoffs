---
name: thesis-writing
description: Thesis writing rules, section recipes and self-check for the thesis "<Full thesis title>" at <university>. Use this whenever drafting, editing, reviewing or proofreading any text meant for the thesis report or its LaTeX source, including the abstract, problem statement, research questions, objectives, literature review, comparison table, research gap, methodology, ethics, conclusion, transitions, captions, citations and the .bib file. Also use it when asked to check a section against the rubric, the guidelines or the supervisor's feedback.
---

# Thesis Writing

This skill turns the department's thesis guidelines into working rules for this team's thesis. Read it fully before writing or reviewing any thesis text. Put the full guideline transcription in `references/` (see `references/README.md`) and open it when you need the original examples or the submission checklist.

The rules below are sensible defaults. Change any of them to match your department's guidelines and your supervisor's instructions, and keep this file and `CLAUDE.md` consistent.

## 1. Before you write

1. Read `faculty/faculty_instructions.md` if it is available. The supervisor's instructions override everything in this skill when they conflict. If a rule here clashes with one there, follow the supervisor's and say so in one line.
2. Take project facts (title, RQs, objectives, sample sizes, status) from `CLAUDE.md`, and the member's context from `brain/<Name>_Brain.md`. Do not rely on memory of earlier versions; titles and methods change.
3. If neither file is available (for example, in claude.ai with an unsynced Project), say so and ask the user to sync or paste the relevant part, rather than guessing facts.

Rule precedence for thesis text: supervisor instructions, then this skill and the guidelines, then the project constraints in `CLAUDE.md`, then the user's general chat preferences. Chat replies may follow the user's own style; the rules below apply to text that goes into the report.

## 2. Non-negotiable rules

- Never invent statistics, citations, authors, page numbers or findings. If a claim needs a source that is not available, write `[CITATION NEEDED]`. For missing project details, write `[TO BE FILLED]`.
- Never describe planned work as done. Until `CLAUDE.md` says otherwise, methodology is written in the future tense ("will be recruited"). Use the past tense only for steps actually completed.
- Present tense for general facts and for what prior work shows ("Smith et al. [3] report that...").
- Voice: <third person or passive ("This thesis examines", "Interviews will be conducted"); no "I"; no "we" unless the supervisor allows it>.
- <No contractions in thesis text.>
- <Punctuation rules, for example no em-dashes; number ranges use "to".>
- <Citation style, for example IEEE numeric `[n]` in order of first appearance through BibTeX `\cite{key}`.>
- <Spelling variety, for example British English, applied consistently.>

## 3. Project constraints

- <Title rules: what it must keep and must avoid.>
- <Key terms and how to use them.>
- <Narrow novelty claim and the prior work that must be acknowledged.>
- <Anything that must never be implied, for example that a prototype connects to a real service.>

## 4. Plain academic style

Examiners read many AI-polished reports, and inflated prose costs credibility. Write the way a careful researcher talks.

- Avoid: delve, tapestry, testament, landscape, realm, pivotal, crucial, paramount, robust, seamless, leverage, harness, foster, underscore, furthermore, moreover, notably, "it is important to note", "in today's digital age", "plays a vital role", "in conclusion".
- No promotional claims ("novel", "groundbreaking", "revolutionary", "the first"). State what the work does and let the reader judge.
- Match claim strength to evidence. A study of 21 people "suggests"; it does not "prove".
- Vary sentence length. Keep paragraphs to four to six sentences, each with one main point.
- Prefer concrete numbers and named instruments over adjectives ("about 120 participants", not "a large sample").

## 5. Section recipes

### Problem statement (five parts, in order)
Context (the broader area), Issue (the specific problem), Evidence (cited figures), Consequence (what happens if unsolved), Direction (how this thesis addresses it).

### Research questions
Four to six. Each must be specific, answerable by a named part of the methodology, and tied to the problem statement. If you cannot say which method answers an RQ, rewrite the RQ.

### Objectives
Five to seven, each starting "To" plus an action verb (investigate, assess, identify, analyse, design, develop, evaluate, compare). Each must be SMART: specific, measurable, achievable, relevant, time-bound. Every objective maps to at least one RQ.

### Alignment table
Every RQ maps to an objective and a concrete method; every objective traces back to an RQ. Reference the table in the text, and update it whenever an RQ, objective or method changes.

### Literature review
- Thematic organisation by default. Each theme groups papers by idea, compares and contrasts them, states what they show together and where they disagree, and ends with what remains unsolved for this thesis.
- Synthesis, not a list. Wrong: "Study A found X. Study B found Y." Right: "Several studies report X [a], [b], although Y [c] found the opposite in a different sample."
- Coverage target: <number of papers your checklist asks for>. Flag it if the review falls short.

### Comparison table
Columns: Author(s) | Year | Method | Context | Key Finding | Limitation. The last row is "This Study". Each Limitation should connect to the gap this thesis addresses.

### Research gap (four steps)
Existing work (with citations), then limitations, then the specific gap, then this thesis's contribution with concrete specifics (method, numbers, setting).

### Methodology
All six components, each with numbers and named instruments: research approach with justification; data collection instruments; participants (who, how many, how selected); analysis method; tools and technologies; ethical considerations. Include a methodology flow figure.

### Transitions
Add a transition sentence at every chapter boundary, linking what was just established to what comes next.

## 6. LaTeX rules

- Floats use `[htbp]`, never `[H]` or `[h!]` everywhere.
- Put `\label{}` immediately after `\caption{}`. Prefixes: `fig:`, `tab:`, `eq:`, `sec:`, `chap:`.
- Reference with a tilde: `Figure~\ref{fig:x}`, `Table~\ref{tab:x}`, `Chapter~\ref{chap:x}`. Never hard-code chapter numbers.
- Table captions above tables; figure captions below figures.
- Diagrams in vector formats (.pdf, .eps), not .png or .jpg.
- No `\\` or `\newline` for spacing; use paragraph breaks or `\vspace{}`.
- References only through the `.bib` file and `\cite{}`. Do not hand-edit `report/references.bib` if it is exported from Zotero; add the paper in Zotero instead.
- Each file in `core/`, `chapters/` and `appendix/` starts with `% !TEX root = ../main.tex`.
- File names: lowercase, no spaces.
- The official template is in `report/university-template/`. Read it, never edit or build it. Check its front-matter order and chapter list before changing `report/main.tex`.
- Intended differences from the official template: <list them here, for example citation sorting or the image path>. Keep them.

## 7. Working modes

Pick the mode from the request.

Draft mode: write the requested section following sections 2 to 6. Mark every missing fact or citation inline. After the text, list in at most five lines anything the user must supply or verify.

Edit mode: change only what was asked. Return the changed paragraphs (or a diff for LaTeX), not the whole chapter, unless the user asks for the full version.

Review mode (when asked to check, review or grade a section): report problems in this format, most serious first, then a one-line verdict. Save longer reviews in `report/reviews/`.

```
[Rule] Location: "short quote of the problem" -> suggested fix
```

Group problems under: Rule breaks (section 2), Structure (section 5), Style (section 4), LaTeX (section 6). Do not rewrite the section in review mode unless asked.

## 8. Self-check before every thesis output

1. Supervisor instructions checked and followed.
2. Voice rule followed.
3. Punctuation and contraction rules followed.
4. Tense: future for planned work, present for general facts and literature, past only for completed work.
5. Every factual claim cited; nothing invented; gaps marked.
6. Facts match `CLAUDE.md` (title, numbers, RQs, objectives, status).
7. Problem statement has all five parts in order.
8. RQs: each answerable by a named method.
9. Objectives: "To" plus action verb, SMART, each mapped to an RQ.
10. Alignment table consistent with RQs, objectives and methods, and referenced in the text.
11. Literature review: thematic, synthesised, each theme ends with what remains unsolved.
12. Comparison table: correct columns, last row "This Study".
13. Gap: existing work, limitations, gap, contribution, with specifics.
14. Methodology: six components with numbers and instruments; flow figure present.
15. Transitions at chapter boundaries.
16. LaTeX rules in section 6 respected.
17. Style: none of the avoided words; claims match evidence; spelling consistent.

## 9. When the guidelines change

When new phase guidelines or a new rubric arrive, the supervisor's entries in `faculty_instructions.md` take effect immediately. Update this skill and `references/` so the rules stay in one place.

## 10. Working with other skills (optional)

If the team adds community skills (for example a LaTeX compile and lint skill or a prose-review skill), they rank below `faculty/faculty_instructions.md` and this skill. List here, per skill, what to use it for and which of its advice to ignore. Typical entries:

- A LaTeX skill aimed at conference papers: use it for compiling, linting and auditing; ignore its venue layout advice, because the university template stays.
- A prose-review skill aimed at other formats: keep its clutter, weak-verb, hollow-qualifier and cliche checks; ignore any push towards a voice or tense that section 2 forbids.
