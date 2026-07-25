# Essential Git Command Cheat Sheet

> **A comprehensive reference to the most commonly used Git commands for software development, DevOps workflows, and technical interview preparation.**

This chapter is designed as a **quick reference guide**. While later chapters explain concepts in detail, this document helps you quickly find the right Git command along with its purpose and real-world use case.

---

# 📖 Introduction

Git provides hundreds of commands, but in day-to-day development, only a small set of commands are used regularly.

Whether you're:

* Building a new project
* Collaborating with a team
* Fixing bugs
* Managing branches
* Deploying applications

these commands form the foundation of almost every Git workflow.

---

# 🚀 Repository Setup

| Command                      | Purpose                         | Real-World Use Case           |
| ---------------------------- | ------------------------------- | ----------------------------- |
| `git init`                   | Initialize a new Git repository | Start tracking a new project  |
| `git clone <repository-url>` | Clone an existing repository    | Join an existing team project |

---

# 📋 Repository Inspection

| Command                | Purpose                            | Real-World Use Case                         |
| ---------------------- | ---------------------------------- | ------------------------------------------- |
| `git status`           | View the current repository status | Check modified, staged, and untracked files |
| `git diff`             | View unstaged changes              | Review changes before staging               |
| `git diff --staged`    | View staged changes                | Verify what will be committed               |
| `git log`              | View complete commit history       | Review previous commits                     |
| `git log --oneline`    | Display a compact commit history   | Quickly inspect project history             |
| `git show <commit-id>` | Display commit details             | Review a specific commit                    |

---

# 📦 Staging Changes

| Command                       | Purpose                          | Real-World Use Case                    |
| ----------------------------- | -------------------------------- | -------------------------------------- |
| `git add <file>`              | Stage a specific file            | Commit only selected changes           |
| `git add .`                   | Stage all new and modified files | Prepare all project changes for commit |
| `git restore --staged <file>` | Remove a file from staging       | Undo accidental staging                |

---

# 💾 Commit Management

| Command                   | Purpose                  | Real-World Use Case                           |
| ------------------------- | ------------------------ | --------------------------------------------- |
| `git commit -m "message"` | Create a new commit      | Save completed work                           |
| `git commit --amend`      | Modify the latest commit | Fix commit message or include forgotten files |

---

# 🌿 Branch Management

| Command                    | Purpose                       | Real-World Use Case                          |
| -------------------------- | ----------------------------- | -------------------------------------------- |
| `git branch`               | List local branches           | Check available branches                     |
| `git branch <branch-name>` | Create a new branch           | Start a new feature                          |
| `git switch <branch>`      | Switch branches               | Continue work on another branch              |
| `git switch -c <branch>`   | Create and switch to a branch | Begin a new feature immediately              |
| `git checkout <branch>`    | Switch branches (legacy)      | Older Git workflow                           |
| `git checkout -b <branch>` | Create and switch (legacy)    | Compatible with older Git versions           |
| `git merge <branch>`       | Merge another branch          | Merge completed work into the current branch |
| `git branch -d <branch>`   | Delete a merged branch        | Clean up completed feature branches          |

---

# 🌐 Remote Repository Commands

| Command                                  | Purpose                             | Real-World Use Case               |
| ---------------------------------------- | ----------------------------------- | --------------------------------- |
| `git remote -v`                          | View configured remote repositories | Verify GitHub connection          |
| `git remote add origin <repository-url>` | Add a remote repository             | Connect local project to GitHub   |
| `git push -u origin main`                | First push to GitHub                | Upload initial project            |
| `git push`                               | Push commits                        | Share latest changes              |
| `git pull`                               | Fetch and merge remote changes      | Synchronize with teammates        |
| `git fetch`                              | Download remote changes only        | Review updates before merging     |
| `git clone <repository-url>`             | Copy an existing repository         | Start working on a shared project |

---

# 📦 Git Stash Commands

| Command           | Purpose                         | Real-World Use Case             |
| ----------------- | ------------------------------- | ------------------------------- |
| `git stash`       | Save uncommitted changes        | Switch tasks without committing |
| `git stash list`  | View saved stashes              | Check temporary work            |
| `git stash pop`   | Restore and remove latest stash | Continue previous work          |
| `git stash apply` | Restore without deleting stash  | Reuse the same stash later      |
| `git stash drop`  | Delete a specific stash         | Remove unnecessary stash        |
| `git stash clear` | Delete all stashes              | Clean the stash list            |

---

# 🏷️ Git Tag Commands

