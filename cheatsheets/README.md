# Git & GitHub Cheat Sheet 🚀

> **A one-page reference for the most commonly used Git & GitHub commands.**
>
> Perfect for interviews, daily development, DevOps engineers, and quick revisions.

---

# 📁 Repository Setup

| Command                                              | Description                     |
| ---------------------------------------------------- | ------------------------------- |
| `git init`                                           | Initialize a new Git repository |
| `git clone <url>`                                    | Clone an existing repository    |
| `git config --global user.name "Name"`               | Configure username              |
| `git config --global user.email "email@example.com"` | Configure email                 |
| `git config --list`                                  | Show Git configuration          |

---

# 📊 Check Repository Status

| Command                           | Description              |
| --------------------------------- | ------------------------ |
| `git status`                      | Show working tree status |
| `git diff`                        | Show unstaged changes    |
| `git diff --staged`               | Show staged changes      |
| `git log`                         | View commit history      |
| `git log --oneline`               | Compact commit history   |
| `git log --graph --oneline --all` | Graphical history        |

---

# ➕ Staging Changes

| Command                         | Description       |
| ------------------------------- | ----------------- |
| `git add file.txt`              | Stage one file    |
| `git add .`                     | Stage all changes |
| `git restore --staged file.txt` | Unstage a file    |

---

# 💾 Commit Changes

| Command                   | Description            |
| ------------------------- | ---------------------- |
| `git commit -m "message"` | Create a commit        |
| `git commit --amend`      | Modify the last commit |

---

# 🌿 Branching

| Command                     | Description          |
| --------------------------- | -------------------- |
| `git branch`                | List branches        |
| `git branch branch-name`    | Create a branch      |
| `git switch branch-name`    | Switch branches      |
| `git switch -c branch-name` | Create and switch    |
| `git branch -d branch-name` | Delete merged branch |
| `git branch -D branch-name` | Force delete branch  |

---

# 🔀 Merge & Rebase

| Command                 | Description            |
| ----------------------- | ---------------------- |
| `git merge branch-name` | Merge a branch         |
| `git rebase main`       | Rebase onto main       |
| `git rebase --continue` | Continue rebase        |
| `git rebase --abort`    | Abort rebase           |
| `git rebase --skip`     | Skip conflicted commit |

---

# 📦 Stash

| Command           | Description              |
| ----------------- | ------------------------ |
| `git stash`       | Save uncommitted work    |
| `git stash list`  | List stashes             |
| `git stash pop`   | Restore and remove stash |
| `git stash apply` | Restore without removing |
| `git stash drop`  | Delete a stash           |

---

# 🏷️ Tags

| Command                          | Description            |
| -------------------------------- | ---------------------- |
| `git tag`                        | List tags              |
| `git tag v1.0.0`                 | Create lightweight tag |
| `git tag -a v1.0.0 -m "Release"` | Create annotated tag   |
| `git show v1.0.0`                | View tag details       |
| `git push origin v1.0.0`         | Push tag               |

---

# 🔄 Reset, Restore & Revert

| Command                   | Description                                 |
| ------------------------- | ------------------------------------------- |
| `git restore file.txt`    | Restore file changes                        |
| `git reset --soft HEAD~1` | Undo commit, keep staged changes            |
| `git reset HEAD~1`        | Undo commit, keep working directory changes |
| `git reset --hard HEAD~1` | Remove commit and changes                   |
| `git revert HEAD`         | Safely undo with a new commit               |

---

# 🍒 Cherry-pick

| Command                    | Description             |
| -------------------------- | ----------------------- |
| `git cherry-pick <commit>` | Copy a specific commit  |
| `git cherry-pick A..B`     | Copy a range of commits |

---

# 🌐 Remote Repository

| Command                           | Description             |
| --------------------------------- | ----------------------- |
| `git remote -v`                   | View remotes            |
| `git remote add origin <url>`     | Add remote repository   |
| `git remote add upstream <url>`   | Add upstream repository |
| `git remote remove origin`        | Remove remote           |
| `git remote rename origin github` | Rename remote           |

---

# ☁️ Push & Pull

| Command                   | Description           |
| ------------------------- | --------------------- |
| `git push origin main`    | Push branch           |
| `git pull origin main`    | Pull latest changes   |
| `git fetch origin`        | Download changes only |
| `git push -u origin main` | Set upstream branch   |

---

# 🔐 SSH Authentication

