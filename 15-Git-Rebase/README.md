# Git Rebase

## 📖 Introduction

As projects grow, developers create multiple branches to work on new features, bug fixes, and experiments. Eventually, these branches need to be integrated back into the main branch.

The most common way to combine branches is **Git Merge**, but merging often creates additional **merge commits**, making the commit history more complex over time.

To maintain a **clean, linear, and easy-to-read commit history**, Git provides another powerful feature called **Git Rebase**.

Instead of creating a merge commit, Git Rebase **replays your branch's commits on top of another branch**, making it appear as if your work started from the latest version of that branch.

---

# 🤔 What is Git Rebase?

**Git Rebase** is a command that moves or reapplies commits from one branch onto another branch.

Instead of combining two branches with a merge commit, rebase rewrites the commit history by replaying commits one by one.

As a result, the project history becomes **linear**, making it easier to understand and navigate.

---

# 🌍 Real-World Analogy

Imagine two students are writing different chapters of the same book.

While you are writing **Chapter 5**, another student updates **Chapters 1–4**.

Instead of attaching your work at the end with an extra note saying *"Merged later"*, you rewrite your Chapter 5 as if you had started writing after reading the latest version of Chapters 1–4.

The story flows naturally without any unnecessary interruption.

That's exactly how **Git Rebase** works.

---

# 🤔 Why Do We Use Git Rebase?

Git Rebase helps developers:

* Maintain a clean commit history
* Avoid unnecessary merge commits
* Replay feature branch commits on top of the latest branch
* Make project history easier to review
* Simplify debugging using `git log`

---

# 🏗️ Merge vs Rebase

### Using Merge

```text
main
A──B──C──────────────M
     \              /
      D────E───────
         feature
```

A new **Merge Commit (M)** is created.

---

### Using Rebase

```text
main
A──B──C──D'──E'
```

Instead of creating a merge commit, Git replays commits **D** and **E** after **C**.

The result is a clean and linear history.

---

# 🔄 How Git Rebase Works

Suppose you have two branches.

```text
main
A──B──C

feature
     \
      D──E
```

Meanwhile, another developer adds a commit to **main**.

```text
main
A──B──C──F

feature
     \
      D──E
```

Now your feature branch is behind the latest main branch.

Run:

```bash
git switch feature
git rebase main
```

Git temporarily removes commits **D** and **E**, updates the feature branch to **F**, and then reapplies **D** and **E**.

Result:

```text
main
A──B──C──F

feature
          \
           D'──E'
```

The commits have the same changes but receive new commit IDs because they were recreated.

---

# 🚀 Basic Rebase Workflow

### Step 1: Create a Feature Branch

```bash
git switch -c feature
```

---

### Step 2: Make Changes

```bash
touch login.html
git add .
git commit -m "Add login page"
```

---

### Step 3: Switch to Main

```bash
git switch main
```

---

### Step 4: Make Another Commit

```bash
touch home.html
git add .
git commit -m "Add home page"
```

Current history:

```text
main
A──B──C──F

feature
     \
      D
```

---

### Step 5: Rebase Feature Branch

```bash
git switch feature
git rebase main
```

---

### Step 6: Merge into Main

```bash
git switch main
git merge feature
```

Since the feature branch is already ahead of main, Git performs a **Fast-Forward Merge**.

No extra merge commit is created.

Final history:

```text
main
A──B──C──F──D'
```

---

# 🔥 Fast-Forward Merge

After rebasing, merging becomes much simpler.

```text
Before Merge

main
A──B──C──F

feature
          \
           D'
```

```text
After Merge

main
A──B──C──F──D'
```

Git simply moves the `main` branch pointer forward.

---

# ⚠️ Rebase Conflicts

Sometimes the same lines of code are modified in both branches.

Git pauses the rebase and reports a conflict.

Example:

```text
CONFLICT (content): Merge conflict in app.js
```

Resolve the conflict manually.

Then continue:

```bash
git add .
git rebase --continue
```

---

# ❌ Abort Rebase

If you decide not to continue the rebase,

```bash
git rebase --abort
```

Git restores the repository to its previous state.

---

# ⏭️ Skip a Commit

If a particular commit isn't needed during rebasing:

```bash
git rebase --skip
```

Git skips that commit and continues with the remaining ones.

---

# 🎯 Interactive Rebase

Interactive Rebase lets you modify commit history before sharing your code.

Start Interactive Rebase:

```bash
git rebase -i HEAD~3
```

Common operations:

| Command  | Purpose                                   |
| -------- | ----------------------------------------- |
| `pick`   | Keep commit                               |
| `reword` | Change commit message                     |
| `edit`   | Modify commit                             |
| `squash` | Combine commits                           |
| `fixup`  | Merge commits without keeping the message |
| `drop`   | Remove commit                             |

Interactive Rebase is commonly used to clean up commits before opening a Pull Request.

---

# 📋 Common Rebase Commands

| Command                 | Purpose                            |
| ----------------------- | ---------------------------------- |
| `git rebase main`       | Rebase current branch onto main    |
| `git rebase --continue` | Continue after resolving conflicts |
| `git rebase --abort`    | Cancel the rebase                  |
| `git rebase --skip`     | Skip the current commit            |
| `git rebase -i HEAD~3`  | Start Interactive Rebase           |

---

# 💡 Best Practices

* Rebase your feature branch regularly to stay up to date.
* Resolve conflicts carefully before continuing.
* Use Interactive Rebase to clean commit history before creating a Pull Request.
* Prefer rebase for local feature branches.
* Keep commit messages meaningful.

---

# ❌ Common Mistakes

| Mistake                                                | Better Practice                                          |
| ------------------------------------------------------ | -------------------------------------------------------- |
| Rebasing the shared `main` branch                      | Rebase only your local feature branches                  |
| Force pushing without understanding the impact         | Verify history before using `git push --force`           |
| Ignoring rebase conflicts                              | Resolve every conflict carefully                         |
| Using rebase when preserving exact history is required | Use merge when historical merge information is important |

---

# 🎯 Interview Questions

### Q1. What is Git Rebase?

**Answer:**

Git Rebase moves or reapplies commits from one branch onto another to create a clean and linear commit history.

---

### Q2. What is the difference between Merge and Rebase?

**Answer:**

Merge combines branches by creating a new merge commit, whereas Rebase reapplies commits on top of another branch without creating an additional merge commit.

---

### Q3. Does Git Rebase create a merge commit?

**Answer:**

No. Git Rebase replays commits instead of creating a merge commit.

---

### Q4. Which command starts a rebase?

```bash
git rebase main
```

---

### Q5. How do you continue a rebase after resolving conflicts?

```bash
git rebase --continue
```

---

### Q6. How do you cancel an ongoing rebase?

```bash
git rebase --abort
```

---

### Q7. What is Interactive Rebase?

**Answer:**

Interactive Rebase allows developers to edit, reorder, combine, rename, or remove commits before sharing them with others.

---

# 📌 Key Takeaways

* Git Rebase creates a clean and linear commit history.
* Unlike Merge, Rebase does not create unnecessary merge commits.
* Rebasing replays commits on top of another branch.
* Interactive Rebase helps organize commit history before code review.
* Rebase is best suited for local feature branches before merging into the main branch.

---

## 🚀 What's Next?

Now that you understand how to maintain a clean commit history using Git Rebase, it's time to learn how to safely undo changes in Git.

In the next chapter, you'll explore **Git Reset, Git Restore, and Git Revert**. You'll learn the differences between these commands, when to use each one, how they affect your working directory, staging area, and commit history, and how to recover from common mistakes without losing important work.
