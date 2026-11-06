# Setup guide

Part A is done once, by one person (the repo owner). Everyone does Part B. Steps list Windows, Mac and Linux where they differ.

---

## Part A: create the repo (one person, once)

1. Fill in the `<placeholders>` in `CLAUDE.md`, `faculty/`, `brain/` and `.claude/skills/thesis-writing/SKILL.md`. Put your department's guidelines in `guidelines/` and the official LaTeX template in `report/university-template/`.
2. On GitHub, create a new **private** repository named `thesis`. Leave "Add a README" unticked.
3. Open a terminal inside the workspace folder and run:

   ```
   git init -b main
   git add -A
   git commit -m "Initial thesis workspace"
   git remote add origin https://github.com/<your-username>/thesis.git
   git push -u origin main
   ```

   Use the terminal rather than GitHub's drag-and-drop upload. The upload page can skip hidden files such as `.gitignore`, `.vscode/` and `.claude/`, and those matter.
4. In the repo on GitHub, open Settings, then Collaborators, and add every teammate and the supervisor.
5. Ask everyone to click "Watch" on the repo so the supervisor's edits show up as notifications.

---

## Part B: everyone

### 1. Git

- Windows: install Git for Windows from git-scm.com. Keep the default options. Claude Code on Windows also relies on it.
- Mac: run `git --version` in Terminal. If Git is missing, macOS offers to install the developer tools.
- Linux: install `git` from your package manager.

Then tell Git who you are (once per machine):

```
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Clone the repo:

```
git clone https://github.com/<owner>/thesis.git
```

### 2. MiKTeX (the LaTeX compiler)

Everyone uses **MiKTeX**, installed for your own account, so it never needs admin rights to install or repair packages.

- Windows: download the installer from miktex.org/download and run it. Choose **"Install MiKTeX only for me"** (not "for all users") and set "Install missing packages on-the-fly" to **Yes**. Then install Strawberry Perl from strawberryperl.com, because latexmk needs Perl and MiKTeX does not include it.
- Mac and Linux: follow the instructions for your system on miktex.org/download, again as a per-user installation. Perl is already part of macOS and Linux.

When it finishes, open MiKTeX Console, go to Updates, and install all updates. Then open a new terminal and check:

```
pdflatex --version
latexmk -v
```

Post the MiKTeX version from the first line in the group chat so everyone can confirm they match.

### 3. VS Code

1. Install VS Code from code.visualstudio.com.
2. Open the `thesis` folder (File, then Open Folder).
3. Accept the recommended extensions: LaTeX Workshop (build and PDF preview), LTeX+ (grammar and spelling) and Claude Code.

The shared settings in `.vscode/` make LaTeX Workshop build with latexmk every time you save. The PDF appears in `report/build/`, and Ctrl+Alt+V (Cmd+Option+V on Mac) opens the preview. Change `ltex.language` in `.vscode/settings.json` if your thesis does not use British English.

### 4. Claude Code

1. Open the Claude Code panel in VS Code and sign in with your Claude account. You need a paid Claude plan that includes Claude Code.
2. Claude Code reads `CLAUDE.md` and the `thesis-writing` skill automatically, and `CLAUDE.md` tells it to read your brain in `brain/`. Say who you are at the start of a session ("I'm <Name>") so it picks the right one.
3. End each session with "wrap up". Claude Code adds the log entry to `logs/<you>.md` and asks whether your brain needs an update.

### 5. claude.ai Project

For chats on the web or phone:

1. In your thesis Project, open the Project knowledge, click "+", and choose GitHub.
2. Pick this repo and select `CLAUDE.md`, your own `brain/<You>_Brain.md`, `faculty/`, `logs/` and `guidelines/`. Leave out `report/` and `archive/` unless you need them, to save context.
3. Delete any brain or handoff file you uploaded by hand, so Claude reads only the synced version.
4. Skills are per account in claude.ai. Add the `thesis-writing` skill in claude.ai's settings if you want it on the web too.
5. The sync is not automatic. Click "Sync now" before each session.

### 6. Zotero and references (one owner)

Better BibTeX rewrites the whole `.bib` file on every export, so only one person exports.

1. Create a Zotero group library for the team and invite everyone. Everyone adds papers there.
2. Everyone installs the Better BibTeX plugin for Zotero, so citation keys match.
3. The owner only: right-click the group library, choose Export Library, pick "Better BibTeX", tick "Keep updated", and save to `report/references.bib`.
4. Nobody edits `references.bib` by hand. Fix entries in Zotero instead.

Record the owner in the Decision log in `CLAUDE.md`.

### 7. Optional: community skills

Community skills can help, for example a LaTeX compile and lint skill, or a prose-review skill. Before committing one:

- Put it in its own folder, `.claude/skills/<name>/SKILL.md`, or Claude Code will not load it.
- Read the whole `SKILL.md`. Check whether it runs scripts, installs packages or uses the network, and check its license.
- Rank it below your own `thesis-writing` skill, and list in that skill which of its advice to ignore (see section 10 of `thesis-writing/SKILL.md`).

---

## Git survival kit

```
git pull                       get teammates' changes (do this first)
git status                     see what you changed
git add -A                     stage everything
git commit -m "message"        save a snapshot
git push                       send it to GitHub
```

If `git pull` reports a conflict, the file shows both versions between `<<<<<<<` and `>>>>>>>` markers. Keep both, then ask Claude Code: "Resolve the merge conflict in CLAUDE.md, keeping both sides' content." Check the result, then `git add -A`, `git commit` and `git push`.
