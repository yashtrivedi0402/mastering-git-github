# Git Architecture & Workflow

## 📖 Introduction

Before learning Git commands, it's important to understand **how Git manages your project internally**.

Whenever you create or modify a file, Git moves your changes through different stages before they are finally stored and shared.

Understanding this workflow is the key to mastering Git.

---

# 🏗️ Git Architecture

Git manages your project using four main areas:

```text
                Git Workflow

        ┌─────────────────────┐
        │  Working Directory  │
        └─────────┬───────────┘
                  │
           git add
                  │
                  ▼
        ┌─────────────────────┐
        │    Staging Area     │
        └─────────┬───────────┘
                  │
          git commit
                  │
                  ▼
        ┌─────────────────────┐
        │  Local Repository   │
        └─────────┬───────────┘
                  │
           git push
                  │
                  ▼
        ┌─────────────────────┐
        │ Remote Repository   │
        │     (GitHub)        │
        └─────────────────────┘
```

Each stage has a different responsibility.

Let's understand them one by one.

---

# 1️⃣ Working Directory

The **Working Directory** is the folder where you create, edit, rename, or delete files.

Whenever you run:

```bash
git init
```

or

```bash
git clone
```

Git creates a working directory for your project.

Any changes you make are initially available **only in this directory**.

Git has not yet recorded them.

### Example

```text
Portfolio Website

│── index.html
│── style.css
│── script.js
```

Editing `index.html` only changes the Working Directory.

---

# 2️⃣ Staging Area

The **Staging Area** is a temporary area where you select the changes that should be included in the next commit.

Files move into the Staging Area using:

```bash
git add
```

The Staging Area allows you to decide exactly **which changes** should become part of the next snapshot.

Think of it as a review area before saving your work.

---

# 3️⃣ Local Repository

Once your staged changes are ready, you create a commit using:

```bash
git commit
```

Git creates a permanent snapshot and stores it in the **Local Repository**.

Every commit contains:

* Commit ID (SHA)
* Author Name
* Author Email
* Date & Time
* Commit Message

The Local Repository exists on your own computer.

No internet connection is required to create commits.

---

# 4️⃣ Remote Repository

A **Remote Repository** is an online copy of your Git repository.

Platforms such as **GitHub**, **GitLab**, and **Bitbucket** host remote repositories.

After creating commits locally, you can upload them using:

```bash
git push
```

The remote repository makes collaboration, backup, and code sharing possible.

---

# 🌍 Real-World Analogy

Imagine you're writing an assignment.

### 📝 Working Directory

You are writing the assignment in Microsoft Word.

Nothing has been submitted yet.

---

### 📂 Staging Area

You review the pages and decide which ones are ready to submit.

---

### 💾 Local Repository

You save a final copy on your laptop.

Now you have a permanent version.

---

### ☁️ Remote Repository

You upload the assignment to Google Drive or your college portal.

Now others can access it and you have an online backup.

This is exactly how Git manages your project.

---

# 🔄 Complete Workflow

A typical Git workflow looks like this:

```text
Create Project
        │
        ▼
Modify Files
        │
        ▼
Working Directory
        │
    git add
        │
        ▼
Staging Area
        │
  git commit
        │
        ▼
Local Repository
        │
   git push
        │
        ▼
Remote Repository (GitHub)
```

Every Git project follows this workflow.

---

# 💡 Why Does Git Have a Staging Area?

Many beginners wonder:

> "Why can't Git commit files directly?"

The Staging Area gives developers complete control.

For example:

You modified:

* index.html
* style.css
* README.md

But today you only want to commit `README.md`.

The Staging Area allows you to choose exactly what should be included in the next commit.

Without it, every change would be committed together.

---

# 🎯 Interview Questions

### Q1. What are the four stages of the Git workflow?

**Answer:**

* Working Directory
* Staging Area
* Local Repository
* Remote Repository

---

### Q2. Which command moves changes to the Staging Area?

**Answer:**

```bash
git add
```

---

### Q3. Which command creates a snapshot in the Local Repository?

**Answer:**

```bash
git commit
```

---

### Q4. Which command uploads commits to the Remote Repository?

**Answer:**

```bash
git push
```

---

### Q5. Does `git commit` require an internet connection?

**Answer:**

No.

`git commit` creates a commit in the **Local Repository** and works completely offline.

---

# 📌 Key Takeaways

* Git follows a four-stage workflow.
* Every file starts in the Working Directory.
* The Staging Area allows you to choose what will be committed.
* A commit creates a permanent snapshot in the Local Repository.
* The Remote Repository stores an online copy for collaboration and backup.
* Most Git operations can be performed without an internet connection.

---

## 🚀 What's Next?

Now that you understand how Git manages your project internally, it's time to learn the **basic Git commands** that move your code through each stage of the workflow.

In the next chapter, we'll explore commands like `git init`, `git status`, `git add`, `git commit`, `git log`, and `git restore` in detail.
