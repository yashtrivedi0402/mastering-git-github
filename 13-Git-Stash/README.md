# Git Stash

## 📖 Introduction

During development, there are times when you're working on a feature but suddenly need to switch to another task—perhaps to fix a critical bug, review code, or work on a different branch.

Your current changes are incomplete, and you don't want to commit unfinished work.

This is where **Git Stash** becomes useful.

Git Stash allows you to **temporarily save your uncommitted changes** and restore them later, giving you a clean working directory without losing your progress.

---

# 🤔 What is Git Stash?

**Git Stash** is a Git feature that temporarily stores your uncommitted changes in a hidden stack.

These changes are removed from your working directory, allowing you to switch branches or perform other tasks safely.

When you're ready, you can restore the stashed changes and continue working from where you left off.

---

# 🌍 Real-World Analogy

Imagine you're writing a report when your manager suddenly asks you to fix an urgent issue.

Instead of throwing away your unfinished report, you place it in a drawer.

After finishing the urgent task, you take the report out of the drawer and continue writing.

Git Stash works exactly like that drawer—it temporarily stores your unfinished work.

---

# 🤔 Why Do We Use Git Stash?

Git Stash is useful when:

* You need to switch branches quickly.
* Your current work is incomplete.
* You don't want to create unnecessary commits.
* You need a clean working directory.
* You want to save work temporarily without pushing it.

---

# 🏗️ How Git Stash Works

```text
Working Directory
        │
        ▼
Uncommitted Changes
        │
        ▼
git stash
        │
        ▼
Stash Stack
        │
        ▼
Clean Working Directory
        │
        ▼
git stash pop
        │
        ▼
Restore Changes
```

Git temporarily moves your changes into the stash stack and restores them later.

---

# 🛠️ Save Your Changes

Temporarily save your current changes:

```bash
git stash
```

Git saves:

* Modified files
* Staged changes
* Tracked file changes

Your working directory becomes clean.

---

# 📋 View All Stashes

Display all saved stashes:

```bash
git stash list
```

Example:

```text
stash@{0}: WIP on feature-login: Add login page
stash@{1}: WIP on main: Fix navbar
```

Each stash receives an index.

---

# 📥 Restore the Latest Stash

Restore the latest stash and remove it from the stash stack:

```bash
git stash pop
```

This is the most commonly used stash command.

---

# 📂 Apply a Stash Without Deleting It

Restore a stash but keep it in the stash stack:

```bash
git stash apply
```

This is useful when you may need the same stash again.

---

# 🎯 Apply a Specific Stash

Restore a particular stash:

```bash
git stash apply stash@{1}
```

Git applies only the selected stash.

---

# 🗑️ Delete a Stash

Delete a specific stash:

```bash
git stash drop stash@{0}
```

Delete all stashes:

```bash
git stash clear
```

Use `git stash clear` carefully because it permanently removes every saved stash.

---

# 🔄 Typical Git Stash Workflow

```text
Start Working
      │
      ▼
Modify Files
      │
      ▼
Need to Switch Branch?
      │
      ▼
git stash
      │
      ▼
Switch Branch
      │
      ▼
Complete Other Work
      │
      ▼
Return to Original Branch
      │
      ▼
git stash pop
      │
      ▼
Continue Development
```

---

# 📌 Common Git Stash Commands

| Command           | Purpose                         |
| ----------------- | ------------------------------- |
| `git stash`       | Save current changes            |
| `git stash list`  | View saved stashes              |
| `git stash pop`   | Restore and remove latest stash |
| `git stash apply` | Restore without removing        |
| `git stash drop`  | Delete a specific stash         |
| `git stash clear` | Delete all stashes              |

---

# 💡 Best Practices

* Use Git Stash only for temporary work.
* Give preference to feature branches for long-term development.
* Apply stashes as soon as possible to avoid conflicts.
* Review your stash list regularly and remove unused entries.
* Use `git stash pop` when you're finished with a stash.

---

# ❌ Common Mistakes

| Mistake                               | Better Practice                          |
| ------------------------------------- | ---------------------------------------- |
| Using Git Stash for long-term storage | Commit work to a feature branch instead. |
| Forgetting saved stashes              | Check `git stash list` regularly.        |
| Clearing all stashes accidentally     | Verify before using `git stash clear`.   |
| Creating too many unnamed stashes     | Keep the stash list organized and clean. |

---

# 🎯 Interview Questions

### Q1. What is Git Stash?

**Answer:**

Git Stash temporarily saves uncommitted changes and restores the working directory to a clean state.

---

### Q2. Why do developers use Git Stash?

**Answer:**

Developers use Git Stash when they need to switch tasks or branches without committing unfinished work.

---

### Q3. Which command saves your current work?

```bash
git stash
```

---

### Q4. What is the difference between `git stash pop` and `git stash apply`?

**Answer:**

* `git stash pop` restores the stash and removes it from the stash list.
* `git stash apply` restores the stash but keeps it in the stash list.

---

### Q5. Which command displays all stashes?

```bash
git stash list
```

---

### Q6. How do you remove all saved stashes?

```bash
git stash clear
```

---

# 📌 Key Takeaways

* Git Stash temporarily stores uncommitted changes.
* It provides a clean working directory without losing progress.
* `git stash pop` restores and removes a stash.
* `git stash apply` restores a stash while keeping it saved.
* Git Stash is intended for short-term work, not long-term storage.

---

## 🚀 What's Next?

Now that you know how to temporarily save unfinished work, the next step is learning how to mark important points in your project's history.

In the next chapter, we'll explore **Git Tags**, understand the difference between lightweight and annotated tags, and learn how tags are used to manage software releases and versioning.
