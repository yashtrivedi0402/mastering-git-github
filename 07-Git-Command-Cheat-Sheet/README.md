# Essential Git Command Cheat Sheet

> **A quick reference to the most commonly used Git commands in day-to-day development and DevOps workflows.**

This cheat sheet is designed for quick revision. Detailed explanations and practical usage are covered in the following chapters.

---

# 🚀 Repository Setup

| Command                | Description                                        |
| ---------------------- | -------------------------------------------------- |
| `git init`             | Initialize a new Git repository.                   |
| `git clone <repo-url>` | Clone an existing repository from a remote source. |

---

# 📋 Repository Status

| Command             | Description                                                       |
| ------------------- | ----------------------------------------------------------------- |
| `git status`        | Show the current state of the working directory and staging area. |
| `git diff`          | Display unstaged changes.                                         |
| `git diff --staged` | Display staged changes waiting to be committed.                   |

---

# 📦 Staging Changes

| Command                       | Description                          |
| ----------------------------- | ------------------------------------ |
| `git add <file>`              | Stage a specific file.               |
| `git add .`                   | Stage all modified and new files.    |
| `git restore --staged <file>` | Remove a file from the staging area. |

---

# 💾 Commits

| Command                   | Description                         |
| ------------------------- | ----------------------------------- |
| `git commit -m "message"` | Create a new commit with a message. |
| `git commit --amend`      | Modify the most recent commit.      |

---

# 📜 Commit History

| Command                | Description                        |
| ---------------------- | ---------------------------------- |
| `git log`              | Display complete commit history.   |
| `git log --oneline`    | Display a concise commit history.  |
| `git show <commit-id>` | Show details of a specific commit. |

---

# 🌐 Remote Repository

| Command                | Description                                            |
| ---------------------- | ------------------------------------------------------ |
| `git remote -v`        | View configured remote repositories.                   |
| `git push origin main` | Push local commits to the remote repository.           |
| `git pull origin main` | Download and merge changes from the remote repository. |
| `git fetch`            | Download remote changes without merging them.          |

---

# 🌿 Branching

| Command                    | Description                             |
| -------------------------- | --------------------------------------- |
| `git branch`               | List all local branches.                |
| `git branch <branch-name>` | Create a new branch.                    |
| `git checkout <branch>`    | Switch to another branch.               |
| `git checkout -b <branch>` | Create and switch to a new branch.      |
| `git merge <branch>`       | Merge a branch into the current branch. |

---

# ⚙️ Configuration

| Command                                           | Description                             |
| ------------------------------------------------- | --------------------------------------- |
| `git config --list`                               | Display all Git configuration settings. |
| `git config --global user.name "Your Name"`       | Set the global username.                |
| `git config --global user.email "your@email.com"` | Set the global email address.           |

---

# 🧹 Undo Changes

| Command                       | Description                                        |
| ----------------------------- | -------------------------------------------------- |
| `git restore <file>`          | Discard unstaged changes in a file.                |
| `git restore --staged <file>` | Unstage a staged file.                             |
| `git reset --soft HEAD~1`     | Undo the last commit while keeping changes staged. |
| `git reset --hard HEAD~1`     | Remove the last commit and discard its changes.    |

> **⚠️ Warning:** Use `git reset --hard` carefully. It permanently discards uncommitted changes.

---

# ⭐ Most Frequently Used Commands

These are the commands you'll use almost every day:

```bash
git status
git add .
git commit -m "message"
git log --oneline
git push origin main
git pull origin main
git branch
git checkout -b feature-name
git merge feature-name
```

---

# 💡 Pro Tips

* Check `git status` before every commit.
* Write meaningful commit messages.
* Commit small, logical changes instead of one large commit.
* Pull the latest changes before pushing to avoid conflicts.
* Review changes using `git diff` before staging them.

---

## 🚀 What's Next?

Now that you're familiar with the most commonly used Git commands, let's put them into practice.

In the next chapter, we'll build a project from scratch and understand the complete **Single User Git Workflow** using `git init`, `git status`, `git add`, `git commit`, and `git log` step by step.
