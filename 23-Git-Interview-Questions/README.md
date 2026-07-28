# Git & GitHub Interview Questions

## 📖 Introduction

Git is one of the most frequently asked topics in **Software Development**, **DevOps**, **Cloud**, **SRE**, and **Platform Engineering** interviews.

Interviewers usually don't ask you to memorize commands—they want to understand whether you know **how Git works**, **when to use specific commands**, and **how to solve real-world collaboration problems**.

This chapter covers beginner to advanced interview questions along with concise, interview-ready answers.

---

# 🟢 Beginner Level Questions

## Q1. What is Git?

**Answer:**

Git is a **distributed version control system (DVCS)** used to track changes in source code, collaborate with multiple developers, and maintain project history.

---

## Q2. What is Version Control?

**Answer:**

Version Control is a system that records changes to files over time, allowing developers to track history, collaborate, and restore previous versions if needed.

---

## Q3. Why do we use Git?

**Answer:**

Git helps developers:

* Track code changes
* Collaborate with teams
* Manage multiple features simultaneously
* Recover previous versions
* Resolve merge conflicts
* Maintain project history

---

## Q4. What is the difference between Git and GitHub?

| Git                    | GitHub                 |
| ---------------------- | ---------------------- |
| Version Control System | Git hosting platform   |
| Works locally          | Cloud platform         |
| Tracks history         | Hosts repositories     |
| CLI tool               | Collaboration platform |

---

## Q5. What is a Repository?

**Answer:**

A repository (repo) is a storage location that contains project files, commit history, branches, and Git metadata.

---

## Q6. What is a Commit?

**Answer:**

A commit is a snapshot of your project at a specific point in time.

---

## Q7. What is the purpose of the `.git` folder?

**Answer:**

The `.git` directory stores all Git metadata, including commits, branches, tags, configuration, and repository history.

---

# 🟡 Intermediate Level Questions

## Q8. Explain the Git workflow.

```text id="kc09rg"
Working Directory
        │
        ▼
Staging Area
        │
        ▼
Local Repository
        │
        ▼
Remote Repository
```

Typical workflow:

```bash id="9sulva"
git add .
git commit -m "message"
git push origin main
```

---

## Q9. What is the difference between `git fetch` and `git pull`?

| git fetch                         | git pull                       |
| --------------------------------- | ------------------------------ |
| Downloads changes                 | Downloads + merges changes     |
| Does not modify working directory | Updates current branch         |
| Safe for inspection               | Immediately integrates changes |

---

## Q10. What is the difference between `git merge` and `git rebase`?

| Merge                     | Rebase                            |
| ------------------------- | --------------------------------- |
| Preserves branch history  | Creates a linear history          |
| Creates merge commits     | Rewrites commit history           |
| Safer for shared branches | Better for local feature branches |

---

## Q11. What is a Merge Conflict?

**Answer:**

A merge conflict occurs when Git cannot automatically combine changes because the same section of a file has been modified differently in two branches.

---

## Q12. What is Git Stash?

**Answer:**

Git Stash temporarily saves uncommitted changes so you can switch branches without committing incomplete work.

---

## Q13. What is Git Tag?

**Answer:**

A Git Tag is a permanent reference to a specific commit, commonly used to mark software releases such as `v1.0.0`.

---

## Q14. What is Cherry-pick?

**Answer:**

Git Cherry-pick copies one or more specific commits from one branch and applies them to another branch.

---

## Q15. What is Git Reflog?

**Answer:**

Git Reflog records every movement of `HEAD` and helps recover commits that may no longer appear in the normal commit history.

---

# 🟠 GitHub Questions

## Q16. What is a Fork?

**Answer:**

A Fork is your personal copy of another user's GitHub repository, allowing you to contribute without direct write access.

---

## Q17. What is a Pull Request (PR)?

**Answer:**

A Pull Request is a request to merge changes from one branch or fork into another branch after review.

---

## Q18. What is the difference between Fork and Clone?

| Fork                            | Clone                        |
| ------------------------------- | ---------------------------- |
| Creates a copy on GitHub        | Downloads repository locally |
| Used for external contributions | Used for local development   |

---

## Q19. Why do teams use Pull Requests?

**Answer:**

Pull Requests enable:

* Code reviews
* Team discussions
* Automated testing
* Approval workflows
* Better code quality

---

## Q20. What is the upstream remote?

**Answer:**

The upstream remote points to the original repository, allowing your fork to stay synchronized with new changes.

---

# 🔵 Advanced Level Questions

## Q21. What is Git Reset?

**Answer:**

Git Reset moves the current branch pointer to a different commit and can optionally modify the staging area and working directory.

Types:

* Soft
* Mixed
* Hard