| Command                        | Purpose                  | Real-World Use Case               |
| ------------------------------ | ------------------------ | --------------------------------- |
| `git tag`                      | View all tags            | Check release versions            |
| `git tag v1.0`                 | Create a lightweight tag | Mark a quick milestone            |
| `git tag -a v1.0 -m "Release"` | Create an annotated tag  | Mark an official software release |
| `git show v1.0`                | View tag details         | Review release information        |
| `git push origin v1.0`         | Push a specific tag      | Publish a release                 |
| `git push origin --tags`       | Push all tags            | Upload every release tag          |
| `git tag -d v1.0`              | Delete a local tag       | Remove an incorrect tag           |

---

# ⚙️ Git Configuration

| Command                                            | Purpose                  | Real-World Use Case             |
| -------------------------------------------------- | ------------------------ | ------------------------------- |
| `git config --list`                                | Display all Git settings | Verify current configuration    |
| `git config --global user.name "Your Name"`        | Set username             | Configure author information    |
| `git config --global user.email "you@example.com"` | Set email                | Configure commit identity       |
| `git config --global init.defaultBranch main`      | Set default branch       | Use `main` for new repositories |

---

# 🔄 Undo Changes

| Command                       | Purpose                                             | Real-World Use Case                        |
| ----------------------------- | --------------------------------------------------- | ------------------------------------------ |
| `git restore <file>`          | Discard unstaged changes                            | Undo local edits                           |
| `git restore --staged <file>` | Remove staged changes                               | Fix accidental staging                     |
| `git reset --soft HEAD~1`     | Undo last commit and keep changes staged            | Correct a recent commit                    |
| `git reset --mixed HEAD~1`    | Undo last commit and unstage changes                | Rework staged files                        |
| `git reset --hard HEAD~1`     | Remove commit and discard changes                   | Permanently discard unwanted work          |
| `git revert <commit-id>`      | Create a new commit that reverses a previous commit | Safely undo changes in shared repositories |

> **⚠️ Warning:** Use `git reset --hard` carefully. It permanently removes uncommitted work.

---

# ⭐ Daily Git Workflow

```text
Create Project
      │
      ▼
git init
      │
      ▼
Create / Modify Files
      │
      ▼
git status
      │
      ▼
git add .
      │
      ▼
git commit -m "message"
      │
      ▼
git branch
      │
      ▼
git switch feature-branch
      │
      ▼
Development
      │
      ▼
git merge
      │
      ▼
git push
```

---

# 🎯 Most Frequently Used Commands

```bash
git status
git add .
git commit -m "message"
git log --oneline
git switch -c feature-name
git switch main
git merge feature-name
git push
git pull
git fetch
git stash
git tag
```

---

# 💡 Best Practices

* Check `git status` before every commit.
* Review changes using `git diff`.
* Write clear and meaningful commit messages.
* Commit small, logical changes frequently.
* Pull the latest changes before pushing.
* Create feature branches instead of working directly on `main`.
* Never commit sensitive files such as `.env`, passwords, or API keys.

---

# ❌ Common Mistakes

| Mistake                                                   | Better Practice                                    |
| --------------------------------------------------------- | -------------------------------------------------- |
| Working directly on `main`                                | Create feature branches for new work               |
| Forgetting to pull before pushing                         | Synchronize with the remote repository first       |
| Committing everything blindly with `git add .`            | Review changes using `git status` and `git diff`   |
| Using vague commit messages like "update"                 | Write descriptive commit messages                  |
| Using `git reset --hard` without understanding its impact | Use it only when you're sure data can be discarded |

---

# 📌 Command Summary

| Category              | Frequently Used Commands                          |
| --------------------- | ------------------------------------------------- |
| Repository Setup      | `git init`, `git clone`                           |
| Repository Inspection | `git status`, `git diff`, `git log`               |
| Staging               | `git add`, `git restore --staged`                 |
| Commits               | `git commit`, `git commit --amend`                |
| Branches              | `git branch`, `git switch`, `git merge`           |
| Remote Repository     | `git push`, `git pull`, `git fetch`, `git remote` |
| Stash                 | `git stash`, `git stash pop`, `git stash apply`   |
| Tags                  | `git tag`, `git show`                             |
| Undo                  | `git restore`, `git reset`, `git revert`          |
| Configuration         | `git config`                                      |

---

## 🚀 What's Next?

Now that you're familiar with the most commonly used Git commands, it's time to use them in a real project.

In the next chapter, you'll build a project from scratch and follow the complete **Single User Git Workflow**, learning how these commands work together to manage a project's lifecycle—from initialization to commits and version history.
