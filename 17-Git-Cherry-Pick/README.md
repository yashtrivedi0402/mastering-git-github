# Git Cherry-pick

## 📖 Introduction

In software development, there are situations where you need **only one specific commit** from another branch instead of merging the entire branch.

For example, suppose your teammate fixed a critical bug on a feature branch, but the rest of that branch is still under development. Instead of merging all the unfinished work, you can copy **only the required commit** into your current branch.

Git provides **Cherry-pick** for exactly this purpose.

It allows you to apply one or more selected commits from another branch without merging the complete branch.

---

# 🤔 What is Git Cherry-pick?

**Git Cherry-pick** copies a specific commit from one branch and applies it to another branch.

Unlike **Merge** or **Rebase**, Cherry-pick works on **individual commits**, not the entire branch.

The copied commit becomes a **new commit** with a new commit ID on the target branch.

---

# 🌍 Real-World Analogy

Imagine you're preparing a presentation, and your teammate has created **10 slides** in another presentation.

However, you only need **Slide 4**.

Instead of copying the entire presentation, you copy only that one slide into yours.

Git Cherry-pick works in the same way by copying only the required commit.

---

# 🤔 Why Do We Use Git Cherry-pick?

Git Cherry-pick helps developers:

* Copy a specific commit from another branch.
* Move bug fixes between branches.
* Reuse useful features without merging unfinished work.
* Apply hotfixes to production branches.
* Avoid unnecessary merges.

---

# 🏗️ How Git Cherry-pick Works

Suppose you have two branches.

```text id="6zsmk9"
main

A──B──C

feature

A──B──D──E
```

You only want commit **D**.

Run:

```bash id="x7w0pt"
git cherry-pick <commit-id-of-D>
```

Result:

```text id="4b0f3m"
main

A──B──C──D'

feature

A──B──D──E
```

Notice that **D'** is a new commit.

Although it contains the same changes as **D**, it has a different commit hash because Git creates a new commit.

---

# 🚀 Basic Cherry-pick Workflow

### Step 1: Create a Feature Branch

```bash id="n4jhqv"
git switch -c feature
```

---

### Step 2: Create a New File

```bash id="d3kh12"
touch login.html
git add .
git commit -m "Add login page"
```

---

### Step 3: View Commit History

```bash id="m1rqg7"
git log --oneline
```

Example:

```text id="i1s5ur"
8fd42ab Add login page
```

Copy the commit ID.

---

### Step 4: Switch to Main Branch

```bash id="sj2x8h"
git switch main
```

---

### Step 5: Cherry-pick the Commit

```bash id="2pdxcu"
git cherry-pick 8fd42ab
```

Git copies only that commit into the current branch.

---

### Final History

```text id="2rmds7"
main

A──B──C──D'

feature

A──B──D
```

The complete feature branch is **not merged**.

Only the selected commit is copied.

---

# 🎯 Cherry-pick Multiple Commits

Copy multiple commits:

```bash id="g34hnv"
git cherry-pick <commit1> <commit2>
```

Example:

```bash id="ocxt7m"
git cherry-pick a12bc34 b56de78
```

---

# 🎯 Cherry-pick a Range of Commits

Git also supports copying a sequence of commits.

```bash id="r1v8bz"
git cherry-pick <start-commit>^..<end-commit>
```

Example:

```bash id="22lhru"
git cherry-pick a12bc34^..d45ef67
```

---

# ⚠️ Cherry-pick Conflicts

Sometimes the selected commit modifies the same lines that already exist in the target branch.

Git pauses and reports a conflict.

Example:

```text id="l2h0eu"
CONFLICT (content): Merge conflict in app.js
```

Resolve the conflict manually.

Stage the resolved files.

```bash id="9rnh4d"
git add .
```

Continue Cherry-pick.

```bash id="zrjmyo"
git cherry-pick --continue
```

---

# ❌ Abort Cherry-pick

If you don't want to continue,

```bash id="2mdqps"
git cherry-pick --abort
```

Git restores the repository to its previous state.

---

# 📋 Common Cherry-pick Commands

| Command                           | Purpose                            |
| --------------------------------- | ---------------------------------- |
| `git cherry-pick <commit-id>`     | Copy a specific commit             |
| `git cherry-pick <id1> <id2>`     | Copy multiple commits              |
| `git cherry-pick <start>^..<end>` | Copy a range of commits            |
| `git cherry-pick --continue`      | Continue after resolving conflicts |
| `git cherry-pick --abort`         | Cancel the Cherry-pick             |

---

# 🔄 Merge vs Rebase vs Cherry-pick

| Feature                     | Merge              | Rebase           | Cherry-pick              |
| --------------------------- | ------------------ | ---------------- | ------------------------ |
| Works on entire branch      | ✅                  | ✅                | ❌                        |
| Works on individual commits | ❌                  | ❌                | ✅                        |
| Creates merge commit        | Usually            | ❌                | ❌                        |
| Rewrites history            | ❌                  | ✅                | ❌                        |
| Best for                    | Combining branches | Cleaning history | Copying selected commits |

---

# 💡 Best Practices

* Cherry-pick only the commits you actually need.
* Use Cherry-pick for hotfixes and bug fixes.
* Verify the commit ID before running the command.
* Resolve conflicts carefully before continuing.
* Avoid repeatedly Cherry-picking the same commit into the same branch.

---

# ❌ Common Mistakes

| Mistake                              | Better Practice                                               |
| ------------------------------------ | ------------------------------------------------------------- |
| Cherry-picking the wrong commit      | Verify the commit using `git log --oneline` first             |
| Cherry-picking large feature commits | Prefer Merge or Rebase for complete features                  |
| Forgetting to resolve conflicts      | Resolve conflicts before running `git cherry-pick --continue` |
| Copying duplicate commits            | Check whether the commit already exists in the target branch  |

---

# 🎯 Interview Questions

### Q1. What is Git Cherry-pick?

**Answer:**

Git Cherry-pick copies one or more selected commits from one branch and applies them to another branch without merging the entire branch.

---

### Q2. What is the difference between Merge and Cherry-pick?

**Answer:**

Merge combines the complete branch, whereas Cherry-pick copies only the selected commit(s).

---

### Q3. Does Cherry-pick create a new commit?

**Answer:**

Yes. Git creates a new commit with a new commit hash on the target branch.

---

### Q4. Which command copies a specific commit?

```bash id="w7obxy"
git cherry-pick <commit-id>
```

---

### Q5. How do you continue after resolving Cherry-pick conflicts?

```bash id="b9w1hx"
git cherry-pick --continue
```

---

### Q6. How do you cancel an ongoing Cherry-pick?

```bash id="9tvq4j"
git cherry-pick --abort
```

---

# 📌 Key Takeaways

* Git Cherry-pick copies selected commits instead of entire branches.
* It is useful for bug fixes, hotfixes, and reusing specific changes.
* Cherry-picked commits receive new commit hashes.
* Cherry-pick can produce conflicts, which must be resolved before continuing.
* Use Merge for complete branches, Rebase for a clean history, and Cherry-pick for individual commits.

---

## 🚀 What's Next?

Now that you've learned how to copy individual commits between branches, it's time to make your GitHub workflow more secure and convenient.

In the next chapter, you'll learn **Git SSH Authentication**—how to generate SSH keys, connect your local machine to GitHub, test the connection, and securely push and pull code without entering your username and password every time.
