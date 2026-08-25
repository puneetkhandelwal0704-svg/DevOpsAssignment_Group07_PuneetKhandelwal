# Unit 3 — VS Code Essentials

---

## Q. What is VS Code?

Visual Studio Code (VS Code) is a **free, open-source, lightweight source code editor** developed by Microsoft. It supports almost every programming language and is highly extensible through a large marketplace of extensions.

Key characteristics:
- Cross-platform (Windows, macOS, Linux)
- Built-in **Git integration**
- Built-in **integrated terminal**
- Rich **IntelliSense** (smart autocompletion)
- Massive **extension ecosystem**
- Free and open-source (built on Electron)

---

## Q. Core VS Code Interface

| Area | Purpose |
|---|---|
| **Activity Bar** (left icons) | Switch between Explorer, Search, Source Control, Run/Debug, Extensions |
| **Explorer** | File/folder browser for the open project |
| **Editor** | Where you write/edit code (supports split view, tabs) |
| **Integrated Terminal** | Run shell commands without leaving VS Code — `` Ctrl + ` `` |
| **Status Bar** (bottom) | Shows branch name, language mode, errors/warnings, line/column |
| **Command Palette** | Access every VS Code command — `Ctrl+Shift+P` |

---

## Q. Essential Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl+Shift+P` | Open Command Palette |
| `Ctrl+P` | Quick file open (go to file) |
| `` Ctrl+` `` | Toggle integrated terminal |
| `Ctrl+Shift+E` | Open Explorer panel |
| `Ctrl+Shift+G` | Open Source Control (Git) panel |
| `Ctrl+/` | Toggle line comment |
| `Ctrl+D` | Select next occurrence of current word (multi-cursor) |
| `Alt+Click` | Add a new cursor at click position |
| `Ctrl+Shift+F` | Search across entire project |
| `F2` | Rename symbol (refactor across file) |
| `Ctrl+B` | Toggle sidebar |
| `Ctrl+S` | Save file |

---

## Q. Git Integration in VS Code

VS Code has **Git built in** — no extension needed for basic operations.

Via the **Source Control panel** (`Ctrl+Shift+G`), you can:
- See changed files (modified, staged, untracked)
- Stage/unstage changes with a click (`+` / `-` icons)
- Write a commit message and commit
- Push / Pull / Sync directly from the UI
- View inline diffs (old vs new lines highlighted)
- Switch/create branches from the status bar (bottom-left branch name)
- Resolve merge conflicts with a visual 3-way merge editor

This means you can do an entire `add → commit → push` cycle without touching the terminal, though the integrated terminal is right there if you prefer CLI commands.

---

## Q. Useful Extensions for DevOps/Coding Workflows

| Extension | Purpose |
|---|---|
| **GitLens** | Supercharges Git integration — inline blame, commit history, comparisons |
| **Docker** | Manage Dockerfiles, images, and containers from VS Code |
| **Remote - SSH** | Edit code on a remote server as if it were local |
| **Live Share** | Real-time collaborative editing with teammates |
| **Prettier / ESLint** | Code formatting and linting |
| **YAML** | Syntax highlighting/validation for CI/CD config files (`.yml`) |
| **Python / Pylance** | Rich Python language support |

---

## Q. Workspace & Settings Concepts

| Concept | Description |
|---|---|
| **Workspace** | A folder (or set of folders) opened in VS Code, can have its own settings |
| **`.vscode/settings.json`** | Project-specific settings (formatting rules, exclusions, etc.) |
| **User Settings** | Global settings applied across all projects |
| **Extensions.json** | Recommends specific extensions for anyone opening the workspace |
| **Snippets** | Reusable code templates triggered by a short prefix |

---

## Q. Debugging in VS Code

1. Set a **breakpoint** by clicking to the left of a line number
2. Open the **Run and Debug** panel (`Ctrl+Shift+D`)
3. Select/create a debug configuration (`launch.json`)
4. Start debugging (`F5`) — execution pauses at breakpoints
5. Inspect variables, call stack, and use step controls (Step Over `F10`, Step Into `F11`, Continue `F5`)

---

## Q. Why VS Code Fits a DevOps Workflow

- One editor for code, YAML pipeline configs, Dockerfiles, and shell scripts
- Native Git panel removes the need to switch to CLI for routine commits
- Remote development extensions let you edit code directly on servers/containers
- Extension ecosystem covers nearly every tool in a DevOps toolchain (Docker, Kubernetes, Terraform, cloud CLIs, etc.)
