# Git Reset, Git Restore & Git Revert

## 📖 Introduction

Mistakes are a natural part of software development. You might accidentally modify a file, stage the wrong changes, or create a commit that shouldn't exist.

Git provides several commands to undo these mistakes safely. However, each command works differently and affects different parts of your repository.

The three most commonly used commands are:

* **Git Restore** – Undo changes in files or unstage files.
* **Git Reset** – Move the current branch to a previous commit.
* **Git Revert** – Undo a commit by creating a new commit.

Understanding the differences between these commands is essential for every Git user.

---

# 🎯 Understanding the Three Areas of Git

Before learning these commands, it's important to understand where changes exist inside Git.

```text
                Git Repository
            (Committed Snapshots)
                     ▲
                     │
               git commit
                     │
                     ▼
               Staging Area
             (Indexed Changes)
                     ▲
                     │
                 git add
                     │
                     ▼
             Working Directory
            (Your Project Files)
```

Each command affects different parts of this workflow.

---

# 🔄 Git Restore

## 🤔 What is Git Restore?

`git restore` is used to discard changes in your working directory or remove files from the staging area.

It **does not delete commits**.

It simply restores files to a previous state.

---

# 🌍 Real-World Analogy

Imagine you're writing an essay.

Before submitting it, you accidentally make unwanted edits.

Instead of rewriting everything manually, you restore the document to its last saved version.

That's exactly what Git Restore does.

---

# 🏗️ How Git Restore Works

```text
Working Directory
       ▲
       │
git restore
```

Only the **Working Directory** is affected.

---

# 📌 Restore Modified Files

Suppose you edited a file but don't want those changes.

```bash
git restore app.py
```

Git restores the file to the latest committed version.

---

# 📌 Unstage Files

Suppose you accidentally staged a file.

```bash
git restore --staged app.py
```

Architecture:

```text
Working Directory
       │
       ▼
Staging Area
       ▲
       │
git restore --staged
```

The file is removed from the staging area but your changes remain in the working directory.

---

# 🔄 Git Reset

## 🤔 What is Git Reset?

Git Reset moves the current branch (HEAD) to an earlier commit.

Depending on the option used, it can affect:

* Commit History
* Staging Area
* Working Directory

---

# 🌍 Real-World Analogy

Imagine saving multiple versions of a presentation.

Later, you decide Version 6 wasn't good enough.

Git Reset lets you move back to Version 5.

Depending on the reset mode, you may keep or discard your edits.

---

# 🏗️ How Git Reset Works

```text
HEAD
 │
 ▼
Commit 5
 │
 ▼
Commit 4
 │
 ▼
Commit 3
```

Running Git Reset moves **HEAD** backward.

---

# 🔹 Soft Reset

Command:

```bash
git reset --soft HEAD~1
```

Architecture:

```text
Commit History  ◀──── Changed

Staging Area    ✔ Preserved

Working Directory ✔ Preserved
```

Use Case:

Undo the last commit while keeping everything staged.

---

# 🔹 Mixed Reset (Default)

Command:

```bash
git reset HEAD~1
```

or

```bash
git reset --mixed HEAD~1
```

Architecture:

```text
Commit History ◀──── Changed

Staging Area ◀──── Cleared

Working Directory ✔ Preserved
```

Use Case:

Undo a commit but continue editing the files.

---

# 🔹 Hard Reset

Command:

```bash
git reset --hard HEAD~1
```

Architecture:

```text
Commit History ◀──── Changed

Staging Area ◀──── Cleared

Working Directory ◀──── Cleared
```

Everything after the selected commit is permanently removed.

> **⚠️ Warning:** Only use `git reset --hard` when you're certain you no longer need those changes.

---

# 🔄 Git Revert

## 🤔 What is Git Revert?

Unlike Reset, Git Revert **does not delete commits**.

Instead, it creates a **new commit** that reverses the changes introduced by an earlier commit.

This makes Git Revert the safest way to undo changes in shared repositories.

---

# 🌍 Real-World Analogy

Imagine sending an email with incorrect information.

