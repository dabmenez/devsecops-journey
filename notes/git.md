# 🗃️ Git - Version Control

## 📌 What is Git?

**Git** is a **version control system** that tracks changes in files and allows multiple developers to collaborate on software projects efficiently.

It helps teams:
- Manage code across time and contributors
- Roll back to previous versions
- Merge and branch for experimentation or parallel work

---

## ⚙️ How it works

- All project files and change history are stored in a **repository** (aka *repo*).
- Git operations are typically performed via the **CLI** using the `git` command.
- Hosted services such as **GitHub**, **GitLab**, **Bitbucket**, **Azure Repos**, and **AWS CodeCommit** provide cloud-based repository management.

---

## 🔧 Common Git Commands

| Command | Description |
|---------|-------------|
| `git clone` | Clone a remote repository to your local machine |
| `git status` | Check the current status of your working directory |
| `git switch --create <branchname>` | Create and switch to a new branch |
| `git add <file>` | Stage changes (files or directories) for commit |
| `git commit -m "message"` | Commit the staged changes with a message |
| `git push` | Push local commits to a remote repository |

> 💡 These are just the basics — Git is a powerful tool with many advanced workflows.

---

## 🧠 Why Git Matters in DevSecOps

In DevSecOps pipelines:
- Git is the **source of truth** for all code and configuration.
- Security scanning tools (SAST, SCA, Secrets Detection) often integrate directly with Git to analyze commits.
- Automation tools trigger CI/CD pipelines based on Git events (like push, merge, pull request).

---