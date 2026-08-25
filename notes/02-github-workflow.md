# Unit 3 — GitHub Workflow

---

## Q. What is GitHub?

GitHub is a **cloud-based hosting platform for Git repositories**, owned by Microsoft. It adds a web interface and collaboration tooling on top of plain Git: pull requests, issue tracking, project boards, GitHub Actions (CI/CD), and social/discovery features (stars, forks, followers).

It is the most widely used Git hosting platform for **open-source** and public collaborative development.

---

## Q. Core GitHub Concepts

| Concept | Description |
|---|---|
| **Repository (Repo)** | A project's folder + full Git history, hosted on GitHub |
| **Fork** | Your own copy of someone else's repo, under your account |
| **Clone** | Downloading a repo (yours or forked) to your local machine |
| **Remote** | A pointer to the GitHub URL of a repo (commonly named `origin`) |
| **Pull Request (PR)** | A request to merge changes from one branch/fork into another, with review |
| **Issue** | A tracked task, bug report, or feature request |
| **Star** | Bookmarking/showing appreciation for a repo |
| **Watch** | Subscribing to notifications for a repo |

---

## Q. Typical Individual Contributor Workflow

1. **Clone** the repo — `git clone <repo-url>`
2. **Create a branch** for your change — `git checkout -b feature/login-page`
3. **Make changes** and commit — `git add .` → `git commit -m "Add login page"`
4. **Push the branch** — `git push origin feature/login-page`
5. **Open a Pull Request** on GitHub comparing your branch to `main`
6. **Get it reviewed** — teammates comment, request changes, or approve
7. **Merge** the PR into `main` once approved
8. **Delete the branch** (optional cleanup)

---

## Q. Open-Source Contribution Workflow (Fork-based)

Used when you don't have direct write access to a repo:

1. **Fork** the repository (creates a copy under your account)
2. **Clone your fork** locally — `git clone <your-fork-url>`
3. **Add the original repo as an "upstream" remote** — `git remote add upstream <original-url>`
4. **Create a branch**, make changes, commit
5. **Push to your fork** — `git push origin <branch>`
6. **Open a PR** from your fork's branch → the original repo's `main`
7. Maintainers review and merge

---

## Q. Pull Requests (PRs) — Best Practices

- Keep PRs **small and focused** on one change
- Write a **clear title and description** (what changed and why)
- Link related issues (e.g., `Closes #12`)
- Request reviewers; respond to review comments
- Ensure CI checks (tests, linting) pass before merge
- Use **"Squash and merge"** to keep history clean, or **"Merge commit"** to preserve full history — depends on team convention

---

## Q. GitHub Actions (CI/CD basics)

GitHub Actions is GitHub's built-in automation/CI-CD tool. Workflows are defined in YAML files inside `.github/workflows/`.

Example — a simple workflow that runs tests on every push:

```yaml
name: CI
on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Install dependencies
        run: npm install
      - name: Run tests
        run: npm test
```

Key terms:
| Term | Meaning |
|---|---|
| **Workflow** | An automated process defined in a YAML file |
| **Event** (`on:`) | What triggers the workflow (push, PR, schedule, etc.) |
| **Job** | A set of steps that run on the same runner/machine |
| **Step** | An individual task/command within a job |
| **Runner** | The virtual machine that executes the job |

---

## Q. Other Important GitHub Features

| Feature | Purpose |
|---|---|
| **README.md** | Landing page/documentation for a repo, rendered automatically |
| **Issues** | Track bugs, feature requests, tasks; supports labels, assignees, milestones |
| **Projects** | Kanban-style boards for organizing issues/PRs |
| **Releases** | Tagged, packaged versions of the project (often with changelogs) |
| **GitHub Pages** | Free static site hosting directly from a repo |
| **Branch Protection Rules** | Enforce PR reviews/CI checks before merging into protected branches like `main` |
| **.gitignore templates** | GitHub can auto-generate language-specific ignore files on repo creation |

---

## Q. GitHub CLI (`gh`)

A command-line tool to interact with GitHub without leaving the terminal.

| Command | Purpose |
|---|---|
| `gh repo create` | Create a new repo |
| `gh repo clone <repo>` | Clone a repo |
| `gh pr create` | Open a pull request |
| `gh pr list` | List open PRs |
| `gh issue create` | Create an issue |

---

## Q. GitHub vs Git — Recap

Git is the version control *tool*; GitHub is a *platform* that hosts Git repositories in the cloud and layers on collaboration features (PRs, Issues, Actions, code review) that plain Git does not provide on its own.
