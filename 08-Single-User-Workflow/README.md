# Single User Git Workflow

## 📖 Introduction

Now that you understand Git architecture and the most commonly used Git commands, it's time to see how they work together in a real project.

A **Single User Git Workflow** is the process followed by an individual developer to track changes, save progress, and maintain a project's history using Git.

This workflow forms the foundation of software development and is the first step before learning team collaboration with GitHub.

---

# 🎯 Workflow Overview

The complete workflow looks like this:

```text id="f8r1qn"
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
git commit -m "Initial commit"
      │
      ▼
git log
      │
      ▼
Continue Development
```

Every Git project follows this cycle repeatedly throughout its lifecycle.

---

# 🛠️ Step 1: Create a Project

Create a new project directory and move into it.

```bash id="z0r7pk"
mkdir my-first-project
cd my-first-project
```

At this point, the folder is just a normal directory.

Git is not tracking it yet.

---

# 🚀 Step 2: Initialize Git

Initialize the repository.

```bash id="7g0xjv"
git init
```

Git creates a hidden **`.git`** directory that stores commits, branches, configuration, references, and the complete history of the repository.

---

# 📄 Step 3: Create Project Files

Create a simple file.

```bash id="1lxzj2"
echo "# My First Project" > README.md
```

Git notices the new file, but it is still **untracked**.

---

# 🔍 Step 4: Check Repository Status

Check the current state of the repository.

```bash id="f5d0pn"
git status
```

Example output:

```text id="f5tcn9"
Untracked files:
  README.md
```

This tells you that Git has detected the file, but it isn't being tracked yet.

---

# 📦 Step 5: Stage the File

Move the file to the Staging Area.

```bash id="4jv19y"
git add README.md
```

Or stage all changes:

```bash id="l9xm7s"
git add .
```

The file is now ready to be committed.

---

# 💾 Step 6: Create the First Commit

Save the staged changes.

```bash id="5svvij"
git commit -m "Initial commit"
```

Git creates a permanent snapshot and stores it in the Local Repository.

This is the first version of your project.

---

# 📜 Step 7: View Commit History

Display the project's commit history.

```bash id="c2vmqa"
git log --oneline
```

Example:

```text id="7nn54r"
8f3d2ab Initial commit
```

Each commit has a unique SHA (commit ID) that identifies it forever.

---

# 🔁 Step 8: Continue Development

Modify the project.

```bash id="h2kn3s"
echo "Welcome to Git!" >> README.md
```

Check the status again.

```bash id="dhz5pg"
git status
```

Stage the new changes.

```bash id="uk03tm"
git add README.md
```

Create another commit.

```bash id="bh6n6m"
git commit -m "Update README"
```

View the updated history.

```bash id="6lmxhy"
git log --oneline
```

Example:

```text id="9s3vqe"
b12e4d1 Update README
8f3d2ab Initial commit
```

Git now stores multiple versions of your project, making it easy to review or restore previous work.

---

# 🌍 Real-World Analogy

Imagine you're writing a book.

* **Create the folder** → Start a new book project.
* **`git init`** → Create a revision notebook for the book.
* **Write content** → Draft new chapters.
* **`git status`** → Check what has changed.
* **`git add`** → Mark changes ready for publishing.
* **`git commit`** → Publish a new edition of the book.
* **`git log`** → View the history of all published editions.

Each commit becomes a permanent version of your work.

---

# 💡 Best Practices

* Initialize Git at the beginning of a project.
* Check `git status` before staging or committing.
* Stage only the changes you intend to commit.
* Write meaningful commit messages.
* Commit small, logical changes frequently instead of waiting too long.

---

# ❌ Common Mistakes

| Mistake                                     | Better Practice                                                                   |
| ------------------------------------------- | --------------------------------------------------------------------------------- |
| Forgetting to check `git status`            | Review repository status before every commit.                                     |
| Using vague commit messages like `"update"` | Write descriptive messages such as `"Add login page"` or `"Fix API timeout bug"`. |
| Creating one huge commit                    | Make several smaller, focused commits.                                            |
| Skipping commits for long periods           | Commit regularly to preserve a clear project history.                             |

---

# 🎯 Interview Questions

### Q1. What is a Single User Git Workflow?

**Answer:**
It is the process an individual developer follows to create a repository, track changes, stage files, create commits, and manage project history using Git.

---

### Q2. Which command starts Git tracking for a project?

**Answer:**

```bash id="4pd3qa"
git init
```

---

### Q3. Why should you run `git status` frequently?

**Answer:**
It shows the current state of the repository, including untracked, modified, and staged files, helping you verify what will be included in the next commit.

---

### Q4. Why are multiple small commits better than one large commit?

**Answer:**
Small commits make the project history easier to understand, review, debug, and revert when necessary.

---

# 📌 Key Takeaways

* A Single User Git Workflow is the foundation of using Git effectively.
* Every project follows the sequence: **Initialize → Modify → Stage → Commit → Review → Repeat**.
* `git status` should become a habit before every commit.
* Small, meaningful commits create a clean and maintainable project history.
* This workflow prepares you for team collaboration using remote repositories.

---

## 🚀 What's Next?

So far, all work has been stored on your local machine.

In the next chapter, you'll learn how to connect your local repository to **GitHub**, create a remote repository, and use commands like `git remote`, `git push`, `git pull`, and `git fetch` to collaborate and back up your code.
