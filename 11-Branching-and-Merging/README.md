# Branching & Merging

## 📖 Introduction

In real-world software development, developers rarely work directly on the **main** branch.

Instead, they create separate branches to develop new features, fix bugs, or experiment with changes without affecting the stable version of the project.

Once the work is complete and tested, the changes are merged back into the main branch.

Branching allows multiple developers to work independently while keeping the project's history clean and organized.

---

# 🤔 What is a Branch?

A **branch** is an independent line of development in a Git repository.

Think of it as a copy of your project's timeline where you can make changes without affecting the original branch.

Every branch has its own commits and history until it is merged.

---

# 🌍 Real-World Analogy

Imagine your team is writing a book.

The published version of the book is stored safely.

Now your manager asks you to add a new chapter.

Instead of editing the published copy directly, you create a duplicate, write the new chapter there, review it, and only after approval merge it back into the original book.

Git branches work exactly the same way.

---

# 🤔 Why Do We Use Branches?

Without branches:

* Every change affects the main codebase.
* Bugs can break production.
* Team collaboration becomes difficult.
* Multiple developers may overwrite each other's work.

With branches:

* Features are developed independently.
* Bugs are fixed safely.
* Experiments don't affect stable code.
* Collaboration becomes easier.

---

# 🏗️ Branch Architecture

```text id="a2w9rk"
                main

Commit A ─── Commit B ─── Commit C
                  │
                  │
          feature-login
                  │
          Commit D
                  │
          Commit E
                  │
          git merge
                  │
                  ▼
Commit A ─── Commit B ─── Commit C ─── Merge Commit
                                   \
                                    Commit D
                                     \
                                      Commit E
```

The `feature-login` branch grows independently until it is merged into `main`.

---

# 🌿 Create a Branch

Create a new branch:

```bash id="b7n4tm"
git branch feature-login
```

List all branches:

```bash id="k3v8pr"
git branch
```

Example:

```text id="j8m2ye"
* main
  feature-login
```

The `*` indicates the current branch.

---

# 🔄 Switch Between Branches

Switch to another branch:

```bash id="w6p9ga"
git switch feature-login
```

Or create and switch in one command:

```bash id="y5l2fd"
git switch -c feature-login
```

---

# 💻 Working on a Feature Branch

Once you've switched branches, continue development as usual:

```bash id="n4r7hj"
git add .
git commit -m "Add login feature"
```

These commits belong only to the current branch.

The `main` branch remains unchanged.

---

# 🔀 Merge a Branch

After completing your work, switch back to the main branch:

```bash id="d1x5qu"
git switch main
```

Merge the feature branch:

```bash id="m8c3vk"
git merge feature-login
```

Git combines the commits from the feature branch into the main branch.

---

# 🏗️ What is a Merge Commit?

When Git combines two different development histories, it may create a **Merge Commit**.

A merge commit records the point where two branches became one.

Example:

```text id="t5k1bh"
Commit A
     │
Commit B
 ├───────────────┐
 │               │
 │          Commit C
 │          Commit D
 │               │
 └──── Merge Commit
```

This preserves the complete history of both branches.

---

# 🗑️ Delete a Branch

Once the branch has been merged successfully, it is no longer needed.

Delete it using:

```bash id="r2m8sn"
git branch -d feature-login
```

This keeps the repository clean.

---

# 💡 Branch is Just a Pointer

One of Git's most important concepts is:

> **A branch is simply a pointer to the latest commit.**

When you commit on a branch, Git moves the branch pointer to the new commit.

That's why creating branches is extremely fast and lightweight.

---

# 🔄 Typical Branch Workflow

```text id="h8z7qw"
main
 │
 │
 ├──── Create Branch
 │
 ▼
feature-login
 │
 │
 ├── Commit
 ├── Commit
 └── Commit
 │
 ▼
Switch to main
 │
 ▼
git merge feature-login
 │
 ▼
Delete Branch
```

This is the workflow followed by most software development teams.

---

# 💡 Best Practices

* Create one branch for one feature or bug fix.
* Never develop directly on the `main` branch.
* Write meaningful commit messages.
* Merge only after testing your changes.
* Delete merged branches to keep the repository clean.
* Use descriptive branch names such as `feature-login`, `bugfix-payment`, or `hotfix-api`.

---

# ❌ Common Mistakes

| Mistake                                | Better Practice                           |
| -------------------------------------- | ----------------------------------------- |
| Developing directly on `main`          | Create a dedicated feature branch.        |
| Mixing multiple features in one branch | Keep one feature per branch.              |
| Keeping branches alive for too long    | Merge them regularly.                     |
| Forgetting to delete merged branches   | Remove merged branches to reduce clutter. |

---

# 🎯 Interview Questions

### Q1. What is a Git branch?

**Answer:**
A branch is an independent line of development that allows developers to work on changes without affecting the main branch.

---

### Q2. Why do developers use branches?

**Answer:**
Branches enable parallel development, safer experimentation, easier collaboration, and better code organization.

---

### Q3. Which command creates a new branch?

```bash id="v3n6ep"
git branch feature-name
```

---

### Q4. Which command creates and switches to a new branch?

```bash id="j7q4cm"
git switch -c feature-name
```

---

### Q5. What does `git merge` do?

**Answer:**
It combines the changes from one branch into another, preserving the project's history.

---

### Q6. What is a Merge Commit?

**Answer:**
A merge commit records the point where two branches are combined into one, preserving both development histories.

---

# 📌 Key Takeaways

* A branch is an independent line of development.
* Branches allow multiple developers to work safely in parallel.
* Merge combines completed work into the target branch.
* A branch is simply a pointer to the latest commit.
* Deleting merged branches keeps the repository organized.

---

## 🚀 What's Next?

Branching makes parallel development possible, but sometimes two developers modify the same file in different branches.

In the next chapter, we'll explore **Merge Conflicts**, understand why they happen, and learn how to resolve them confidently.
