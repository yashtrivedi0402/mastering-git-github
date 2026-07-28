# Advanced Git Commands

## 📖 Introduction

After learning the core Git workflow, there are several advanced Git commands that help developers troubleshoot issues, recover lost work, inspect repository history, clean repositories, and maintain Git's internal database.

These commands are commonly used by **Software Engineers**, **DevOps Engineers**, **Release Engineers**, and **Open Source Contributors** when working on large or long-running projects.

Understanding these commands will help you solve real-world Git problems more efficiently.

---

# 🎯 Why Learn Advanced Git Commands?

Advanced Git commands help you:

* Recover accidentally lost commits
* Find who changed a specific line of code
* Remove unnecessary files
* Create project archives
* Clean obsolete remote references
* Optimize repository performance
* Verify repository integrity

---

# 🗂️ Advanced Git Commands Covered

* Git Reflog
* Git Blame
* Git Clean
* Git Archive
* Git Remote Prune
* Git GC (Garbage Collection)
* Git FSCK (File System Check)

---

# 🔄 Git Reflog

## 🤔 What is Git Reflog?

Git Reflog records every movement of **HEAD**, including commits, resets, rebases, checkouts, and branch switches.

Even if a commit no longer appears in `git log`, you can often recover it using Reflog.

---

## 🌍 Real-World Analogy

Imagine CCTV footage inside a building.

Even if someone leaves the building, the CCTV still records where they went.

Git Reflog acts like Git's CCTV, recording every movement of HEAD.

---

## 🏗️ Architecture

```text id="5x1yjk"
Commit A
    │
Commit B
    │
Commit C
    │
Reset
    │
Commit Hidden

↓

git reflog

Shows every HEAD movement
```

---

## Command

```bash id="k1rbxv"
git reflog
```

Example:

```text id="a1u0qm"
9e4d3c2 HEAD@{0}: commit: Fix login bug
8ab1f44 HEAD@{1}: reset: moving to HEAD~1
7de11fa HEAD@{2}: commit: Add login page
```

---

## Recover Lost Commit

```bash id="4n5b8v"
git reset --hard HEAD@{2}
```

---

# 🔍 Git Blame

## 🤔 What is Git Blame?

Git Blame shows **who last modified each line** of a file.

It is extremely useful for debugging and understanding code history.

---

## 🌍 Real-World Analogy

Imagine every sentence in a book has the author's name written beside it.

Git Blame tells you exactly who last edited every line.

---

## Command

```bash id="l5f9ya"
git blame app.py
```

Example:

```text id="mjxv61"
7de11fa (Alice) Line 1
3af221b (Bob)   Line 2
91ef443 (John)  Line 3
```

---

## Use Cases

* Debugging bugs
* Finding the author of a change
* Understanding code history

---

# 🧹 Git Clean

## 🤔 What is Git Clean?

Git Clean removes **untracked files and directories** from your working directory.

Unlike `git restore`, it only removes files that Git is **not tracking**.

---

## 🌍 Real-World Analogy

Imagine cleaning your desk by throwing away rough notes that were never officially filed.

Git Clean removes temporary files that Git doesn't know about.

---

## Commands

Preview what will be removed.

```bash id="j84ef0"
git clean -n
```

Delete untracked files.

```bash id="bxq8m6"
git clean -f
```

Delete untracked directories.

```bash id="h73dzr"
git clean -fd
```

---

# 📦 Git Archive

## 🤔 What is Git Archive?

Git Archive creates a compressed archive of your project without including Git history.

Useful for releasing source code.

---

## Command

Create ZIP archive.

```bash id="d2v8nw"
git archive --format=zip --output=project.zip HEAD
```

---

## Use Cases

* Share source code
* Release project versions
* Package applications

---

# 🌐 Git Remote Prune

## 🤔 What is Git Remote Prune?

Sometimes remote branches are deleted on GitHub but still appear in your local repository.

Git Remote Prune removes these obsolete remote references.

---

## Architecture

```text id="v5kq7g"
GitHub

feature/login ❌ Deleted

↓

Local Repository

Still Exists

↓

git remote prune origin

↓

Reference Removed
```

