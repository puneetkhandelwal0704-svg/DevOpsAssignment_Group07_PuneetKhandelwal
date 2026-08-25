# Coding Tools Cheatsheet — Git, GitHub, GitLab, VS Code

---

## Git — Command Reference

| Category | Command | Purpose |
|---|---|---|
| Setup | `git init` | Initialize a new repo |
| Setup | `git clone <url>` | Copy a remote repo locally |
| Setup | `git config --global user.name "Name"` | Set global username |
| Setup | `git config --global user.email "mail"` | Set global email |
| Status | `git status` | See changed/staged files |
| Status | `git log --oneline` | Compact commit history |
| Status | `git diff` | Show unstaged changes |
| Stage/Commit | `git add <file>` / `git add .` | Stage file(s) |
| Stage/Commit | `git commit -m "msg"` | Commit staged changes |
| Stage/Commit | `git commit -am "msg"` | Stage tracked files + commit in one step |
| Branching | `git branch` | List branches |
| Branching | `git checkout -b <name>` | Create + switch to new branch |
| Branching | `git switch <name>` | Switch branch |
| Branching | `git merge <branch>` | Merge branch into current |
| Branching | `git branch -d <name>` | Delete branch |
| Remote | `git remote -v` | List remotes |
| Remote | `git push origin <branch>` | Push commits |
| Remote | `git pull origin <branch>` | Pull + merge remote changes |
| Remote | `git fetch` | Download without merging |
| Undo | `git restore <file>` | Discard local changes |
| Undo | `git reset --soft HEAD~1` | Undo last commit, keep changes |
| Undo | `git reset --hard HEAD~1` | Undo last commit, discard changes |
| Undo | `git revert <commit>` | Safely undo a pushed commit |

---

## GitHub — Quick Reference

| Term | Meaning |
|---|---|
| Repo | Hosted project + Git history |
| Fork | Personal copy of someone else's repo |
| Pull Request (PR) | Request to merge a branch, with review |
| Issue | Tracked bug/task/feature request |
| GitHub Actions | Built-in CI/CD, config in `.github/workflows/*.yml` |
| Branch Protection | Rules requiring review/CI pass before merge to `main` |

**Typical flow:** `clone → branch → commit → push → open PR → review → merge`

**GitHub Actions minimal YAML:**
```yaml
on: [push]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: npm test
```

---

## GitLab — Quick Reference

| Term | Meaning |
|---|---|
| Merge Request (MR) | GitLab's equivalent of a Pull Request |
| Pipeline | Full CI/CD run defined in `.gitlab-ci.yml` |
| Stage | Ordered phase in a pipeline (build/test/deploy) |
| Job | Task within a stage |
| Runner | Machine/agent executing jobs |
| Auto DevOps | Zero-config CI/CD setup |

**Minimal `.gitlab-ci.yml`:**
```yaml
stages: [build, test, deploy]

build-job:
  stage: build
  script: [echo "building"]

test-job:
  stage: test
  script: [echo "testing"]
```

**GitHub vs GitLab naming:**

| GitHub | GitLab |
|---|---|
| Pull Request | Merge Request |
| GitHub Actions | GitLab CI/CD |
| `.github/workflows/` | `.gitlab-ci.yml` |
| GitHub Pages | GitLab Pages |

---

## VS Code — Shortcut Reference

| Shortcut | Action |
|---|---|
| `Ctrl+Shift+P` | Command Palette |
| `Ctrl+P` | Quick open file |
| `` Ctrl+` `` | Toggle terminal |
| `Ctrl+Shift+G` | Source Control panel |
| `Ctrl+Shift+E` | Explorer panel |
| `Ctrl+/` | Comment/uncomment line |
| `Ctrl+D` | Select next matching word |
| `Alt+Click` | Multi-cursor |
| `Ctrl+Shift+F` | Project-wide search |
| `F2` | Rename symbol |
| `F5` | Start debugging |

**Git in VS Code:** Source Control panel (`Ctrl+Shift+G`) → stage (`+`) → write message → commit → Sync/Push, all without leaving the editor.

**Useful extensions:** GitLens, Docker, Remote-SSH, Prettier/ESLint, YAML.

---

## One-Line Summary

- **Git** = the version control tool (local, offline-capable)
- **GitHub** = cloud platform for hosting Git repos + PRs + Actions (CI/CD) + Issues
- **GitLab** = cloud/self-hosted all-in-one DevOps platform with built-in CI/CD (MRs + Pipelines)
- **VS Code** = the editor tying it all together, with native Git support and terminal access