You cannot delete the email from everyone's inbox.

Instead, you send another email correcting the mistake.

Git Revert works the same way.

---

# 🏗️ How Git Revert Works

Before:

```text
A──B──C
```

Run:

```bash
git revert C
```

After:

```text
A──B──C──D

D = Reverts C
```

Commit **C** remains in history.

Git simply creates another commit that reverses its changes.

---

# 📌 Revert the Latest Commit

```bash
git revert HEAD
```

---

# 📌 Revert a Specific Commit

```bash
git revert <commit-id>
```

---

# 📊 Reset vs Restore vs Revert

| Feature                      | Restore | Reset | Revert |
| ---------------------------- | ------- | ----- | ------ |
| Removes file changes         | ✅       | ✅     | ❌      |
| Removes commits              | ❌       | ✅     | ❌      |
| Creates new commit           | ❌       | ❌     | ✅      |
| Safe for shared repositories | ✅       | ❌     | ✅      |
| Changes Git history          | ❌       | ✅     | ❌      |

---

# 📋 Common Commands

| Command                     | Purpose                          |
| --------------------------- | -------------------------------- |
| `git restore file`          | Restore file changes             |
| `git restore --staged file` | Unstage a file                   |
| `git reset --soft HEAD~1`   | Undo commit, keep staged changes |
| `git reset --mixed HEAD~1`  | Undo commit, keep file changes   |
| `git reset --hard HEAD~1`   | Remove commit and changes        |
| `git revert HEAD`           | Undo latest commit safely        |
| `git revert <commit-id>`    | Undo a specific commit           |

---

# 💡 Best Practices

* Use **Git Restore** for accidental file modifications.
* Use **Soft Reset** to rewrite your latest commit.
* Use **Mixed Reset** when you want to continue editing.
* Avoid **Hard Reset** unless you're certain the changes can be discarded.
* Prefer **Git Revert** for public or shared repositories.
* Always check `git status` before running destructive commands.

---

# ❌ Common Mistakes

| Mistake                                                   | Better Practice                                          |
| --------------------------------------------------------- | -------------------------------------------------------- |
| Using `git reset --hard` without understanding its impact | Use `git revert` if the commit has already been shared   |
| Using Reset on a shared branch                            | Use Revert to preserve history                           |
| Confusing Restore with Reset                              | Remember: Restore works on files, Reset works on commits |
| Forgetting to review repository status                    | Run `git status` before undoing changes                  |

---

# 🎯 Interview Questions

### Q1. What is the difference between Git Reset and Git Revert?

**Answer:**

Git Reset moves the current branch pointer and can remove commits from history, whereas Git Revert preserves history by creating a new commit that reverses a previous commit.

---

### Q2. Which command is safest for shared repositories?

**Answer:**

Git Revert, because it does not rewrite commit history.

---

### Q3. What does `git restore --staged` do?

**Answer:**

It removes a file from the staging area while keeping the changes in the working directory.

---

### Q4. What is the difference between Soft, Mixed, and Hard Reset?

**Answer:**

* **Soft Reset** → Removes the commit but keeps changes staged.
* **Mixed Reset** → Removes the commit and unstages the changes.
* **Hard Reset** → Removes the commit and permanently deletes all associated changes.

---

### Q5. Which command creates a new commit to undo changes?

**Answer:**

```bash
git revert <commit-id>
```

---

# 📌 Key Takeaways

* **Git Restore** is used to restore files or unstage changes.
* **Git Reset** moves the current branch to a previous commit and can rewrite history.
* **Git Revert** safely undoes changes by creating a new commit.
* Use **Restore** for file-level mistakes.
* Use **Reset** for local history changes.
* Use **Revert** when working on shared repositories.

---

## 🚀 What's Next?

Now that you know how to undo changes safely, it's time to learn how to copy specific commits from one branch to another without merging the entire branch.

In the next chapter, you'll explore **Git Cherry-pick**, where you'll learn how to apply individual commits across branches, when Cherry-pick is useful, its workflow, and the best practices followed in real-world development.