---

## Command

```bash id="k80zgc"
git remote prune origin
```

---

# ♻️ Git GC (Garbage Collection)

## 🤔 What is Git GC?

Git GC optimizes the repository by:

* Compressing objects
* Removing unreachable data
* Cleaning unnecessary files
* Improving repository performance

Git also runs this automatically when required.

---

## Command

```bash id="3v9dme"
git gc
```

---

## Use Cases

* Large repositories
* Long project history
* Repository optimization

---

# 🛠️ Git FSCK

## 🤔 What is Git FSCK?

FSCK stands for **File System Check**.

Git FSCK verifies the integrity of your repository and detects:

* Corrupted objects
* Missing commits
* Broken references

---

## Command

```bash id="ol9msf"
git fsck
```

Example Output:

```text id="70kmt6"
Checking object directories...
Checking commits...
No problems found.
```

---

## Use Cases

* Repository corruption
* Verifying backups
* Debugging Git issues

---

# 📋 Common Advanced Commands

| Command                   | Purpose                            |
| ------------------------- | ---------------------------------- |
| `git reflog`              | View HEAD history                  |
| `git blame file`          | Show who modified each line        |
| `git clean -n`            | Preview files to remove            |
| `git clean -fd`           | Remove untracked files/directories |
| `git archive`             | Create project archive             |
| `git remote prune origin` | Remove stale remote references     |
| `git gc`                  | Optimize repository                |
| `git fsck`                | Verify repository integrity        |

---

# 💡 Best Practices

* Use `git reflog` before assuming work is lost.
* Preview with `git clean -n` before using `git clean -f`.
* Run `git gc` occasionally for large repositories.
* Use `git blame` to understand code history, not to assign blame to teammates.
* Use `git fsck` if you suspect repository corruption.

---

# ❌ Common Mistakes

| Mistake                                     | Better Practice                            |
| ------------------------------------------- | ------------------------------------------ |
| Running `git clean -f` without preview      | Use `git clean -n` first                   |
| Assuming deleted commits are unrecoverable  | Check `git reflog`                         |
| Forgetting to prune stale remote branches   | Run `git remote prune origin` periodically |
| Misusing `git blame` to criticize teammates | Use it as a debugging tool                 |
| Ignoring repository corruption warnings     | Run `git fsck` and investigate immediately |

---

# 🎯 Interview Questions

### Q1. What is Git Reflog?

**Answer:**

Git Reflog records every movement of HEAD and helps recover commits that may no longer appear in `git log`.

---

### Q2. What is the difference between `git log` and `git reflog`?

**Answer:**

`git log` shows the commit history of the current branch, whereas `git reflog` records every HEAD movement, including resets, rebases, and checkouts, making it useful for recovering lost commits.

---

### Q3. What does Git Blame do?

**Answer:**

Git Blame shows which commit and author last modified each line of a file.

---

### Q4. Which command safely previews files before deleting them?

```bash id="v65lbx"
git clean -n
```

---

### Q5. What is Git GC used for?

**Answer:**

Git GC performs garbage collection by cleaning unnecessary data and optimizing repository performance.

---

### Q6. What is Git FSCK?

**Answer:**

Git FSCK checks the integrity of a Git repository by detecting corrupted objects, missing commits, and broken references.

---

# 📌 Key Takeaways

* `git reflog` helps recover lost commits.
* `git blame` identifies who last modified each line.
* `git clean` removes untracked files.
* `git archive` creates distributable project archives.
* `git remote prune` removes obsolete remote references.
* `git gc` optimizes repository storage.
* `git fsck` verifies repository health and integrity.

---

## 🚀 What's Next?

Congratulations! You have now covered the complete Git and GitHub workflow—from basic version control concepts to advanced Git operations used in professional software development.

In the next chapters, you'll reinforce your knowledge through **Git Best Practices**, **Interview Questions**, and **Hands-on Labs**, where you'll apply everything you've learned in real-world scenarios and become confident using Git in production environments.
