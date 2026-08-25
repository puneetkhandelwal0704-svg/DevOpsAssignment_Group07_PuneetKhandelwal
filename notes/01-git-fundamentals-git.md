# Unit 3 — Git Fundamentals

---

## Q. What is Git?

Git is a **distributed version control system (DVCS)** that tracks changes to files over time, letting multiple people work on the same project without overwriting each other's work.

Unlike older centralized systems (e.g., SVN), every developer has a **full copy of the repository** (including its entire history) on their local machine — not just the latest snapshot.

Key benefits:
1. **Tracks history** — every change is recorded, so you can go back to any previous version
2. **Enables collaboration** — multiple people can work on the same codebase without conflicts
3. **Supports branching** — experiment safely without touching the main code
4. **Works offline** — since the full history is local, you don't need network access to commit or view history

---

## Q. Git Architecture — The Three Areas

Git manages files across three main areas:

| Area | Description |
|---|---|
| **Working Directory** | The actual files on your disk that you edit |
| **Staging Area (Index)** | A holding zone for changes you plan to commit next (`git add`) |
| **Repository (.git folder)** | Where committed history is permanently stored (`git commit`) |

Flow: `Working Directory → (git add) → Staging Area → (git commit) → Repository`

---

## Q. Basic Git Workflow

1. **Initialize** a repo — `git init`
2. **Check status** of files — `git status`
3. **Stage** changes — `git add <file>` or `git add .`
4. **Commit** changes — `git commit -m "message"`
5. **View history** — `git log`
6. **Push** to a remote — `git push`
7. **Pull** latest changes — `git pull`

---

## Q. Core Git Commands

| Command | Purpose |
|---|---|
| `git init` | Create a new local repository |
| `git clone <url>` | Copy a remote repository to your machine |
| `git status` | Show changed/staged/untracked files |
| `git add <file>` | Stage a specific file |
| `git add .` | Stage all changed files |
| `git commit -m "msg"` | Save staged changes with a message |
| `git log` | View commit history |
| `git log --oneline` | Compact one-line-per-commit history |
| `git diff` | Show unstaged changes |
| `git diff --staged` | Show staged changes not yet committed |
| `git remote -v` | List remote repositories linked to this repo |
| `git push origin <branch>` | Upload local commits to remote |
| `git pull origin <branch>` | Download and merge remote changes |
| `git fetch` | Download remote changes without merging |

---

## Q. Branching in Git

A **branch** is an independent line of development. The default branch is usually `main` (or `master`).

| Command | Purpose |
|---|---|
| `git branch` | List all local branches |
| `git branch <name>` | Create a new branch |
| `git checkout <name>` | Switch to a branch |
| `git checkout -b <name>` | Create and switch in one step |
| `git switch <name>` | Modern alternative to checkout for switching |
| `git merge <branch>` | Merge another branch into the current one |
| `git branch -d <name>` | Delete a branch (safe delete) |

**Why branch?** So you can build a feature, fix a bug, or experiment in isolation without breaking the working `main` branch. Once tested, it's merged back in.

---

## Q. Merge Conflicts

A **merge conflict** happens when Git can't automatically combine changes — usually because two branches edited the same line(s) of a file differently.

Git marks the conflicting section in the file like this:

```
<<<<<<< HEAD
your current branch's version
=======
the incoming branch's version
>>>>>>> feature-branch
```

**Resolving a conflict:**
1. Open the file and manually edit it to keep the correct content
2. Remove the `<<<<<<<`, `=======`, `>>>>>>>` markers
3. Stage the resolved file — `git add <file>`
4. Complete the merge — `git commit`

---

## Q. Undoing Changes

| Command | Effect |
|---|---|
| `git restore <file>` | Discard unstaged changes in working directory |
| `git restore --staged <file>` | Unstage a file (keep the edits) |
| `git reset --soft HEAD~1` | Undo last commit, keep changes staged |
| `git reset --hard HEAD~1` | Undo last commit, discard changes completely |
| `git revert <commit>` | Create a new commit that undoes a previous one (safe for shared history) |

**Rule of thumb:** Use `revert` on shared/pushed branches (doesn't rewrite history). Use `reset` only on local/unpushed commits.

---

## Q. .gitignore

A `.gitignore` file tells Git which files/folders to **never track** — e.g., build artifacts, secrets, `node_modules/`, `.env` files, IDE settings.

Example `.gitignore`:
```
node_modules/
*.log
.env
__pycache__/
.vscode/
```

---

## Q. Git vs GitHub vs GitLab — Quick Distinction

| | Git | GitHub / GitLab |
|---|---|---|
| What it is | Version control **tool** (software) | Cloud **hosting platform** for Git repos |
| Runs | Locally on your machine | On a remote server (cloud or self-hosted) |
| Purpose | Track changes, branching, merging | Collaboration, code review, CI/CD, issue tracking |

Git is the engine; GitHub/GitLab are platforms built around Git that add collaboration and automation features on top.