---

## Q22. Difference between Reset, Restore, and Revert?

| Reset               | Restore        | Revert                       |
| ------------------- | -------------- | ---------------------------- |
| Moves HEAD          | Restores files | Creates a new undo commit    |
| Can rewrite history | Safe           | Safe for shared repositories |

---

## Q23. What is Git GC?

**Answer:**

Git Garbage Collection optimizes repository storage by cleaning unnecessary objects and compressing repository data.

---

## Q24. What is Git FSCK?

**Answer:**

Git FSCK verifies repository integrity and detects corrupted or missing Git objects.

---

## Q25. What is Git Blame?

**Answer:**

Git Blame shows who last modified each line of a file and identifies the corresponding commit.

---

## Q26. What is Git Clean?

**Answer:**

Git Clean removes untracked files and directories from the working directory.

---

## Q27. What is HEAD in Git?

**Answer:**

HEAD is a pointer that references the current commit you are working on.

---

## Q28. What is the difference between Fast-forward Merge and Three-way Merge?

| Fast-forward Merge                     | Three-way Merge             |
| -------------------------------------- | --------------------------- |
| No new merge commit                    | Creates a merge commit      |
| Linear history                         | Preserves branch history    |
| Happens when branches haven't diverged | Used after branches diverge |

---

## Q29. What is Detached HEAD?

**Answer:**

A Detached HEAD state occurs when HEAD points directly to a commit instead of a branch, allowing temporary exploration without affecting any branch.

---

## Q30. What happens when you run `git push`?

**Answer:**

Git transfers your local commits to the corresponding branch in the remote repository.

---

# 🔴 Scenario-Based Questions

## Q31. You accidentally deleted a commit. How can you recover it?

**Answer:**

Use:

```bash id="zj10g9"
git reflog
```

Locate the lost commit and restore it:

```bash id="mv58s8"
git reset --hard HEAD@{n}
```

---

## Q32. A teammate deleted a remote branch. How do you clean your local references?

```bash id="jxv4y8"
git remote prune origin
```

---

## Q33. You have uncommitted work but need to switch branches. What should you do?

**Answer:**

Temporarily save your changes:

```bash id="ztqx0n"
git stash
```

Switch branches, then restore your work:

```bash id="nqmy2e"
git stash pop
```

---

## Q34. How do you undo the last commit without losing your changes?

```bash id="x9tf3o"
git reset --soft HEAD~1
```

---

## Q35. How do you undo a commit that has already been pushed?

**Answer:**

Use:

```bash id="ejlwmu"
git revert <commit-id>
```

This creates a new commit that safely reverses the previous changes.

---

## Q36. A production bug needs an immediate fix. Which branch would you create?

**Answer:**

Create a `hotfix` branch, fix the issue, test it, and merge it into the production branch.

---

## Q37. When would you use Rebase instead of Merge?

**Answer:**

Use Rebase on your local feature branch to create a clean, linear commit history before opening a Pull Request.

---

# ⭐ Frequently Asked Commands

| Command               | Purpose                    |
| --------------------- | -------------------------- |
| `git status`          | Check repository status    |
| `git add .`           | Stage changes              |
| `git commit -m "msg"` | Create commit              |
| `git push`            | Upload commits             |
| `git pull`            | Download and merge changes |
| `git fetch`           | Download changes only      |
| `git merge`           | Merge branches             |
| `git rebase`          | Reapply commits            |
| `git stash`           | Save temporary changes     |
| `git reflog`          | View HEAD history          |
| `git reset`           | Move branch pointer        |
| `git revert`          | Undo with a new commit     |
| `git blame`           | Show line authorship       |
| `git clean`           | Remove untracked files     |

---

# 💡 Interview Tips

* Understand concepts before memorizing commands.
* Explain **why** you would use a command, not just **how**.
* Use real-world examples whenever possible.
* Mention best practices, such as using feature branches and Pull Requests.
* Be honest if you haven't used a command in production, but explain its purpose and use case.

---

# 📌 Key Takeaways

* Git interviews focus on concepts, workflows, and problem-solving rather than memorizing commands.
* Be comfortable explaining branching, merging, rebasing, Pull Requests, and collaboration workflows.
* Practice common recovery scenarios such as recovering lost commits, resolving merge conflicts, and undoing changes.
* Understanding real-world use cases will help you answer confidently in both interviews and day-to-day development.

---

## 🚀 What's Next?

You've now completed the complete Git & GitHub learning journey—from fundamentals to advanced concepts and interview preparation.

The final chapter, **Git Hands-on Labs**, will help you apply everything you've learned through practical exercises, real-world scenarios, and interview-style challenges so you can confidently use Git in professional projects.
