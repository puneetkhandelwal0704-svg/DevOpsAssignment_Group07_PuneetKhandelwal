# Unit 3 — GitLab & CI/CD

---

## Q. What is GitLab?

GitLab is a **web-based DevOps platform** that provides Git repository hosting *plus* an integrated suite of tools covering the entire software development lifecycle — planning, source control, CI/CD, security scanning, and deployment — all in a single application.

Unlike GitHub (which relies more on third-party integrations/marketplace apps), GitLab aims to be an **all-in-one DevOps platform** out of the box.

It's available as:
- **GitLab.com** — GitLab's own hosted SaaS platform
- **Self-hosted GitLab** — companies can run GitLab on their own servers for full control (common in enterprises with strict compliance needs)

---

## Q. GitLab vs GitHub — Key Differences

| Feature | GitHub | GitLab |
|---|---|---|
| CI/CD | GitHub Actions (added later) | Built-in from the start (`.gitlab-ci.yml`) |
| Self-hosting | GitHub Enterprise Server (paid) | Free self-hosted Community Edition available |
| Issue/Project Mgmt | Issues + Projects (boards) | Issues + built-in epics, milestones, boards |
| Container Registry | Available | Built-in, tightly integrated |
| Philosophy | Hub for open-source collaboration | Single application for the whole DevOps lifecycle |

---

## Q. GitLab Flow (Branching Strategy)

GitLab promotes a workflow similar to GitHub's, centered on **Merge Requests (MRs)** — GitLab's term for what GitHub calls a Pull Request.

1. Create a feature branch off `main`
2. Commit changes
3. Push the branch to GitLab
4. Open a **Merge Request (MR)**
5. Pipeline runs automatically (CI/CD checks)
6. Team reviews and approves
7. Merge into `main`

---

## Q. GitLab CI/CD — Core Concept

GitLab CI/CD is configured through a single file at the root of the repo: **`.gitlab-ci.yml`**

This file defines a **pipeline** made up of **stages**, and each stage contains one or more **jobs**.

Example `.gitlab-ci.yml`:

```yaml
stages:
  - build
  - test
  - deploy

build-job:
  stage: build
  script:
    - echo "Building the project..."
    - npm install

test-job:
  stage: test
  script:
    - echo "Running tests..."
    - npm test

deploy-job:
  stage: deploy
  script:
    - echo "Deploying to server..."
  only:
    - main
```

---

## Q. GitLab CI/CD Key Terms

| Term | Meaning |
|---|---|
| **Pipeline** | The full automated process (build → test → deploy) triggered by a commit/push |
| **Stage** | A phase in the pipeline (e.g., `build`, `test`, `deploy`) — stages run in order |
| **Job** | A single unit of work within a stage (runs in parallel with other jobs in the same stage) |
| **Runner** | The agent/machine that actually executes the jobs |
| **Artifact** | Files produced by a job (e.g., build output) that can be passed to later stages or downloaded |
| **`.gitlab-ci.yml`** | The YAML file where the entire pipeline is defined |

---

## Q. Merge Requests (MRs) in GitLab

Functionally equivalent to GitHub's Pull Requests:
- Propose merging a source branch into a target branch
- Trigger CI pipelines automatically
- Support inline code comments/discussions
- Can require **approvals** before merging
- Can show pipeline pass/fail status directly on the MR

---

## Q. Other Notable GitLab Features

| Feature | Purpose |
|---|---|
| **Auto DevOps** | Automatically configures build/test/deploy pipelines with minimal setup |
| **Container Registry** | Store and manage Docker images per project |
| **GitLab Pages** | Static site hosting, similar to GitHub Pages |
| **Epics & Milestones** | Higher-level planning above individual issues |
| **Security/Dependency Scanning** | Built-in vulnerability and dependency checks in the pipeline |
| **Environments** | Track what's deployed where (staging, production, etc.) |

---

## Q. Why Learn Both GitHub and GitLab?

Both are built on the same underlying tool (Git), so core commands (`clone`, `commit`, `push`, `pull`, `branch`, `merge`) are identical. The differences are mainly in:
- **Terminology** (Pull Request vs Merge Request)
- **CI/CD approach** (Actions/YAML in `.github/workflows/` vs `.gitlab-ci.yml`)
- **Platform philosophy** (marketplace/ecosystem vs all-in-one)

Understanding both makes you adaptable across different company toolchains.
