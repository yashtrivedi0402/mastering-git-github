# Git Tags

## 📖 Introduction

As a project evolves, developers release multiple versions such as **v1.0**, **v1.1**, **v2.0**, and so on.

These versions represent important milestones in the project's history.

Instead of remembering specific commit hashes, Git provides **Tags**, which allow developers to assign meaningful names to important commits.

Git Tags make it easy to identify releases, revisit previous versions, and maintain a clear version history.

---

# 🤔 What is a Git Tag?

A **Git Tag** is a permanent reference that points to a specific commit.

Unlike branches, tags **do not move** when new commits are created.

They are commonly used to mark:

* Software releases
* Stable versions
* Milestones
* Production deployments

---

# 🌍 Real-World Analogy

Imagine you've written several editions of a book.

Instead of remembering page numbers where each edition ends, you label them:

* First Edition
* Second Edition
* Anniversary Edition

Whenever someone asks for the **Second Edition**, you can immediately locate it.

Git Tags work the same way by labeling important commits.

---

# 🤔 Why Do We Use Tags?

Tags help developers:

* Mark release versions
* Identify stable builds
* Simplify deployments
* Roll back to previous releases
* Track important milestones

---

# 🏗️ How Git Tags Work

```text id="0hq2eu"
Commit A
    │
Commit B
    │
Commit C  ← v1.0
    │
Commit D
    │
Commit E  ← v1.1
    │
Commit F
    │
Commit G  ← v2.0
```

Each tag permanently points to a specific commit.

Even after new commits are added, the tag remains attached to its original commit.

---

# 🏷️ Types of Git Tags

Git supports two main types of tags.

## 1️⃣ Lightweight Tag

A lightweight tag is simply a name that points to a commit.

Create one using:

```bash id="3gd57d"
git tag v1.0
```

Use lightweight tags when you only need a quick label.

---

## 2️⃣ Annotated Tag

An annotated tag stores additional information such as:

* Tag name
* Author
* Date
* Description

Create an annotated tag:

```bash id="m1o5vs"
git tag -a v1.0 -m "First stable release"
```

Annotated tags are recommended for official software releases.

---

# 📋 View Tags

Display all tags:

```bash id="jlwmwm"
git tag
```

Example:

```text id="1bxgxu"
v1.0
v1.1
v2.0
```

---

# 🔍 View Tag Information

Display details of an annotated tag:

```bash id="cyvftg"
git show v1.0
```

Git displays:

* Tag information
* Author
* Date
* Message
* Associated commit

---

# 🚀 Push Tags to GitHub

Tags are not pushed automatically.

Push a specific tag:

```bash id="6i0odt"
git push origin v1.0
```

Push all tags:

```bash id="l4v5fo"
git push origin --tags
```

---

# ❌ Delete a Tag

Delete a local tag:

```bash id="65aq2i"
git tag -d v1.0
```

Delete the tag from GitHub:

```bash id="vjlwmq"
git push origin --delete v1.0
```

---

# 📦 Semantic Versioning

Most software projects follow **Semantic Versioning (SemVer)**.

Version format:

```text id="5blgks"
MAJOR.MINOR.PATCH
```

Example:

```text id="e99p78"
v2.4.1
```

Meaning:

| Part  | Description                                 |
| ----- | ------------------------------------------- |
| Major | Breaking changes                            |
| Minor | New features without breaking compatibility |
| Patch | Bug fixes and small improvements            |

Examples:

```text id="56i7g5"
v1.0.0
v1.1.0
v1.1.1
v2.0.0
```

---

# 🔄 Typical Release Workflow

```text id="3n0w2g"
Develop Feature
       │
       ▼
Commit Changes
       │
       ▼
Test Project
       │
       ▼
Create Tag
       │
       ▼
git push origin --tags
       │
       ▼
Release Software
```

---

# 📌 Common Tag Commands

| Command                         | Purpose                  |
| ------------------------------- | ------------------------ |
| `git tag`                       | List all tags            |
| `git tag v1.0`                  | Create a lightweight tag |
| `git tag -a v1.0 -m "message"`  | Create an annotated tag  |
| `git show v1.0`                 | Display tag details      |
| `git push origin v1.0`          | Push a specific tag      |
| `git push origin --tags`        | Push all tags            |
| `git tag -d v1.0`               | Delete a local tag       |
| `git push origin --delete v1.0` | Delete a remote tag      |

---

# 💡 Best Practices

* Use annotated tags for official releases.
* Follow Semantic Versioning.
* Use meaningful version numbers.
* Push tags after creating a release.
* Never rename release tags after publishing.

---

# ❌ Common Mistakes

| Mistake                                        | Better Practice                              |
| ---------------------------------------------- | -------------------------------------------- |
| Using random tag names                         | Follow Semantic Versioning (e.g., `v1.2.0`). |
| Forgetting to push tags                        | Push tags using `git push origin --tags`.    |
| Using lightweight tags for production releases | Prefer annotated tags for official releases. |
| Modifying released tags                        | Treat release tags as permanent milestones.  |

---

# 🎯 Interview Questions

### Q1. What is a Git Tag?

**Answer:**

A Git Tag is a permanent reference to a specific commit, typically used to mark releases, milestones, or stable versions.

---

### Q2. What is the difference between a branch and a tag?

**Answer:**

A branch moves forward as new commits are added, while a tag permanently points to a specific commit and never moves.

---

### Q3. What are the two types of Git Tags?

**Answer:**

* Lightweight Tags
* Annotated Tags

---

### Q4. Which type of tag is recommended for software releases?

**Answer:**

Annotated Tags, because they include metadata such as the author, date, and a descriptive message.

---

### Q5. Which command creates an annotated tag?

```bash id="fh0u2m"
git tag -a v1.0 -m "First stable release"
```

---

### Q6. Are Git Tags pushed automatically to GitHub?

**Answer:**

No. Tags must be pushed explicitly using `git push origin <tag-name>` or `git push origin --tags`.

---

# 📌 Key Takeaways

* Git Tags mark important commits permanently.
* Tags are commonly used for software releases and milestones.
* Lightweight tags are simple references.
* Annotated tags store additional metadata and are recommended for official releases.
* Tags do not move like branches.
* Semantic Versioning helps maintain clear and consistent release versions.

---

## 🎉 Congratulations!

You have now completed the **core Git & GitHub learning path**.

You now understand:

* Git Fundamentals
* Version Control
* GitHub & Remote Repositories
* Git Architecture
* Branching & Merging
* Merge Conflicts
* Git Stash
* Git Tags

With these concepts, you have a strong foundation to start collaborating on real-world software projects.

### 🚀 What's Next?

In future chapters, you can continue with advanced Git topics such as:

* Rebasing
* Cherry-pick
* Reset vs Revert
* Git Reflog
* Interactive Rebase
* Git Hooks
* Git Bisect
* Git Submodules
* Git Worktrees
* GitHub Pull Requests & Code Reviews
* GitHub Actions (CI/CD)
* Open Source Contribution Workflow
