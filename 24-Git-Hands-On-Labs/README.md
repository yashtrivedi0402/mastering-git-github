# Git Hands-on Labs

## 📖 Introduction

Learning Git commands is important, but mastering Git comes from **practical experience**.

These hands-on labs simulate real-world situations that Software Engineers, DevOps Engineers, and Cloud Engineers encounter daily.

By completing these labs, you'll gain confidence in using Git for personal projects, team collaboration, and technical interviews.

> **Prerequisites:** Install Git and have a GitHub account. Basic familiarity with Git commands is recommended.

---

# 🏗️ Lab Environment Setup

Create a practice repository.

```bash
mkdir git-labs
cd git-labs

git init
echo "# Git Labs" > README.md

git add .
git commit -m "Initial commit"
```

Verify the repository.

```bash
git status
git log --oneline
```

---

# 🧪 Lab 1 – Initialize a Git Repository

## 🎯 Objective

Learn how to create and initialize a Git repository.

### Tasks

* Create a new directory named `project1`.
* Initialize Git.
* Create a `README.md` file.
* Stage and commit the file.

### Expected Commands

```bash
mkdir project1
cd project1

git init

touch README.md

git add README.md

git commit -m "Initial commit"
```

### Skills Covered

* `git init`
* `git add`
* `git commit`

---

# 🧪 Lab 2 – Track File Changes

## 🎯 Objective

Understand Git's tracking behavior.

### Tasks

* Create a file named `notes.txt`.
* Modify it multiple times.
* Observe changes using Git.

### Expected Commands

```bash
echo "Version 1" > notes.txt

git status

git add notes.txt

git commit -m "Add notes"

echo "Version 2" >> notes.txt

git diff

git status
```

### Skills Covered

* `git status`
* `git diff`

---

# 🧪 Lab 3 – Git Log

## 🎯 Objective

Explore commit history.

### Tasks

Create multiple commits.

View history using:

```bash
git log
```

Compact view:

```bash
git log --oneline
```

Graph view:

```bash
git log --graph --oneline --all
```

### Skills Covered

* Git history
* Commit visualization

---

# 🧪 Lab 4 – Branching

## 🎯 Objective

Create and switch between branches.

### Tasks

```bash
git switch -c feature/login

echo "Login Feature" > login.txt

git add .

git commit -m "Add login feature"

git switch main
```

Verify:

```bash
git branch
```

### Skills Covered

* Branch creation
* Branch switching

---

# 🧪 Lab 5 – Merge Branches

## 🎯 Objective

Merge a feature branch into `main`.

### Tasks

```bash
git switch main

git merge feature/login
```

Verify history.

```bash
git log --graph --oneline
```

### Skills Covered

* Branch merging

---

# 🧪 Lab 6 – Resolve Merge Conflicts

## 🎯 Objective

Learn how to resolve merge conflicts.

### Steps

Create two branches.

Modify the same line in both branches.

Merge them.

Git will display:

```text
CONFLICT (content): Merge conflict
```

Resolve manually.

Stage:

```bash
git add .
```

Complete merge.

```bash
git commit
```

### Skills Covered

* Merge conflicts
* Conflict resolution

---

# 🧪 Lab 7 – Git Stash

## 🎯 Objective

Temporarily save unfinished work.

### Tasks

Modify a file.

Run:

```bash
git stash
```

Switch branch.

Return later.

Restore work.

```bash
git stash pop
```

### Skills Covered

* Git stash
* Task switching

---

# 🧪 Lab 8 – Git Tags

## 🎯 Objective

Create release tags.

### Tasks

```bash
git tag -a v1.0.0 -m "First Release"
```

View tags.

```bash
git tag
```

View tag information.

```bash
git show v1.0.0
```

### Skills Covered

* Version tagging

---

# 🧪 Lab 9 – Git Rebase

## 🎯 Objective

Practice rebasing.

Create:

```text
main

feature/login
```

Rebase.

```bash
git switch feature/login

git rebase main
```

Resolve conflicts if prompted.

Continue.

```bash
git rebase --continue
```

Abort if necessary.

```bash
git rebase --abort
```

### Skills Covered

* Git rebase
* Conflict resolution

---

# 🧪 Lab 10 – Reset, Restore & Revert

## 🎯 Objective

Undo changes safely.

Restore file.

```bash
git restore notes.txt
```

Soft reset.

```bash
git reset --soft HEAD~1
```

Mixed reset.

```bash
git reset HEAD~1
```

Revert commit.

```bash
git revert HEAD
```

### Skills Covered

* Undo operations

---

# 🧪 Lab 11 – Cherry-pick

## 🎯 Objective