| Command                                        | Description                      |
| ---------------------------------------------- | -------------------------------- |
| `ssh-keygen -t ed25519 -C "email@example.com"` | Generate SSH key                 |
| `ssh -T git@github.com`                        | Test GitHub SSH connection       |
| `cat ~/.ssh/id_ed25519.pub`                    | Display public key (Linux/macOS) |
| `clip.exe < ~/.ssh/id_ed25519.pub`             | Copy public key (Windows/WSL)    |

---

# 🚀 Fork Workflow

```text
Fork Repository
      │
      ▼
Clone Fork
      │
      ▼
Create Branch
      │
      ▼
Commit Changes
      │
      ▼
Push Branch
      │
      ▼
Open Pull Request
```

---

# 👥 Daily Collaboration Workflow

```text
Pull Latest Changes
        │
        ▼
Create Feature Branch
        │
        ▼
Write Code
        │
        ▼
git add .
        │
        ▼
git commit
        │
        ▼
git push
        │
        ▼
Create Pull Request
        │
        ▼
Code Review
        │
        ▼
Merge
```

---

# 🧰 Advanced Commands

| Command                   | Description                    |
| ------------------------- | ------------------------------ |
| `git reflog`              | View HEAD history              |
| `git blame file.txt`      | Show who modified each line    |
| `git clean -n`            | Preview untracked files        |
| `git clean -fd`           | Remove untracked files         |
| `git archive`             | Create project archive         |
| `git remote prune origin` | Remove stale remote references |
| `git gc`                  | Optimize repository            |
| `git fsck`                | Check repository integrity     |

---

# ⚔️ Frequently Asked Comparisons

| Feature         | Difference                                                    |
| --------------- | ------------------------------------------------------------- |
| Git vs GitHub   | Git is a VCS; GitHub is a hosting platform                    |
| Fetch vs Pull   | Fetch downloads; Pull downloads + merges                      |
| Merge vs Rebase | Merge preserves history; Rebase creates linear history        |
| Reset vs Revert | Reset rewrites history; Revert creates a new undo commit      |
| Clone vs Fork   | Clone creates a local copy; Fork creates your own GitHub copy |
| HTTPS vs SSH    | HTTPS uses PAT; SSH uses key-based authentication             |

---

# 📌 Common Branch Naming

```text
main
develop
feature/login
feature/payment
bugfix/navbar
hotfix/security
release/v1.0
docs/readme-update
```

---

# 📝 Conventional Commit Messages

```text
feat: Add user authentication

fix: Resolve login bug

docs: Update README

style: Format source code

refactor: Improve authentication logic

test: Add unit tests

chore: Update dependencies
```

---

# 💡 Git Best Practices

* ✅ Commit frequently with meaningful messages.
* ✅ Create a new branch for every feature or bug fix.
* ✅ Pull the latest changes before starting work.
* ✅ Keep Pull Requests small and focused.
* ✅ Never commit passwords, API keys, or secrets.
* ✅ Use `.gitignore` for generated files and dependencies.
* ✅ Delete merged branches regularly.
* ✅ Use SSH instead of HTTPS for daily development.
* ✅ Test changes before opening a Pull Request.
* ✅ Use `git reflog` before assuming work is lost.

---

# 🚨 Emergency Recovery

### Recover Lost Commit

```bash
git reflog
git reset --hard HEAD@{1}
```

### Undo Last Commit (Keep Changes)

```bash
git reset --soft HEAD~1
```

### Undo Last Commit (Discard Changes)

```bash
git reset --hard HEAD~1
```

### Undo a Pushed Commit

```bash
git revert <commit-id>
```

### Remove Untracked Files

```bash
git clean -fd
```

---

# 🎯 Interview Must-Know Commands

```bash
git init
git clone
git status
git add .
git commit -m
git push
git pull
git fetch
git branch
git switch
git merge
git rebase
git stash
git tag
git reset
git restore
git revert
git cherry-pick
git reflog
git blame
git clean
git remote
git log --oneline
```

---

# 🏆 Git Master Workflow

```text
Initialize Repository
        │
        ▼
Clone Repository
        │
        ▼
Create Feature Branch
        │
        ▼
Develop Feature
        │
        ▼
Stage Changes
        │
        ▼
Commit Changes
        │
        ▼
Push Branch
        │
        ▼
Create Pull Request
        │
        ▼
Code Review
        │
        ▼
Merge
        │
        ▼
Tag Release
        │
        ▼
Deploy
```

---

## 🎉 Congratulations!

You have completed the **Mastering Git & GitHub** roadmap.

From **Version Control** and **Git fundamentals** to **advanced Git commands**, **GitHub collaboration**, **best practices**, **interview preparation**, **hands-on labs**, and this **cheat sheet**, you now have a complete reference to confidently use Git in real-world development and DevOps workflows.

**Happy Coding! 🚀**
