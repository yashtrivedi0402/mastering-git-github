# Merge Conflicts

## 📖 Introduction

Git is designed to combine changes made by multiple developers automatically. In most cases, Git can merge different changes without any issues.

However, sometimes two developers modify the **same part of the same file** in different branches. Since Git cannot determine which change is correct, it stops the merge and asks the developer to resolve the conflict manually.

This situation is called a **Merge Conflict**.

Understanding merge conflicts is an essential Git skill because they are a normal part of collaborative software development.

---

# 🤔 What is a Merge Conflict?

A **Merge Conflict** occurs when Git cannot automatically merge changes from two branches because the same content has been modified differently.

Git pauses the merge process until the conflict is resolved.

---

# 🌍 Real-World Analogy

Imagine two authors are editing the same paragraph of a book.

### Author A writes:

> Git is a distributed version control system.

### Author B writes:

> Git is the world's most popular version control system.

When the editor receives both versions, they cannot automatically decide which sentence should remain.

The editor must manually choose the final version.

Git behaves exactly like this.

---

# 🤔 Why Do Merge Conflicts Occur?

Merge conflicts usually happen when:

* Two developers edit the same line.
* One developer deletes code while another modifies it.
* Two branches rename or move the same file differently.
* Both branches change the same configuration.

---

# 🏗️ Conflict Workflow

```text
                main

Commit A ─── Commit B
                  │
                  │
          feature-login
                  │
             Edit app.js
                  │
             Commit C
                  │
                  ▼
                Merge
                  │
                  ▼
          ❌ Merge Conflict
                  │
                  ▼
        Resolve Conflict
                  │
                  ▼
            git add
                  │
                  ▼
          git commit
```

Git stops the merge until the conflict is resolved.

---

# 💻 Example Scenario

Suppose the file contains:

```text
Version 1
```

---

### On the `main` branch

```text
Hello from Main Branch
```

Commit the change.

---

### On the `feature-login` branch

```text
Hello from Feature Branch
```

Commit the change.

Now merge:

```bash
git switch main
git merge feature-login
```

Git cannot decide which version should remain.

---

# ⚠️ Conflict Markers

Git marks the conflicting section like this:

```text
<<<<<<< HEAD
Hello from Main Branch
=======
Hello from Feature Branch
>>>>>>> feature-login
```

Meaning:

* `<<<<<<< HEAD` → Current branch (`main`)
* `=======` → Separator
* `>>>>>>> feature-login` → Incoming branch

These markers help identify the conflicting changes.

---

# 🛠️ Resolving a Merge Conflict

Open the affected file and decide what the final content should be.

Example:

```text
Hello from Main Branch
Hello from Feature Branch
```

Or choose only one version.

Remove all conflict markers before saving the file.

---

# ✅ Complete the Merge

After fixing the file:

Stage the resolved file:

```bash
git add app.js
```

Complete the merge:

```bash
git commit
```

Git creates a merge commit that records the successful merge.

---

# 🔄 Complete Conflict Resolution Workflow

```text
git merge feature-login
        │
        ▼
Conflict Detected
        │
        ▼
Open File
        │
        ▼
Edit File
        │
        ▼
Remove Conflict Markers
        │
        ▼
git add
        │
        ▼
git commit
```

---

# 🚫 Abort a Merge

If you decide not to continue the merge:

```bash
git merge --abort
```

Git restores the repository to the state before the merge started.

---

# 💡 Best Practices

* Pull the latest changes before creating new work.
* Merge feature branches regularly.
* Keep branches short-lived.
* Resolve conflicts carefully instead of rushing.
* Review the merged code before committing.
* Communicate with teammates when working on the same files.

---

# ❌ Common Mistakes

| Mistake                               | Better Practice                                          |
| ------------------------------------- | -------------------------------------------------------- |
| Deleting conflict markers incorrectly | Remove markers only after choosing the correct content.  |
| Committing without reviewing          | Always verify the final merged code.                     |
| Keeping branches alive for weeks      | Merge frequently to reduce conflicts.                    |
| Ignoring conflicts                    | Resolve them immediately to avoid larger problems later. |

---

# 🎯 Interview Questions

### Q1. What is a Merge Conflict?

**Answer:**

A merge conflict occurs when Git cannot automatically combine changes because the same content has been modified differently in multiple branches.

---

### Q2. Why does Git stop during a merge conflict?

**Answer:**

Git cannot determine which version is correct, so it pauses the merge and waits for the developer to resolve the conflict manually.

---

### Q3. Which command aborts an ongoing merge?

```bash
git merge --abort
```

---

### Q4. How do you resolve a merge conflict?

**Answer:**

1. Open the conflicting file.
2. Review the conflict markers.
3. Choose or combine the correct changes.
4. Remove the conflict markers.
5. Save the file.
6. Run `git add`.
7. Run `git commit`.

---

### Q5. What does `HEAD` represent in a conflict?

**Answer:**

`HEAD` represents the currently checked-out branch during the merge.

---

# 📌 Key Takeaways

* Merge conflicts are a normal part of collaborative development.
* They occur when Git cannot automatically combine changes.
* Git highlights conflicts using special markers.
* Developers must manually resolve the conflict.
* After resolving, stage the file and create a merge commit.
* Good branching practices reduce the number of conflicts.

---

## 🚀 What's Next?

Now that you know how to resolve merge conflicts, the next step is learning how to temporarily save unfinished work without committing it.

In the next chapter, we'll explore **Git Stash**, understand when to use it, and learn how it helps you switch tasks without losing your progress.