Copy a specific commit.

Find commit.

```bash
git log --oneline
```

Cherry-pick.

```bash
git cherry-pick <commit-id>
```

### Skills Covered

* Commit transfer

---

# 🧪 Lab 12 – SSH Authentication

## 🎯 Objective

Configure SSH for GitHub.

Tasks:

* Generate SSH key.
* Add Public Key to GitHub.
* Test connection.

Commands:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"

ssh -T git@github.com
```

### Skills Covered

* SSH authentication

---

# 🧪 Lab 13 – GitHub Collaboration

## 🎯 Objective

Simulate a team workflow.

Tasks:

* Clone a repository.
* Create a feature branch.
* Push changes.
* Open a Pull Request.
* Merge the Pull Request.

### Skills Covered

* Collaboration workflow
* Pull Requests

---

# 🧪 Lab 14 – Recover Lost Commits

## 🎯 Objective

Recover deleted work.

Reset branch.

```bash
git reset --hard HEAD~1
```

Recover.

```bash
git reflog
```

Restore.

```bash
git reset --hard HEAD@{1}
```

### Skills Covered

* Git recovery
* Reflog

---

# 🧪 Lab 15 – Clean Repository

## 🎯 Objective

Remove temporary files.

Preview.

```bash
git clean -n
```

Delete.

```bash
git clean -fd
```

### Skills Covered

* Git clean

---

# 🧪 Lab 16 – Fork & Pull Request

## 🎯 Objective

Contribute to an open-source project.

### Tasks

1. Fork a public repository.
2. Clone your fork.
3. Create a feature branch.
4. Make a change.
5. Commit and push.
6. Open a Pull Request.
7. Address review comments (if any).

### Skills Covered

* Fork workflow
* Pull Requests
* Open-source contribution

---

# 🧪 Lab 17 – End-to-End Team Project

## 🎯 Objective

Simulate a complete development cycle.

### Scenario

You are part of a team building an **E-Commerce Application**.

### Workflow

```text
Create Repository
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
Commit Changes
        │
        ▼
Push Branch
        │
        ▼
Open Pull Request
        │
        ▼
Code Review
        │
        ▼
Resolve Comments
        │
        ▼
Merge
        │
        ▼
Tag Release
        │
        ▼
Delete Feature Branch
```

### Skills Covered

* Complete Git workflow
* Team collaboration
* Release management

---

# 🏆 Final Challenge

Complete the following workflow **without referring to notes**:

* Initialize a repository.
* Configure Git.
* Create a feature branch.
* Make three commits.
* Merge into `main`.
* Create a merge conflict and resolve it.
* Stash unfinished work.
* Rebase your branch.
* Recover a deleted commit using `git reflog`.
* Create a release tag.
* Push to GitHub using SSH.
* Fork another repository.
* Open a Pull Request.
* Delete merged branches.
* Synchronize your fork with the upstream repository.

If you can complete this challenge independently, you're ready to use Git confidently in professional projects.

---

# 📋 Skills Checklist

| Skill                       | Completed |
| --------------------------- | :-------: |
| Initialize Repository       |     ☐     |
| Stage & Commit              |     ☐     |
| View History                |     ☐     |
| Branching                   |     ☐     |
| Merge                       |     ☐     |
| Merge Conflict Resolution   |     ☐     |
| Stash                       |     ☐     |
| Tags                        |     ☐     |
| Rebase                      |     ☐     |
| Reset / Restore / Revert    |     ☐     |
| Cherry-pick                 |     ☐     |
| SSH Authentication          |     ☐     |
| Fork & Pull Request         |     ☐     |
| Git Reflog Recovery         |     ☐     |
| Git Clean                   |     ☐     |
| Team Collaboration Workflow |     ☐     |

---

# 🎯 Interview Readiness Checklist

Before attending a Git interview, make sure you can confidently:

* Explain the Git workflow.
* Create and merge branches.
* Resolve merge conflicts.
* Differentiate Merge vs Rebase.
* Explain Reset, Restore, and Revert.
* Recover lost commits using `git reflog`.
* Use Stash, Tags, and Cherry-pick.
* Configure SSH authentication.
* Contribute using Forks and Pull Requests.
* Collaborate using feature branches and code reviews.

---

# 🎉 Congratulations!

You've completed the **Mastering Git & GitHub** journey.

From understanding **Version Control Systems** to mastering **advanced Git operations**, collaboration workflows, and hands-on labs, you now have the knowledge needed to work confidently on real-world software projects.

Keep practicing these labs regularly, contribute to open-source projects, and use Git daily—the best way to master Git is through consistent practice.

**Happy Coding! 🚀**
