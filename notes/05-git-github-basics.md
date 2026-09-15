# 05 - Git & GitHub Basics

Notes on version control and collaboration, following on from VS Code essentials.

## What is Git?
Git is a version control system — it tracks every change made to a project's
files over time. Instead of saving files as `final_v2_FINAL.docx`, Git lets
you save a "snapshot" (called a commit) any time you want, with a message
explaining what changed.

Key benefits:
- **Full history** — every commit is saved, so nothing is ever truly lost
- **Works offline** — Git runs locally on your machine, no internet needed
- **Branching** — try new ideas without breaking the working code
- **Team-friendly** — multiple people can work on the same project safely

## Local vs Remote
- **Local repository** — the copy of the project on your own computer
- **Remote repository** — the shared copy hosted on GitHub, that the whole
  team pushes to and pulls from

## Core Git Commands
| Command | Purpose |
|---|---|
| `git init` | Start tracking a folder |
| `git add` | Stage changes to be saved |
| `git commit -m "msg"` | Save a snapshot with a message |
| `git push` | Upload commits to GitHub |
| `git pull` | Download the latest changes |
| `git branch` | Create/list branches |

## What is GitHub?
GitHub is a website that hosts Git repositories in the cloud. It adds
features on top of plain Git:
- A shared home for the repo that every teammate can access
- **Pull Requests (PRs)** — a way to propose your branch's changes and have
  the team review them before merging
- **Issues** — track bugs, tasks, and feature requests
- **GitHub Actions** — automatically build/test code on every push

## The Branch → PR → Merge Workflow
This is exactly how our team is contributing to this project:

1. Create your own branch off `main`
2. Make a small, focused change
3. Commit and push that change to your branch
4. Open a Pull Request into `main`
5. A teammate reviews it
6. It gets merged into `main`

This keeps `main` always in a working state — nobody's unfinished or broken
work lands there directly.

## A Quick Note on GitLab
GitLab works on the same core idea as GitHub (Git hosting + collaboration),
but bundles CI/CD pipelines natively into the platform, whereas GitHub adds
this through the separate GitHub Actions feature. Many companies choose
between the two based on whether they want an all-in-one platform (GitLab)
or the larger open-source ecosystem (GitHub).
